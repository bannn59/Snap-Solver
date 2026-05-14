# Logging Guidelines

> Project-specific Java backend logging conventions.

---

## Overview

Follow the target project's existing logging style unless a project-local Trellis spec says otherwise.

When adding or changing logs:

- Use the project's existing logging library and format.
- Log key business and failure events when useful for diagnosis.
- Do not log secrets, credentials, tokens, or sensitive configuration values.
- Avoid noisy or irrelevant logs.

---

## To Customize Per Project

Document the project's concrete rules here after `trellis init` if the project has specific conventions for:

- Log levels.
- Required structured fields.
- Request tracing identifiers.
- Sensitive data handling.
