# Feature-Driven Development

A specification and rules framework for AI coding agents to follow a structured, feature-driven development workflow.

## Overview

This project provides a comprehensive set of rules and guidelines for AI agents (like Claude, GPT, etc.) to follow when assisting with software development. It enforces a feature-driven approach where tasks are clearly defined, documented, and tracked through a structured workflow.

## Purpose

The Feature-Driven Development rules ensure that:
- Every task is properly refined and documented before implementation
- Features are self-descriptive and well-organized
- Code changes are accompanied by documentation and API references
- Developers can easily search and review implementations
- Project context is maintained through structured feature files

## Quick Start

### Setting Up the Agent

To enable an AI agent to follow these rules, include the `AGENTS.md` file in your AI assistant's context. The agent will automatically reference the `feature-driven-development-rules.md` file.

When the agent starts working, it should respond with:
> "I am your feature-driven code developer"

This confirms it has read and understood the rules.

### Basic Usage

The framework defines several commands to interact with the AI agent:

#### `task xxx`
Start a new task by referencing a prompt file in `prompts/xxx.md`.

**Workflow:**
1. Agent refines the task and creates `features/yyy-zzz.md` for review
2. After user confirmation, implementation begins
3. Upon completion, agent creates:
   - `features/docs/yyy-zzz.md` - Developer documentation
   - `features/apis/yyy-zzz.md` - API reference
4. User confirms final documentation to complete the task

#### `complete yyy-zzz`
Complete the implementation for an existing feature defined in `features/yyy-zzz.md`.

#### `refer yyy-zzz`
Reference an existing feature specification, reading the associated documentation and API files.

#### `review yyy-zzz`
Perform a code review for a feature using its specification, documentation, and API files.

#### `search xxx`
Instruct the agent to search the internet for solutions.

#### `do`
Process the currently opened markdown file in your IDE (interprets as either `task` or `complete` based on the file location).

## File Structure

```
project-root/
├── prompts/           # Task prompt files
│   └── xxx.md         # Initial task descriptions
├── features/          # Feature specifications and documentation
│   ├── readme.md      # Project overview and feature index
│   ├── yyy-zzz.md     # Feature specification
│   ├── docs/          # Feature documentation
│   │   └── yyy-zzz.md # Implementation details, file paths, functions
│   └── apis/          # API documentation
│       └── yyy-zzz.md # Interface definitions and references
├── AGENTS.md          # Agent prompt configuration
└── feature-driven-development-rules.md  # Core rules
```

## Naming Conventions

Feature names (`yyy-zzz`) should be:
- Short and self-descriptive
- Focused on the feature itself, not the action
- **Avoid** words like: `issue`, `add`, `update`, `bugfix`, `refactor`, `ticket`

**Good Examples:**
- `user-authentication`
- `payment-gateway`
- `real-time-notifications`

**Bad Examples:**
- `add-login-feature`
- `fix-payment-bug`
- `update-notifications`

## Documentation Standards

### Feature Specification (`features/yyy-zzz.md`)
- Define the feature scope and requirements
- Outline implementation approach
- Only updated when explicitly requested by the user

### Documentation File (`features/docs/yyy-zzz.md`)
- Written for other developers
- Include file paths, function names, and keywords for code search
- **Do not** use line numbers as references (they change)
- Updated after code reviews when fixes are confirmed

### API File (`features/apis/yyy-zzz.md`)
- Define interfaces for internal or external development
- Follow standard API documentation conventions
- Serve as package/module reference
- Updated alongside documentation when confirmed

## Workflow Rules

### Task Splitting
Large tasks should be split into subtasks:
1. Create separate feature files for each subtask
2. Complete subtasks one by one
3. Get user confirmation after each subtask completion

### Updating vs Creating Features
Not every task requires a new feature file. Consider:
- Can this update an existing feature?
- Is this a bug fix for an existing feature?
- Does this enhance current functionality?

**Always ask the user to confirm** before creating or updating feature files.

### Synchronization
When fixing bugs or updating code:
- Update the related `features/yyy-zzz.md` (if needed)
- Update `features/docs/yyy-zzz.md`
- Update `features/apis/yyy-zzz.md`
- Keep all documentation synchronized with the code

### Memory Management
The `features/readme.md` file serves as a memory aid:
- Lists all feature files under `features/`
- Provides general project information
- Should be concise yet informative
- Agent should periodically read and update it

## Best Practices

### Core Guidelines

1. **Start Small**: Begin with the smallest possible feature and grow incrementally
2. **Understand Everything**: Review and understand every line before proceeding to the next feature
3. **Avoid Big Features**: Never write large features all at once - split them into smaller pieces
4. **No Errors ≠ Correct Code**: Working features don't guarantee correct implementation - you must understand the code deeply

### Documentation Rules

5. **Test Cases**: Do not include test cases in `features/**/*.md` unless explicitly asked
6. **External References**: Do not reference external files in feature documentation; extract and include relevant content
7. **Source Code Only**: Reference only actual source code or files under `features/`
8. **Confirmation**: Always get user confirmation before creating/updating feature files
9. **Context**: The agent should maintain full project context by periodically reading `features/readme.md`

For comprehensive guidance on incremental development, code understanding, and quality practices, see [BEST_PRACTICES.md](BEST_PRACTICES.md).

## Example Workflow

```bash
# User starts a new task
User: task user-login

# Agent refines and creates feature specification
Agent: [Creates features/user-authentication.md]
Agent: "Here's the refined feature specification. Please review."

# User confirms
User: "Looks good, proceed"

# Agent implements the feature
Agent: [Implements code]

# Agent creates documentation
Agent: [Creates features/docs/user-authentication.md]
Agent: [Creates features/apis/user-authentication.md]
Agent: "Implementation complete. Please review the documentation."

# User confirms
User: "Approved"

# Later, user needs to review
User: review user-authentication
Agent: [Analyzes code against documentation]
```

## Integration

### Claude Code
Add `AGENTS.md` to your Claude Code context files.

### Custom AI Agents
Include the rules file in your agent's system prompt:
```
You are a feature driven code developer.
@feature-driven-development-rules.md
```

### IDE Integration
Open relevant feature files in your IDE when using the `do` command for context-aware processing.

## Contributing

Contributions are welcome! Please ensure any modifications to the rules maintain:
- Clarity and simplicity
- Structured workflow
- Comprehensive documentation requirements

## License

MIT License - Copyright (c) 2025 X School Academy

See [LICENSE](LICENSE) for full details.

## Resources

- [AGENTS.md](AGENTS.md) - Agent prompt configuration
- [feature-driven-development-rules.md](feature-driven-development-rules.md) - Complete rule specification
- [BEST_PRACTICES.md](BEST_PRACTICES.md) - Comprehensive best practices guide for incremental development and code understanding
