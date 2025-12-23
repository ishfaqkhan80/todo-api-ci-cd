# Software Development Best Practices

## Project Context
This document outlines development standards and practices for this project to ensure code quality, maintainability, and efficient token usage during AI-assisted development.

## Core Principles

### Code Quality
- Write clean, readable, and self-documenting code
- Follow language-specific conventions and style guides
- Keep functions small and focused (single responsibility)
- Use meaningful variable and function names
- Avoid premature optimization

### Token Efficiency
- Read only necessary files - use targeted searches instead of reading entire directories
- Reference specific functions/lines with `file:line` notation
- Keep responses concise and focused on the task
- Avoid repeating large code blocks unnecessarily
- Use diffs and edits instead of rewriting entire files

### Dependencies & Libraries
- Prefer industry-standard, well-maintained libraries
- Minimize dependency count - only add when truly needed
- Document why each major dependency was chosen
- Keep dependencies updated for security and stability

## Language-Specific Standards

### JavaScript/TypeScript
- Use TypeScript for type safety when possible
- ESLint + Prettier for consistent formatting
- Standard libraries: lodash, date-fns, axios/fetch
- Testing: Jest, Vitest, or similar
- Avoid `any` types - use proper typing

### Python
- Follow PEP 8 style guide
- Use type hints (PEP 484)
- Virtual environments (venv/poetry/pipenv)
- Standard libraries: requests, pandas, numpy where appropriate
- Testing: pytest
- Linting: ruff or pylint

### Go
- Follow official Go style guidelines
- Use `gofmt` for formatting
- Standard library first, external packages when needed
- Testing: built-in testing package
- Error handling: explicit error returns

## File Organization

```
project/
├── src/           # Source code
├── tests/         # Test files
├── docs/          # Documentation
├── config/        # Configuration files
├── scripts/       # Build/utility scripts
└── README.md      # Project overview
```

## Git & Version Control
- Write clear, descriptive commit messages
- Use conventional commits format when appropriate
- Keep commits atomic and focused
- Branch naming: `feature/`, `fix/`, `refactor/`
- Don't commit secrets, credentials, or large binary files

## Testing
- Write tests for critical business logic
- Aim for meaningful coverage, not just high percentages
- Unit tests for isolated functionality
- Integration tests for component interactions
- Keep tests maintainable and readable

## Security
- Validate all user input
- Use parameterized queries (prevent SQL injection)
- Sanitize output (prevent XSS)
- Keep dependencies updated
- Don't hardcode secrets - use environment variables
- Follow OWASP Top 10 guidelines

## Documentation
- README with setup instructions and project overview
- Inline comments only where logic isn't obvious
- Document public APIs and interfaces
- Keep documentation close to code
- Use JSDoc/docstrings for public functions when beneficial

## Performance
- Don't optimize prematurely
- Profile before optimizing
- Consider Big O complexity for algorithms
- Use appropriate data structures
- Cache expensive operations when sensible

## Common Patterns to Follow
- Dependency injection for testability
- Factory pattern for object creation
- Repository pattern for data access
- Middleware for cross-cutting concerns
- Environment-based configuration

## Common Anti-Patterns to Avoid
- God objects/functions
- Magic numbers and strings
- Deep nesting (> 3-4 levels)
- Global state
- Tight coupling
- Copy-paste code duplication

## Industry Standard Libraries by Use Case

### Web Frameworks
- **Node.js**: Express, Fastify, NestJS
- **Python**: FastAPI, Flask, Django
- **Go**: Gin, Echo, Chi

### Database
- **ORMs**: TypeORM, Sequelize (JS), SQLAlchemy (Python), GORM (Go)
- **Query Builders**: Knex.js, QueryBuilder
- **Drivers**: pg, mysql2, mongodb

### Authentication
- **JWT**: jsonwebtoken, PyJWT
- **OAuth**: Passport.js, Authlib
- **Session**: express-session, flask-session

### Validation
- **JS/TS**: Zod, Yup, Joi
- **Python**: Pydantic, Marshmallow
- **Go**: validator/v10

### Logging
- **JS**: Winston, Pino
- **Python**: logging (stdlib), loguru
- **Go**: zap, zerolog

### Testing
- **JS/TS**: Jest, Vitest, Mocha, Chai
- **Python**: pytest, unittest
- **Go**: testing (stdlib), testify

## AI-Assisted Development Notes
- Provide context about what you're trying to achieve
- Share relevant error messages and stack traces
- Indicate which files are most relevant to the task
- Ask for explanations when code isn't clear
- Request specific file ranges for large files

## Review Checklist
Before considering code complete:
- [ ] Code follows project style guidelines
- [ ] Tests are written and passing
- [ ] No console.log/print statements left in production code
- [ ] Error handling is appropriate
- [ ] No security vulnerabilities introduced
- [ ] Documentation updated if needed
- [ ] No unnecessary dependencies added
- [ ] Performance is acceptable

## Resources
- Language-specific style guides (PEP 8, Airbnb JS Style Guide, etc.)
- OWASP Security Guidelines
- 12 Factor App Methodology
- Semantic Versioning (semver.org)

---

**Note**: This is a living document. Update as project needs evolve and new patterns emerge.

## CI/CD Setup Complete
Our first GitHub Actions workflow is now active!