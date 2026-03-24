# AGENTS.md

This is a profile repository for xavier2code. It contains no actual project code with build/test infrastructure.

## General Build/Lint/Test Commands

Since this repo has no project code, use these standard commands for the languages present:

### Python
```bash
# Install dependencies
pip install -r requirements.txt

# Run tests
pytest

# Run a single test
pytest tests/test_file.py::test_function_name

# Lint
ruff check .
black .
mypy .
```

### Java/Gradle
```bash
# Build
./gradlew build

# Run tests
./gradlew test

# Run a single test
./gradlew test --tests "com.example.TestClass.testMethod"

# Lint (Checkstyle)
./gradlew checkstyleMain
```

### TypeScript/Node.js
```bash
# Install dependencies
npm install

# Build
npm run build

# Run tests
npm test

# Run a single test
npm test -- --testPathPattern="test_file" --testNamePattern="test_function"

# Lint
npm run lint
npm run lint:fix

# Type check
npm run typecheck
```

### Go
```bash
# Build
go build ./...

# Run tests
go test ./...

# Run a single test
go test -run TestFunction ./...

# Lint
golangci-lint run
```

### Rust
```bash
# Build
cargo build

# Run tests
cargo test

# Run a single test
cargo test test_function_name

# Lint
cargo clippy
cargo fmt --check
```

---

## Code Style Guidelines

### General Principles
- Write clear, concise code with descriptive names
- Follow the principle of least surprise
- Keep functions small and focused (single responsibility)
- Avoid premature optimization
- Document complex logic with comments

### TypeScript
- Use strict mode (`"strict": true` in tsconfig)
- Prefer interfaces over type aliases for object shapes
- Use `unknown` instead of `any` when type is uncertain
- Use optional chaining (`?.`) and nullish coalescing (`??`)
- Prefer `const` over `let`, avoid `var`
- Use arrow functions for callbacks
- Use named exports over default exports

### Python
- Follow PEP 8
- Use type hints (PEP 484)
- Use `ruff` for linting and formatting
- Use list/dict comprehensions when appropriate
- Use dataclasses or Pydantic for data structures
- Handle exceptions with specific exception types

### Java
- Follow Oracle/Java style guides
- Use streams and lambdas where appropriate
- Prefer immutable objects
- Use checked exceptions sparingly
- Follow dependency injection patterns

### Go
- Follow `gofmt` formatting
- Use `golangci-lint` for linting
- Error handling: wrap errors with context
- Use interfaces for abstraction
- Avoid global variables

### Rust
- Follow `cargo fmt` formatting
- Use `clippy` for linting
- Prefer `Result` over `panic` for error handling
- Use pattern matching exhaustively
- Write doc comments for public APIs

### Naming Conventions
- **Files**: kebab-case (`my-file.ts`) or snake_case (`my_file.py`)
- **Classes**: PascalCase (`MyClass`)
- **Functions/Methods**: camelCase (`myFunction`) or snake_case (`my_function`)
- **Constants**: SCREAMING_SNAKE_CASE
- **Variables**: descriptive, avoid single letters except loops
- **Types/Interfaces**: PascalCase (`MyType`, `IMyInterface`)

### Error Handling
- Never swallow exceptions without logging
- Use specific exception types
- Include context in error messages
- Fail fast on invalid state
- Return errors as values when idiomatic (Go, Rust)

### Imports
- Order: stdlib → third-party → local
- Group by type (types, functions, constants)
- Use alias when names conflict
- Avoid circular imports

### Comments
- Document public APIs
- Explain "why" not "what"
- Keep comments updated with code
- TODO/FIXME should include author or issue reference

---

## Git Workflow
- Commit messages: imperative mood, first line < 50 chars
- Branch naming: `feature/`, `fix/`, `chore/`
- Pull requests: descriptive title and body
- Never commit secrets or credentials
- Run lint and tests before committing

## Tooling
- Editor: Neovim (configured with LSP, treesitter, etc.)
- Terminal: Linux shell environment
- Version control: Git
