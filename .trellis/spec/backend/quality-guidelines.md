# Quality Guidelines

> Java backend code quality, formatting, task scope, and forbidden behavior.

---

## Coding Principles

- Code must be concise, readable, highly cohesive, and loosely coupled.
- Write clear comments where they are needed; explain key logic and non-obvious decisions.
- Keep style consistent across indentation, naming, and structure.
- Do not delete existing code logic unless the user explicitly requests removal; only optimize, enhance, or fix.
- Do not break existing behavior.

---

## Formatting and Encoding

- Indentation: 4 spaces.
- Maximum line length: 120 characters.
- Encoding: UTF-8.
- Line endings: LF.

---

## Required Work Styles

Allowed Java backend work scopes include:

- Code refactoring.
- Bug investigation and fixes.
- Performance optimization.
- Unit test additions.
- API documentation generation.
- Utility class implementation.
- Code review.

When implementing, change code directly with minimal unrelated discussion. Provide a concise modification summary after changes.

---

## Forbidden Behavior

- Do not delete files casually.
- Do not damage existing functionality.
- Do not output irrelevant content.
- Do not modify sensitive information in configuration files.
- Do not automatically execute `git push`.
- Do not casually add files or modify directory structure.
- Do not directly expose Entity objects through external interfaces.
- Do not use untyped `Map` objects for multi-condition queries.

---

## Testing Requirements

- Add or update unit tests when behavior changes, bugs are fixed, or important logic is refactored.
- Keep tests focused on the changed behavior.
- Run the relevant project checks when available.

---

## Code Review Checklist

Review Java backend changes for:

- Naming conventions and service method prefixes.
- Entity/DTO/VO boundaries and converter usage.
- Typed query objects instead of `Map`.
- Entity inheritance from `BaseEntity`.
- Boolean fields without `is` prefix.
- SQL safety and SQL style requirements.
- Formatting, encoding, and line endings.
- No unrelated deletion, no sensitive config changes, and no automatic push.
