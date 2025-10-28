# Vibe Coding Resources Guide

> **Transform ideas into apps using natural language and AI assistance**

A comprehensive guide for Milwaukee's **Vibe Coding Thursday** event, designed to help anyone—regardless of traditional programming experience—build applications through AI-assisted development.

[![GitHub](https://img.shields.io/badge/GitHub-VibeCodingThursday-blue)](https://github.com/yourusername/VibeCodingThursday)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Table of Contents

- [What is Vibe Coding?](#what-is-vibe-coding)
- [Quick Start](#quick-start)
- [Learning Paths](#learning-paths)
  - [Beginner: Web-Based Tools](#beginner-web-based-tools)
  - [Intermediate: Spec-Kit Development](#intermediate-spec-kit-development)
  - [Advanced: CLI Programming](#advanced-cli-programming)
- [Repository Structure](#repository-structure)
- [Available Tools](#available-tools)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [Resources](#resources)
- [License](#license)

---

## What is Vibe Coding?

**Vibe coding** is a modern programming approach where you describe applications in plain English and let AI assistants generate working code. This methodology:

- Opens software development to creators of all skill levels
- Lets you focus on product vision and user experience instead of syntax
- Accelerates prototyping and iteration cycles
- Maintains professional code quality through AI-assisted best practices

By offloading boilerplate and implementation details to AI, you can concentrate on what matters most: building great products.

---

## Quick Start

### 1. Choose Your Level

- **Beginner?** Start with browser-based tools (no installation required)
- **Intermediate?** Try spec-driven development with GitHub workflows
- **Advanced?** Dive into CLI tools for maximum control

### 2. Set Up Your API Key

Most tools use [OpenRouter](https://openrouter.ai/) for AI capabilities:

1. Sign up at [OpenRouter](https://openrouter.ai/)
2. Generate an API key
3. Add it to your chosen tool's settings
4. Keep it secure in a `.env` file (see [UNIVERSAL-PRACTICES](docs/UNIVERSAL-PRACTICES.md))

### 3. Pick a Starting Project

Browse [example prompts](docs/prompts.md) or try these:

- **Blog**: "Build a basic blog with posts and comments"
- **Tracker**: "Create a mobile app that tracks daily mood"
- **Portfolio**: "Make a portfolio website with project showcase"

---

## Learning Paths

### Beginner: Web-Based Tools

**Best for:** First-time builders, rapid prototyping, no local setup

Start with browser-based platforms that handle all configuration:

- **[Replit + Ghostwriter](https://replit.com)** - Full browser IDE with integrated AI
- **[Lovable](https://lovable.dev)** - Polished designs without detailed instructions
- **[v0 by Vercel](https://v0.dev)** - Technical breakdowns with animated previews

**Learn more:** [levels/BEGINNER/README.md](levels/BEGINNER/README.md)

### Intermediate: Spec-Kit Development

**Best for:** Structured workflows, requirement-driven development, team projects

Move beyond ad-hoc prompts with GitHub Spec-Kit:

1. Write a Product Requirements Document (PRD) in YAML/Markdown
2. Feed specifications into scaffolding systems
3. Use AI completions via OpenRouter to iterate
4. Gradually refine front-end and back-end components

**Learn more:** [levels/INTERMEDIATE/README.md](levels/INTERMEDIATE/README.md)

### Advanced: CLI Programming

**Best for:** Experienced developers, fine-grained control, production systems

Command-line tools for AI pair-programming:

- **[Cursor CLI](https://cursor.sh)** - File-level refactoring and testing
- **[Claude Code](https://www.anthropic.com/claude-code)** - Codebase understanding and Git automation
- **[Aider](https://aider.chat)** - Terminal-based pair programming

**Learn more:** [levels/ADVANCED/README.md](levels/ADVANCED/README.md)

---

## Repository Structure

```
VibeCodingThursday/
├── README.md                 # This file - main guide and entry point
├── CONTRIBUTING.md           # How to contribute to this project
├── LICENSE                   # MIT License
├── .gitignore               # Files to exclude from version control
│
├── docs/                    # Documentation and reference materials
│   ├── UNIVERSAL-PRACTICES.md  # Best practices for all projects
│   ├── tools.md                # Comprehensive tool catalog
│   └── reminders.md            # Quick tips and gotchas
│
├── levels/                  # Learning materials by skill level
│   ├── BEGINNER/
│   │   ├── README.md          # Beginner guide and tools
│   │   └── prompts.md         # Example prompts for beginners
│   ├── INTERMEDIATE/
│   │   ├── README.md          # Spec-kit workflow guide
│   │   └── prompts.md         # Intermediate prompt examples
│   └── ADVANCED/
│       ├── README.md          # CLI tools and advanced techniques
│       └── prompts.md         # Advanced prompt examples
│
├── examples/                # Sample projects (coming soon)
│   └── README.md
│
└── .obsidian/              # Obsidian vault config (optional)
```

---

## Available Tools

### Browser-Based Platforms
- **Bolt.new** - Full-stack web and mobile apps
- **Lovable** - Superhuman full-stack engineering
- **v0 by Vercel** - Next.js frontend builder
- **Replit** - Browser IDE with AI agent

### IDE Integrations
- **Cursor** - AI code editor
- **Windsurf by Codeium** - Agentic IDE
- **Zed** - High-performance collaborative editor

### CLI Tools
- **Claude Code** - Natural language codebase automation
- **Aider** - AI pair-programming in terminal
- **codename goose** - Local AI agent with MCP extensions

**Full catalog:** [docs/tools.md](docs/tools.md)

---

## Best Practices

### Version Control
- Commit early and often with descriptive messages
- Use feature branches for all development
- Review AI-generated code before merging

### Security
- Never commit API keys or secrets
- Use `.env` files and proper `.gitignore`
- Rotate keys regularly

### Documentation
- Write in Markdown alongside code
- Update READMEs when adding features
- Use clear headings and short paragraphs

**Full guidelines:** [docs/UNIVERSAL-PRACTICES.md](docs/UNIVERSAL-PRACTICES.md)

---

## Contributing

We welcome contributions from the community! Whether you're:

- Adding new tool recommendations
- Sharing example prompts
- Improving documentation
- Reporting issues

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## Resources

### Official Links
- [Vibe Coding Thursday Event](https://www.meetup.com/milwaukee-tech/)
- [OpenRouter API](https://openrouter.ai/)
- [Awesome Vibe Coding Resources](https://github.com/awesome-vibe-coding)

### Community
- Join our [Discord](#) (coming soon)
- Follow on [Twitter/X](#) (coming soon)
- Share your projects with `#VibeCodingThursday`

### Learn More
- [What is AI-Assisted Development?](docs/UNIVERSAL-PRACTICES.md)
- [Choosing the Right Tool](docs/tools.md)
- [Example Projects](examples/)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

Created for Milwaukee's **Vibe Coding Thursday** community event. Special thanks to all contributors and the Milwaukee tech community.

**Happy Vibe Coding! 🚀**

---

*Last updated: October 2025*
