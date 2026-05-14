# Directory Structure

> Java backend package organization, naming, and object boundary rules.

---

## Object Boundaries

Use the following object layers consistently:

- External API/interface objects: `client.vo`
- Internal objects: `domain.entity` and DTOs
- Persistence objects: `domain.entity`
- Transfer objects: DTOs
- View/response objects: VOs
- Conversion logic: converter classes only

Never expose Entity objects directly from external interfaces. Convert Entity/DTO/VO objects through a converter.

---

## Query Objects

For multi-condition queries, define a query object instead of passing a `Map`.

Do not use `Map` as an unstructured replacement for a typed request/query object.

---

## Naming Conventions

- Class names: `UpperCamelCase`.
- Class suffixes such as `DO`, `DTO`, and `VO` are allowed when they match the object role.
- Method names and field names: `lowerCamelCase`.
- Service method prefixes:
  - `get` for a single object.
  - `list` for multiple objects.
  - `count` for counts.
  - `save` or `insert` for creation.
  - `remove` or `delete` for deletion.
  - `update` for updates.

---

## Directory and File Changes

- Keep the existing project directory structure and naming style.
- Do not casually add new files or modify directory structure.
- Prefer editing existing classes when the existing structure already has the right place for the change.
- If a new file or directory is necessary, keep it aligned with the established package layering.
