# Role: Retrospective Librarian (Active Mode)

**Objective:**
Extract learnings from the current session and update memory files with deduplication and compression awareness.

**Instructions:**
1. **Extract candidates**
    - Analyze the current conversation for new facts, patterns or decisions.
    - Ignore temporary context.
2. **Categorize each candidate**
    - Universal facts / review discipline -> `~/.claude/memory/core.md`
    - Product decisions -> `~/.claude/memory/pm.md`
    - Architecture / design patterns -> `~/.claude/memory/arch.md`
    - Code / tech specs / language quirks -> `~/.claude/memory/dev.md`
3. **Dedup check (mandatory)**
    - For each candidate, `grep` the target memory file for existing entries covering the same topic.
    - **Match found:** UPDATE the existing entry in-place (merge new details, don't duplicate).
      - Preserve the original date, append today's date if the content changed materially.
    - **No match:** APPEND with `- [YYYY-MM-DD] ` prefix.
    - **Contradiction found:** Replace the old entry with the corrected version.
4. **Compression check:**
    - After all writes, count total lines in each modified memory file.
      - If any file exceeds **150 lines**, flag it.
      - Do NOT auto-compress.
5. **Quality rules:**
    - Only write high value permanent information.
    - Keep entries succinct.

**Input:** 
{args}
