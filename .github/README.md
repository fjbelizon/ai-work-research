# GitHub Copilot Customization — `.github/`

This folder contains all GitHub Copilot customization files for the **AI Work Research** project. Each subdirectory or file defines a specific mechanism that controls how Copilot understands the project, generates code, and automates tasks.

---

## `copilot-instructions.md` — Global instructions

**Activation:** automatic on every chat interaction.

Defines the baseline context Copilot applies to *all* conversations: project architecture, coding standards, naming conventions, and documentation references. It is the most important starting point, equivalent to the team's AI standards.

---

## `instructions/` — File-targeted instructions

**Activation:** automatic when the open file matches the `applyTo` pattern.

| File | Applies to | Purpose |
| ---- | ---------- | ------- |
| `csharp.instructions.md` | `**/*.cs`, `**/*.csproj`, `**/*.razor` | C# standards: naming, nullability, async/await, xUnit tests |

---

## `prompts/` — Reusable task templates

**Activation:** on demand by running `/prompt-name` in chat.

| File | Command | Purpose |
| ---- | ------- | ------- |
| `research-summary.prompt.md` | `/research-summary` | Generates a research executive summary in Markdown |
| `new-analysis-script.prompt.md` | `/new-analysis-script` | Creates a C# service and its technical Markdown documentation |

---

## `agents/` — Custom agents (chat modes)

**Activation:** the user selects the agent in the chat mode selector.

| File | Agent | Purpose |
| ---- | ----- | ------- |
| `planner.agent.md` | **Planner** | Generates detailed research plans without changing code. Includes a handoff to the default agent to implement the plan |
| `reviewer.agent.md` | **Reviewer** | Reviews C# code quality and Markdown documentation. Produces a severity report without applying automatic fixes |

---

## `skills/` — Agent skills (specialized capabilities)

**Activation:** automatic when Copilot detects the prompt is relevant to the skill.

| Directory | Skill | Purpose |
| --------- | ----- | ------- |
| `skills/data-analysis/` | `csharp-markdown-workflow` | Guide for creating C# services, contracts, xUnit tests, and technical Markdown docs |

Each skill follows a **progressive disclosure** model: only the name and description from `SKILL.md` are loaded initially; the full body and supporting resources are loaded only when the skill is relevant to the task.

---

## `hooks/` — Agent hooks (lifecycle automation)

**Activation:** automatic on configured lifecycle events.

| File | Events | Purpose |
| ---- | ------ | ------- |
| `quality-gates.json` | `PostToolUse`, `PreToolUse`, `SessionStart` | Formats C# files with `dotnet format` after edits; Blocks destructive commands before execution; Injects project context at session start |

---

## `workflows/` — Agentic workflows (GitHub Actions with AI)

**Activation:** via GitHub Actions triggers (issues, PRs, etc.).

| File | Trigger | Purpose |
| ---- | ------- | ------- |
| `issue-clarifier.md` | `issues: opened` | Analyzes new issues and requests missing details (research question, available data, success criteria) before labeling them `ready-for-research` |

Agentic workflows are compiled with `gh aw compile` to generate a `.lock.yml` workflow with all security safeguards applied.

---

## `plugin/` — Plugin marketplace configuration

| File | Purpose |
| ---- | ------- |
| `plugin/marketplace.json` | Defines the project's distributable plugin catalog. References plugins in `../plugins/` so they can be installed via `/plugins` in chat |

---

## Layered architecture

```text
Layer 1 — Always on       → copilot-instructions.md + instructions/
Layer 2 — On demand       → prompts/
Layer 3 — Session mode    → agents/
Layer 4 — Auto-activated  → skills/
Layer 5 — Events          → hooks/ + workflows/
Distribution              → plugin/
```

For more details on how context is assembled for each request, see the [GitHub Copilot Customization Handbook](https://copilot-academy.github.io/workshops/copilot-customization/copilot_customization_handbook).
