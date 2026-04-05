# API / CLI Contract

This repository currently exposes one executable interface:

## Command
- `php hello-world.php`

## Expected Behavior
- Prints exactly one line: `Hello, world!`
- Ends with newline.
- Exit code should be `0` on success.

## Change Contract
- If output text changes, update `README.md`.
- If new command entrypoints are added, document:
  - command name
  - input parameters
  - expected output
  - failure behavior

