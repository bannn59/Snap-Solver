# Repository Guidelines

## Project Structure & Module Organization
Snap-Solver is a Flask web app served from `app.py`, which wires Socket.IO streaming, screenshot capture, and model dispatch. Model adapters live in `models/`, with `factory.py` loading provider metadata from `config/models.json` and creating the appropriate client (OpenAI, Anthropic, DeepSeek, Qwen, etc.). User-facing templates live under `templates/`, with shared assets in `static/`. Runtime configuration and secrets are JSON files in `config/`; treat these as local-only overrides even if sample values exist in the repo. Python dependencies are listed in `requirements.txt` (lockfile: `uv.lock`).

## Build, Test, and Development Commands
- `python -m venv .venv && source .venv/bin/activate` sets up an isolated environment.
- `pip install -r requirements.txt` or `uv sync` installs Flask, provider SDKs, and Socket.IO.
- `python app.py` boots the development server at `http://localhost:5000` with verbose engine logs.
- `FLASK_ENV=development python app.py` enables auto-reload during active development.

## Coding Style & Naming Conventions
Follow PEP 8: 4-space indentation, `snake_case` for Python functions, and descriptive class names that match provider roles (see `models/openai.py`). JSON configs use lowerCamelCase keys so the web client can consume them directly; keep that convention when adding settings. Client scripts in `static/js/` should stay modular and avoid sprawling event handlers.

## Testing Guidelines
There is no automated test suite yet; whenever you add features, verify end-to-end by launching `python app.py`, triggering a screenshot from the UI, and confirming Socket.IO events stream without tracebacks. When integrating a new model, seed a temporary key in `config/api_keys.json`, exercise one request, and capture console logs before reverting secrets. If you introduce automated tests, place them in `tests/` and gate external calls behind mocks so the suite can run offline.

## Commit & Pull Request Guidelines
The history favors concise, imperative commit subjects in Chinese (e.g., `修复发送按钮保存裁剪框数据`). Keep messages under 70 characters, enumerate multi-part changes in the body, and reference related issues with `#123` when applicable. Pull requests should outline the user-visible impact, note any config updates or new dependencies, attach UI screenshots for front-end tweaks, and list manual verification steps so reviewers can reproduce them quickly.

## Configuration & Security Tips
Never commit real API keys—`.gitignore` already excludes `config/api_keys.json` and other volatile files, so create local copies (`config/api_keys.local.json`) for experimentation. When sharing deployment instructions, direct operators to set API credentials via environment variables or secure vaults and only populate JSON stubs during runtime startup logic.
<!-- TRELLIS:START -->
# Trellis Instructions

These instructions are for AI assistants working in this project.

This project is managed by Trellis. The working knowledge you need lives under `.trellis/`:

- `.trellis/workflow.md` — development phases, when to create tasks, skill routing
- `.trellis/spec/` — package- and layer-scoped coding guidelines (read before writing code in a given layer)
- `.trellis/workspace/` — per-developer journals and session traces
- `.trellis/tasks/` — active and archived tasks (PRDs, research, jsonl context)

If a Trellis command is available on your platform (e.g. `/trellis:finish-work`, `/trellis:continue`), prefer it over manual steps. Not every platform exposes every command.

If you're using Codex or another agent-capable tool, additional project-scoped helpers may live in:
- `.agents/skills/` — reusable Trellis skills
- `.codex/agents/` — optional custom subagents

Managed by Trellis. Edits outside this block are preserved; edits inside may be overwritten by a future `trellis update`.

<!-- TRELLIS:END -->
