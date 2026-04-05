# AGENTS.md

## Purpose
- This repository is a Git-learning sandbox and a minimal PHP demo.
- Keep all changes small, explicit, and easy to review.

## Scope
- In-scope: `hello-world.php`, `README.md`, `harness_engineering.md`, and files under `docs/` and `plans/`.
- Out-of-scope: large framework scaffolding, dependency installation, or unrelated refactors.

## Coding Rules
- PHP code must use `declare(strict_types=1);`.
- Keep scripts simple and readable; avoid unnecessary abstractions.
- Do not add dependencies unless explicitly requested.
- Do not rename files unless explicitly requested.

## Documentation Rules
- Any behavior change must update `README.md`.
- Process or concept changes must update `harness_engineering.md`.
- New workflows should be documented under `docs/`.

## Task Execution Contract
1. Restate task goal and assumptions briefly.
2. Propose minimal file-level plan.
3. Implement only requested changes.
4. Provide changed file list and validation notes.

## Validation
- For PHP script changes, run:
  - `php -l hello-world.php`
  - `php hello-world.php`
- For docs-only changes, no runtime validation required.

## Git & Commit
- Use concise, conventional commit style:
  - `docs: ...`
  - `feat: ...`
  - `fix: ...`
- Commit message must reflect actual diff content.

## Safety
- Do not run destructive commands (`rm`, reset history) unless user requests them.
- Do not modify secrets, credentials, or global system config.

