---
description: "Generate a research executive summary from notes and evidence"
agent: "agent"
model: "GPT-5.4"
tools: ["search/codebase", "web/fetch", "web/githubRepo"]
---
# Research Executive Summary Generator

Your goal is to produce a Markdown executive summary for research about the impact of AI on work.

If the topic is not specified, ask: What use case or sector does this research cover?

## Document requirements

- Start with a `# Executive Summary: <Topic>` heading
- Include the required sections in this order:
  1. **Context** — problem statement or research question
  2. **Key Findings** — comparison table with key metrics
  3. **Implications** — expected impact on roles and processes
  4. **Recommendations** — concrete, prioritized actions
  5. **References** — sources cited in APA format

## Conventions

- Use English headings and standard technical terminology
- Use tables instead of nested lists for comparisons
- Length: maximum 800 words
- Review [copilot-instructions.md](../copilot-instructions.md) to ensure compliance with project standards
