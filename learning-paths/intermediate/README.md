# Intermediate Level – Spec‑Kit Development

After building a few apps with beginner tools, step up to **GitHub Spec‑Kit** for more structured projects.  At this level you'll move beyond simple prompts and create requirement‑driven applications.

## What is GitHub Spec-Kit?

**GitHub Spec-Kit** is an official open-source toolkit (42.9k+ stars) that enables **spec-driven development**—where specifications become executable blueprints for AI-assisted development.

**Official Repository:** [github.com/github/spec-kit](https://github.com/github/spec-kit)
**Complete Guide:** [docs/SPEC-KIT-GUIDE.md](../../docs/SPEC-KIT-GUIDE.md)

### Why Use Spec-Kit?

Traditional vibe coding: `Prompt → Code`
Spec-Kit approach: `Constitution → Specification → Plan → Tasks → Implementation`

**Benefits:**
- Systematic progression from idea to working app
- Built-in project governance and best practices
- AI maintains consistency across all features
- Team collaboration through shared specifications
- Memory system retains context across sessions

## Workflow Summary

### 1. Installation

```bash
# Install spec-kit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Initialize new project
specify init my-project

# Or add to existing project
cd existing-project
specify init .
```

### 2. Six-Phase Development Workflow

**Phase 1: Establish Principles** (`/speckit.constitution`)
- Define project governance and development guidelines
- Set technology constraints and code standards
- Document security and performance requirements

**Phase 2: Create Specifications** (`/speckit.specify`)
- Write detailed user stories with acceptance criteria
- Define database schemas and API contracts
- Document edge cases and error scenarios

**Phase 3: Plan Implementation** (`/speckit.plan`)
- Document technical architecture and tech stack
- Create file structure and module organization
- Plan testing strategy and deployment approach

**Phase 4: Generate Tasks** (`/speckit.tasks`)
- Break implementation into actionable 2-4 hour tasks
- Assign priorities and dependencies
- Estimate time and resources

**Phase 5: Execute Development** (`/speckit.implement`)
- AI generates code for specific tasks
- Follows constitution, specification, and plan
- Maintains consistency across implementation

**Phase 6: Validate** (`/speckit.analyze`, `/speckit.checklist`)
- Quality assurance and alignment checking
- Pre-deployment validation
- Documentation review

### 3. Supported AI Tools

Spec-Kit works with:
- **Claude Code** - Natural language codebase automation
- **Cursor** - AI code editor
- **Windsurf** - Agentic IDE
- **GitHub Copilot** - AI pair programming
- **Gemini CLI** - Google's AI coding assistant
- **Qwen Code** - Open-source coding assistant

## Quick Start Example

```bash
# Install and initialize
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
specify init todo-app --ai claude
cd todo-app

# In your AI agent (Claude Code, Cursor, etc.):
/speckit.constitution
# Define: Simple, offline-first, React + TypeScript

/speckit.specify
# Write user stories: Add todo, complete todo, delete todo

/speckit.plan
# Tech stack: React 18, TypeScript, LocalStorage, Tailwind

/speckit.tasks
# Generate: 12 tasks with estimates

/speckit.implement TASK-001
# AI builds first task according to spec

# Continue for each task...
```

## Key Features

**Memory System**
- Stores constitution, specs, plans, and tasks in `.specify/memory/`
- AI maintains context across sessions
- Team shares project knowledge through version-controlled memory

**Slash Commands**
- Structured workflow through intuitive commands
- Each phase builds on previous work
- AI follows project-specific patterns

**Git Integration**
- Automatic feature branch management
- Commit tracking and history
- Team collaboration support

**Technology Agnostic**
- Works with any tech stack
- No framework lock-in
- Flexible architecture

## Learning Path

**Week 1-2: Fundamentals**
- Install spec-kit and create first project
- Learn constitution and specification writing
- Practice with simple applications (todo list, calculator)
- Study example projects in guide

**Week 3-4: Advanced Workflows**
- Multi-feature applications
- Database integration and API design
- Testing strategy implementation
- Team collaboration patterns

**Week 5-6: Production Projects**
- Full-stack applications with authentication
- Deployment automation
- Performance optimization
- Security best practices

**Week 7-8: Mastery**
- Contributing to existing projects (brownfield)
- Architectural decision documentation
- Custom workflow optimization
- Teaching others

## Essential Resources

**Documentation:**
- **[Complete Spec-Kit Guide](../../docs/SPEC-KIT-GUIDE.md)** - Comprehensive 50+ page guide with examples
- **[Official Repository](https://github.com/github/spec-kit)** - Source code and official docs
- **[GitHub Discussions](https://github.com/github/spec-kit/discussions)** - Community support

**Tools:**
- **[OpenRouter](https://openrouter.ai/)** - Unified API for AI models
- **[Claude Code](https://www.anthropic.com/claude-code)** - Recommended AI agent
- **[Cursor](https://cursor.sh)** - AI code editor with spec-kit support

## Common Workflows

### Solo Developer
1. Initialize with `specify init`
2. Spend 1-2 hours on constitution and specs
3. Generate plan and tasks (1 hour)
4. Implement systematically (1 task at a time)
5. Validate before deployment

### Team Project
1. Lead creates constitution, team reviews
2. Feature owners write specifications
3. Team reviews specs via pull requests
4. Lead generates implementation plan
5. Tasks distributed among developers
6. Regular code reviews against specs

## Best Practices

**Constitution Writing:**
✅ Be specific about technology choices
✅ Include measurable goals (performance, coverage)
✅ Document security requirements
✅ Keep concise (1-2 pages)

**Specification Writing:**
✅ Use user story format: "As a [user], I want [goal], so that [benefit]"
✅ Include acceptance criteria
✅ Document edge cases
✅ Specify API contracts and schemas

**Implementation:**
✅ One task at a time
✅ Test immediately after each task
✅ Commit frequently with descriptive messages
✅ Review AI-generated code
✅ Update documentation

## Next Steps

1. **Read the [Complete Spec-Kit Guide](../../docs/SPEC-KIT-GUIDE.md)**
2. **Install spec-kit** and try the todo app example
3. **Join the community** via GitHub Discussions
4. **Build your first spec-driven project**
5. **Progress to Advanced Level** when ready for CLI mastery

**Ready for Advanced?** Move to [CLI Programming](../ADVANCED/README.md) for tools like Claude Code and Aider with full terminal control.
