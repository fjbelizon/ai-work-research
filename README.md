# ai-work-research

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Research, analysis, and resources on the integration and impact of AI in the workplace.

## 📌 Overview

This repository combines two tracks:

- Research content about AI and work.
- A Copilot customization package that defines agents, prompts, hooks, and workflows.

The current implementation is focused on the Copilot customization layer. Product/business code
(`src/`, `tests/`) is still in planning.

## 📂 Repository structure

- `.githooks/` — local Git safeguards (for example, pre-push checks against direct pushes to protected branches).
- `.github/` — Copilot customization assets (instructions, prompts, agents, skills, hooks, workflows).
- `.vscode/` — local MCP server configuration.
- `docs/` — repository documentation.
- `plugins/` — plugin packaging manifest.

## ✅ Operational features

These parts are currently usable as-is:

1. Copilot project guidance through [.github/copilot-instructions.md](.github/copilot-instructions.md).
2. File-targeted C# coding standards through [.github/instructions/csharp.instructions.md](.github/instructions/csharp.instructions.md).
3. Reusable prompts in [.github/prompts](.github/prompts) for:
   - research executive summary generation.
   - C# service + Markdown documentation generation.
4. Custom chat agents in [.github/agents](.github/agents):
   - Planner (planning-first workflow).
   - Reviewer (C# + Markdown quality review).
5. Skill resources in [.github/skills/data-analysis](.github/skills/data-analysis) for C# service and documentation workflows.
6. Agent hooks in [.github/hooks/quality-gates.json](.github/hooks/quality-gates.json):
   - C# formatting with `dotnet format` after edits.
   - basic command safety gate.
   - session context injection.
7. Agentic workflow template in [.github/workflows/issue-clarifier.md](.github/workflows/issue-clarifier.md) for issue clarification.
8. Contribution governance assets from main:
   - [.githooks/pre-push](.githooks/pre-push) to prevent direct pushes to protected branches.
   - [CONTRIBUTING.md](CONTRIBUTING.md) and [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md) to standardize issue-linked contributions.
   - [.github/workflows/require-issue.yml](.github/workflows/require-issue.yml) to enforce linked issues in PR descriptions.

## 🧩 Skeletons that still need development

These parts are scaffolds and require implementation work to become fully operational:

1. Product code modules referenced in documentation (`src/`, `tests/`, `scripts/`, `tools/`, `examples/`) are not present yet.
2. Plugin package under [plugins/ai-research-tools](plugins/ai-research-tools) includes only `plugin.json`.
   - The manifest references `agents/`, `skills/`, `hooks.json`, and `.mcp.json` inside the plugin package, but those assets are not yet packaged there.
3. Agentic workflow execution pipeline is declarative only.
   - The `.md` workflow exists, but no compiled `.lock.yml` artifact is included yet.
4. Documentation in [docs/project-structure.md](docs/project-structure.md) describes a broader structure that is still planned, not implemented.

## 🛣️ Suggested next implementation steps

1. Add minimal `src/` and `tests/` C# projects to align codebase and documentation.
2. Package real plugin assets under `plugins/ai-research-tools/` (agents, skills, hooks, mcp config).
3. Compile and commit workflow lock files for agentic workflows.
4. Update `docs/project-structure.md` to reflect the actual repository state.

## 🚀 Topics

- AI in the workplace
- Human-AI collaboration
- C# engineering standards for AI-assisted development
- Copilot customization patterns (agents, prompts, skills, hooks, workflows)

## 🤝 Contributing

Contributions are welcome! If you have valuable insights, papers, or data to add:

1. Fork this repository.
2. Create a new branch (e.g., `git checkout -b feature/<issue-number>-short-description`).
3. Commit your changes in that branch.
4. Open a Pull Request.

Please follow the repository contribution policy in [CONTRIBUTING.md](CONTRIBUTING.md). Key rules:

- Every contribution must be linked to a GitHub issue. Open or identify the issue first, then create your branch.
- Direct commits to `main` are not allowed. The same rule applies to `master` if that branch is ever created or used.

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.
