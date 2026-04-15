# OpenCode Skills Repository

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) 
![GitHub last commit](https://img.shields.io/github/last-commit/Solenad/opencode-skills)

A comprehensive collection of modular AI agent skills designed for OpenCode, focused primarily on backend development, DevOps practices, and development workflow automation.

## Project Description

This repository serves as a centralized collection of specialized skills for the OpenCode agent system. Each skill is a self-contained module that provides domain-specific instructions and workflows for executing complex, multi-step development tasks. The skills are designed to work with the OpenCode agent system, enabling AI assistants to perform sophisticated backend engineering, architecture enforcement, and development lifecycle management tasks.

## Technology Stack

- **Skill Definition Format**: Markdown-based skill files with YAML frontmatter
- **Version Control**: Git-based repository management
- **Documentation**: Standardized README.md and SKILL.md formats
- **Platform**: Platform-agnostic (Windows, Linux, macOS compatible)
- **Skill Engine**: OpenCode agent system

## Project Architecture

```
opencode-skills/
├── [skill-name]/
│ └── SKILL.md          # Individual skill definition
├── LICENSE               # MIT License
└── README.md            # This documentation file
```

This repository follows a modular architecture where each skill is independently packaged and discoverable. The architecture supports:

- **Modular Skill System**: Each subdirectory represents an individual skill with its own SKILL.md definition
- **Hierarchical Organization**: Backend-related skills are grouped with common prefixes
- **Self-Documenting**: Each skill contains its own documentation and usage instructions
- **Version Control Integration**: Skills are managed through Git for version tracking and distribution

## Getting Started

### Prerequisites

- Git installed and configured
- OpenCode agent system or compatible AI assistant framework
- Access to a terminal or command prompt

### Installation

1. Clone the repository:
```bash
git clone https://github.com/roehannicholas/opencode-skills.git
cd opencode-skills
```

2. Configure your OpenCode system to use the skills from this repository. Each skill can be loaded dynamically using the OpenCode skill loading mechanism.

3. Use the `find-skills` skill to discover available skills:
```bash
# Load the find-skills skill to explore available skills
skill load find-skills
```

## Project Structure

### Backend Development Skills

- **`backend-core-architecture-contracts`** - Enforces architecture boundaries, repository DTO contracts, invariant discipline, and error taxonomy for defensive backends
- **`backend-defensive-engineering`** - Orchestrator for modular defensive backend engineering guidance in Node.js + TypeScript + Express projects
- **`backend-node-init-minimal`** - Initializes a minimal Node backend baseline with canonical directories, health endpoints, and lifecycle-safe entrypoint contracts
- **`backend-redis-application-patterns`** - Defines Redis behavior patterns at the backend application layer: locking, cache consistency, fallback, and operability
- **`backend-redis-infra-separation`** - Enforces clear boundaries and handoff between Redis application behavior guidance and Redis infrastructure operations
- **`backend-runtime-safety-lifecycle`** - Defines runtime lifecycle safety, health semantics, dependency criticality, and operational baseline for defensive backends

### DevOps Skills

- **`dockerization`** - Initiates a lightweight Docker setup via OpenSpec proposal to ensure stability and simple infrastructure

### Utility Skills

- **`find-skills`** - Helps users discover and install agent skills when they ask questions like "how do I do X", "find a skill for X", "is there a skill that can..."
- **`readme-blueprint-generator`** - Intelligent README.md generation that analyzes project documentation and creates comprehensive repository documentation

## Key Features

### Comprehensive Backend Engineering Support
- **Architecture Enforcement**: Automated checks for architectural boundaries and contracts
- **Defensive Programming**: Patterns and practices for building resilient backend systems
- **Technology-Specific Guidance**: Specialized patterns for Node.js, TypeScript, Express, Redis
- **Safety and Lifecycle Management**: Runtime safety patterns and dependency management

### DevOps Automation
- **Docker Integration**: Automated containerization setup
- **Infrastructure Management**: Patterns for infrastructure separation and operability

### Development Workflow Enhancements
- **Skill Discovery**: Automated skill search and recommendation
- **Documentation Generation**: Intelligent README and documentation creation
- **Code Exemplars**: Reference implementations and best practices

## Development Workflow

### Version Control Strategy
- **Branching**: Feature-based development with descriptive commit messages
- **Commit Convention**: `feat:`, `fix:`, `docs:`, `refactor:` prefixes
- **History**: Linear commit history with meaningful change descriptions

### Recent Development Activity
- `feat: added backend utility and init skills` - Added comprehensive backend skill collection
- `feat: added dockerization skill` - Introduced containerization automation
- `Initial commit` - Repository initialization

### Skill Contribution Process
1. Create new skill directory with descriptive name
2. Add SKILL.md with YAML frontmatter and detailed instructions
3. Follow existing skill structure and documentation patterns
4. Test skill functionality before submission
5. Commit with descriptive message following the convention

## Coding Standards

### Skill Definition Standards
- **YAML Frontmatter**: Required `name` and `description` fields
- **Markdown Formatting**: Clear headings, code blocks, and structured content
- **Documentation Quality**: Comprehensive yet concise instructions
- **Self-Contained**: Each skill must be independently functional

### File Organization
- **Directory Naming**: Kebab-case for skill directories (e.g., `backend-node-init-minimal`)
- **File Naming**: SKILL.md for primary skill definition
- **Documentation**: README.md for repository overview

## Testing

Skills are tested through:
- **Integration Testing**: Verification with OpenCode agent system
- **Documentation Review**: Ensuring clear, actionable instructions
- **Compatibility Testing**: Cross-platform functionality validation

## Contributing

### How to Contribute New Skills

1. **Fork the Repository**: Create your own fork for development
2. **Create a Feature Branch**: `git checkout -b feat/new-skill-name`
3. **Add New Skill Directory**: Create a new directory with descriptive name
4. **Write SKILL.md**: Follow the template with YAML frontmatter and detailed instructions
5. **Test Your Skill**: Verify functionality with OpenCode system
6. **Submit Pull Request**: Include comprehensive description of the skill's purpose

### Skill Development Guidelines

Refer to existing skills for examples of structure and content quality. The `readme-blueprint-generator` skill can help create consistent documentation formats.

### Reporting Issues

For bugs, feature requests, or improvements, please open an issue in the repository with detailed description and steps to reproduce.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Copyright (c) 2026 roe

---

## Additional Resources

- **OpenCode Documentation**: For information about the OpenCode agent system
- **Skill Development Guide**: For creating new OpenCode skills
- **Backend Engineering Best Practices**: Refer to the backend skill collection for guidance

*This README was generated using the readme-blueprint-generator skill as an example of the documentation capabilities within this repository.*
