# Usage Guide - Generate Claude Files Skill

## Quick Start

### 1. Basic Usage

```bash
cd /path/to/your/project

bash /path/to/generate-claude-files/scripts/generate-all.sh .
```

This generates:
- `CLAUDE.md` - Project rules
- `CODEMAP.md` - Architecture map
- `MEMORY.md` - Project context

### 2. Custom Output Directory

```bash
bash /path/to/generate-claude-files/scripts/generate-all.sh /my/project /my/docs
```

Generates files in `/my/docs/` instead of current directory.

---

## What Gets Generated

### CLAUDE.md
- Tech stack detected from package.json
- Code quality rules specific to your framework
- Error handling patterns
- Testing requirements
- Security checklist
- Pre-commit checklist

### CODEMAP.md
- Directory structure with explanations
- Key file purposes
- Request/response flow diagrams
- How to navigate the codebase
- Quick reference tables

### MEMORY.md
- Quick facts about the project
- Architecture overview
- Important conventions
- Known gotchas (template)
- Performance notes (template)
- Security checkpoints

---

## Customization

After generation, customize the files:

**CLAUDE.md**: Update rules specific to your team/company
**CODEMAP.md**: Add business logic explanations
**MEMORY.md**: Add real gotchas you discover

---

## Integration with Claude

Use in your Claude requests:

```
## Task: Add user authentication

See:
- CLAUDE.md (section: Security)
- CODEMAP.md (section: Middleware)
- MEMORY.md (section: Conventions)

When I ask this, Claude understands your project structure instantly!
```

---

## Supported Tech Stacks

- Express, Fastify, NestJS
- PostgreSQL, MySQL, MongoDB, SQLite
- Jest, Vitest, Mocha
- TypeScript + JavaScript

---

## Examples

### Express + PostgreSQL + Jest

Files will include Express-specific patterns, PostgreSQL connection management, Jest testing setup.

### NestJS + MongoDB + Vitest

Files will include NestJS decorators, MongoDB patterns, Vitest configuration.

### Microservices

CODEMAP.md will show inter-service communication, shared middleware, API gateway patterns.

---

## Troubleshooting

### "Python command not found"
- Install Python 3: `brew install python3`
- Or use: `python3 generate-all.sh` instead of `python`

### "Repository analysis failed"
- Ensure path is correct: `bash generate-all.sh /correct/path`
- Ensure it's a Node.js project with package.json

### Files not being created
- Check output directory exists: `mkdir -p /output/dir`
- Ensure write permissions: `ls -la /output/dir`

---

## Next Steps

1. Run: `bash generate-all.sh /path/to/project`
2. Review the generated files
3. Customize as needed
4. Commit to git: `git add CLAUDE.md CODEMAP.md MEMORY.md`
5. Use in Claude requests!
