# Architecture

## Current Structure
- `hello-world.php`: single runnable PHP demo script.
- `README.md`: project overview and run instructions.
- `harness_engineering.md`: concept notes and implementation playbooks.

## Design Principles
- Keep the repository intentionally small for learning.
- Prefer explicit files over hidden conventions.
- Document process so humans and agents can follow the same workflow.

## Layering (Current)
- Runtime layer: `hello-world.php`
- Knowledge layer: `README.md`, `harness_engineering.md`, `docs/`
- Execution policy layer: `AGENTS.md`, `plans/`

## Future Extension (Optional)
- If adding more PHP scripts, place them under `scripts/`.
- If adding tests, place them under `tests/` with clear run commands in `README.md`.

