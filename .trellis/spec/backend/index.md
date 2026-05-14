# Java Backend Development Guidelines

> Global default conventions for Java backend development in Trellis-generated projects.

---

## Scope

These rules apply whenever developing Java backend code.

Project-local `.trellis/spec/` files and clearly established codebase conventions take precedence over this global default when they are more specific.

---

## Guidelines Index

| Guide | Description | Status |
|-------|-------------|--------|
| [Directory Structure](./directory-structure.md) | Java package layering, object boundaries, converters, naming | Filled |
| [Database Guidelines](./database-guidelines.md) | POJO/entity rules, query objects, SQL restrictions | Filled |
| [Error Handling](./error-handling.md) | Error types, handling strategies | Project-specific |
| [Quality Guidelines](./quality-guidelines.md) | Formatting, coding principles, work scope, forbidden behavior | Filled |
| [Logging Guidelines](./logging-guidelines.md) | Structured logging, log levels | Project-specific |

---

## Pre-Development Checklist

Before changing Java backend code:

1. Confirm the task scope: refactor, bug fix, performance optimization, unit test, API docs, utility class, or code review.
2. Preserve existing behavior unless the task explicitly asks for a behavior change.
3. Follow object boundaries: do not expose Entity objects directly through external interfaces.
4. Use existing directory structure and project style; do not casually create files or change directories.
5. Warn before risky changes, especially config changes, sensitive information, or irreversible operations.

---

## Quality Check

Before handoff, verify:

- Naming follows Java conventions and service method prefixes.
- Entity, DTO, VO, query object, and converter boundaries are respected.
- SQL does not use forbidden patterns such as `select *`, `${}`, excessive joins, foreign keys, or stored procedures.
- Formatting uses 4 spaces, line length stays within 120 characters, files are UTF-8 with LF line endings.
- No existing logic was deleted accidentally, no sensitive config was changed, and no `git push` was executed automatically.
