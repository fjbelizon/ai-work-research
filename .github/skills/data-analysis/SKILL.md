---
name: csharp-markdown-workflow
description: >
  Guide for creating C# services and technical Markdown documentation for the
  project. Use it when you need to design contracts, implement business logic,
  write tests, and produce operational docs.
---
# C# Development + Markdown Documentation

## When to use this skill

- Create a new domain service in C#
- Define interfaces and contracts across layers
- Add unit tests with xUnit
- Write or update technical Markdown documentation

## Standard workflow

1. **Contract design** — define `I<Service>` with async methods and `CancellationToken`
2. **Implementation** — apply constructor DI and explicit error handling
3. **Tests** — cover key scenarios with xUnit (`Fact`/`Theory`)
4. **Markdown documentation** — describe context, design, decisions, and examples
5. **Verification** — confirm consistency across code, tests, and docs

## Implementation conventions

- Enable nullability (`<Nullable>enable</Nullable>`) in C# projects
- Use `record` for immutable DTOs and `required` for mandatory properties
- Avoid `async void` outside event handlers
- For documentation, use stable headings and executable examples

## Reference resources

- Service template: [csharp-service-template.md](./csharp-service-template.md)
- Spec example: [examples/feature-spec-example.md](./examples/feature-spec-example.md)
