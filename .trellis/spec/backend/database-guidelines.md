# Database Guidelines

> Java backend POJO, entity, query, and SQL rules.

---

## POJO and Entity Rules

- Boolean fields must not use the `is` prefix to avoid RPC serialization issues.
- Every entity must inherit from `BaseEntity`.
- `BaseEntity` must provide `id`, `createdTime`, and `modifiedTime`.
- Do not expose Entity objects directly through external interfaces; convert through converter classes.

---

## Query Patterns

- Encapsulate multi-condition queries in typed query objects.
- Avoid using `Map` for query parameters.
- Use clear DTO/query classes for internal data transfer and query boundaries.

---

## SQL Requirements

- Do not use `select *`; explicitly list required columns.
- Use `#{}` for parameters.
- Do not use `${}` for SQL parameters.
- Do not join more than 3 tables in a single query.
- Do not use foreign keys.
- Do not use stored procedures.

---

## Sensitive Configuration

Do not modify sensitive information in configuration files unless the user explicitly requests it and the change is necessary for the task.
