# claude-system
A practical, simple and effective system on top of claude code for application developers.

## Overview
`claude-system` provides five command templates that guide Claude through different phases of software development:

- **`/pm`** - Senior Product Manager: Requirements phase, create outcome-oriented PRDs and validate feasibility.
- **`/arch`** - Staff Software Architect: Design phase, create technical specifications, identify architectural risks.
- **`/dev`** - Senior Software Engineer: Implementation phase, write robust code with TDD-first approach.
- **`/reviewer`** - Principal Code Reviewer: Quality assurance, ensure code quality, security, and maintainability.
- **`/retro`** - Retrospective Librarian: Learning phase, extract and organize insights into persistent memory.

The complete system is explained in a series of blog posts:
1. [Building with Coding Agents: Designing Bounded Personas](https://asimkprasad.substack.com/p/systematizing-coding-agents)
2. [Building with Coding Agents: Parallel Isolated Project Context](https://asimkprasad.substack.com/p/building-with-coding-agents-keeping)
3. [Building with Coding Agents: Stitching it Together](https://asimkprasad.substack.com/p/building-with-coding-agents-stitching)
4. [Building with Coding Agents: Continuous Learning](https://asimkprasad.substack.com/p/building-with-coding-agents-continuous)

## How It Works
Each skill is a specialized prompt template that injects relevant context and guidance. They follow a consistent structure:

1. **Memory Injection** - Loads persistent context from memory files
2. **Role Definition** - Sets expectations and objectives
3. **Detailed Instructions** - Step-by-step guidance for the task
4. **Output Structure** - Consistent artifact organization

### Memory System
The system maintains four memory files for institutional knowledge:

- `memory/core.md` - Universal facts and project metadata
- `memory/arch.md` - Architectural decisions and patterns
- `memory/dev.md` - Code patterns, tech stack, implementation conventions
- `memory/pm.md` - Product strategy and context

## Usage
### Invoking Skills
Use the `/pm`, `/arch`, `/dev`, `/reviewer`, or `/retro` commands in Claude Code:

```bash
/arch "design a caching layer for the API"
/dev "implement the design from the TDD first approach"
/pm "write a PRD for the user authentication feature"
/reviewer "review the code changes in this PR"
/retro "extract learnings from this session"
```

### Setting Up
1. Copy the `commands/*.md` files to your Claude Code installation's command directory
2. Initialize the `memory/*.md` files with your project context
3. Invoke skills as needed throughout your development workflow

## Project Structure
```
claude-system/
├── commands/          # Skill/command templates
│   ├── arch.md       # Architect role
│   ├── dev.md        # Developer role
│   ├── pm.md         # Product Manager role
│   ├── reviewer.md   # Code Reviewer role
│   └── retro.md      # Retrospective Librarian role
├── memory/           # Persistent context files
│   ├── core.md       # Universal project facts
│   ├── arch.md       # Architecture decisions
│   ├── dev.md        # Development conventions
│   └── pm.md         # Product context
└── .gitignore        # Standard exclusions
```

## Philosophy
This system is built on the principle of **structured role-based thinking**. Rather than treating Claude as a monolithic assistant, we engage specialized "personas" that each own a specific phase of development:

- **PM owns the why** - validating outcomes and market fit
- **Architect owns the shape** - preventing downstream churn
- **Developer owns the how** - catching edge cases and ensuring robustness
- **Reviewer owns the quality** - maintaining standards
- **Retrospective owns the learning** - capturing and applying insights

Overtime, as you keep using retrospection, the memory files get richer and the system needs less steering.

## License
MIT License - See LICENSE file for details.

## Contributing
This is a foundational template system. Contributions welcome—consider adding domain-specific skills or enhancing existing templates.
