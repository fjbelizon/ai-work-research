# Repository structure

This document describes the **current** repository layout and clarifies what is
already implemented versus what is still planned.

## Current implemented folders

- `.github/`: Copilot customization assets (instructions, prompts, agents, skills, hooks, and agentic workflows).
- `.vscode/`: local MCP configuration for workspace tooling.
- `docs/`: project documentation in Markdown.
- `plugins/`: plugin packaging assets for Copilot distribution.

## Current top-level files

- `README.md`: project overview, feature status, and contribution entry point.
- `LICENSE`: repository license.
- `.gitignore`: Git ignore rules.

## Planned folders (not implemented yet)

The following folders are part of the target architecture, but are not present
in the repository at this time:

- `src/`: application and domain source code.
- `tests/`: unit and integration tests.
- `scripts/`: automation scripts.
- `tools/`: auxiliary tooling.
- `examples/`: runnable examples and sample assets.

## Notes

- The repository is currently focused on Copilot customization and documentation.
- Product/business implementation folders should be created as part of the next development phase.
