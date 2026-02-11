# Agent Notes for tiliote-analyzer

This file documents how to work in this repository as an automated
coding agent. It is intentionally explicit and conservative.

## Repository Snapshot

- Only top-level files found: `README.md`, `.gitignore`.
- No build system files found (no `package.json`, `pyproject.toml`,
  `Cargo.toml`, `go.mod`, `Makefile`, etc.).
- No tests or lint configuration files discovered.
- No Cursor rules or Copilot rules present.

If the repository grows, update this file with concrete commands and
rules that match the actual tooling.

## Build / Lint / Test Commands

There are currently no build, lint, or test commands configured in the
repo. Do not invent commands. If you add tooling, document the exact
commands here.

Suggested discovery steps (non-destructive):

- Check for build/test configs when new files appear.
- Prefer documented scripts in `package.json`, `pyproject.toml`,
  `Makefile`, or similar.
- If multiple toolchains exist, list the recommended one first.

### Running a Single Test

No test runner is configured yet. When tests are added, document a
single-test command in this section using the tool's real syntax.

Example placeholders (do not run unless added):

- Node: `npm test -- <test-name-or-path>`
- Pytest: `pytest path/to/test_file.py -k test_name`
- Go: `go test ./path -run TestName`

### Dependency Management

- Record the chosen package manager and version once introduced.
- Prefer lockfiles committed to the repo (for reproducibility).
- Avoid adding dependencies unless the feature clearly requires them.

### Configuration and Environment

- Do not hardcode secrets, tokens, or credentials.
- Document required environment variables in `README.md`.
- Provide safe defaults for local development where possible.
- Keep configuration close to the code that consumes it.

## Code Style Guidelines

There is no code in this repository yet. The guidelines below are a
starting point for consistency once code is introduced. Prefer to
replace these with the actual style of the codebase.

### General Principles

- Keep changes minimal and aligned with existing patterns.
- Avoid speculative refactors or reformatting unrelated code.
- Prefer clear, small functions over large multipurpose ones.
- Use names that reveal intent; avoid abbreviations unless established.

### Formatting

- Follow the formatter adopted by the project once introduced.
- Keep line lengths reasonable for readability (80-120 characters
  depending on language norms).
- Avoid introducing non-ASCII characters unless already present.

### File Layout and Structure

- Keep related code near each other (feature-based grouping).
- Prefer shallow directory nesting until the project grows.
- Avoid dumping unrelated helpers into a single "utils" module.
- Add new top-level directories only with a clear rationale.

### Imports and Modules

- Group imports by standard library, third-party, then local.
- Sort imports alphabetically within each group.
- Avoid unused imports; remove them promptly.

### API and Interface Design

- Define clear boundaries between modules and layers.
- Prefer small, composable functions over global state.
- Keep public interfaces stable; version or deprecate carefully.
- Validate inputs at module boundaries.

### Types and Interfaces

- Prefer explicit types for public APIs and complex logic.
- Keep types local when possible; export only what is used externally.
- Use narrow types and avoid overly permissive `any`-like types.

### Naming Conventions

- Use descriptive nouns for data and verbs for actions.
- Match casing rules of the language (camelCase, snake_case, etc.).
- Avoid `temp`, `data`, `thing`, `stuff`-style names.

### Error Handling

- Return or propagate errors with context.
- Avoid swallowing errors; log or surface them appropriately.
- Prefer early returns/guards for invalid inputs.

### Logging and Diagnostics

- Log actionable context (operation, identifiers, and error details).
- Avoid logging secrets or large blobs of data.
- Use structured logs if the runtime supports them.

### Testing Expectations

- Add tests alongside new functionality once a test framework exists.
- Prefer deterministic tests; avoid timing-dependent assertions.
- Keep tests focused on behavior, not implementation detail.

### Performance and Reliability

- Prefer clear correctness over premature optimization.
- Avoid unnecessary I/O in hot paths.
- Handle retries or transient failures explicitly where relevant.

### Documentation

- Update `README.md` when new setup steps are introduced.
- Document non-obvious behavior in code or in module-level docs.

### Git Hygiene

- Keep commits focused and logically grouped.
- Do not commit generated artifacts unless required.
- Avoid sweeping renames or formatting unless requested.

## Cursor and Copilot Rules

- No Cursor rules found in `.cursor/rules/` or `.cursorrules`.
- No Copilot instructions found in `.github/copilot-instructions.md`.

If these files are added, summarize and include their guidance here.

## Notes for Agents

- The repository is effectively empty; avoid guessing conventions.
- Prefer to ask for clarification if you need to choose a toolchain.
- Keep changes tightly scoped and document any new tooling.
