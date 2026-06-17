---
description: "Create a new C# service and its technical Markdown documentation"
agent: "agent"
model: "GPT-5.4"
tools: ["search/codebase", "read/readFile", "edit/createFile"]
---
# C# Service + Markdown Document Generator

Your goal is to create a production-ready C# service and its technical
Markdown documentation.

If not specified, ask:

1. What functional domain does the service cover? (e.g., scoring, reporting, ingestion)
2. What inputs/outputs does the service need?
3. Should it be exposed through an API, internal use, or both?

## Expected structure

```text
docs/<project>/<service-name>.md
src/<Project>/Abstractions/I<ServiceName>.cs
src/<Project>/Services/<ServiceName>.cs
```

Must include:

1. **Interface** (`I<ServiceName>`) with clear contracts
2. **Implementation** with constructor-based dependency injection
3. **Async methods** with `CancellationToken`
4. **Input validation** and explicit error handling
5. **Markdown document** with objective, flow, contracts, and examples

## Conventions

- Follow [csharp.instructions.md](../instructions/csharp.instructions.md)
- Keep nullability enabled and use `?` where applicable
- The Markdown document must include: `## Context`, `## Design`, `## Examples`, `## References`
