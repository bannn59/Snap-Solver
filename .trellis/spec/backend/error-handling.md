# Error Handling

> Project-specific Java backend error handling conventions.

---

## Overview

Follow the target project's existing error handling style unless a project-local Trellis spec says otherwise.

When adding or changing error handling:

- Keep error behavior compatible with existing API contracts.
- Do not swallow exceptions silently.
- Preserve existing logging and response patterns unless the task explicitly asks to change them.
- Explain key non-obvious error handling logic with a clear comment.

---

## To Customize Per Project

Document the project's concrete rules here after `trellis init` if the project has specific conventions for:

- Error types.
- Exception propagation.
- API error response format.
- Logging requirements for failures.
