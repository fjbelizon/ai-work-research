---
applyTo: "**/*.cs,**/*.csproj
---
# C# Code Standards

## Style and formatting

- Follow Microsoft naming conventions: `PascalCase` for types, methods, and properties; `camelCase` for local variables and parameters; `_` prefix for private fields (`_myField`)
- Maximum line length is 120 characters; format with `dotnet format` (EditorConfig)
- Use `var` only when the type is obvious on the same line; otherwise use explicit types

## Types and nullability

- Enable `<Nullable>enable</Nullable>` in all projects
- Explicitly annotate nullable reference types with `?` where null is allowed
- Prefer `record` for immutable data types and DTOs
- Use `required` for mandatory properties in `record` and `class`

## Design patterns

- Apply the Repository pattern for data access and expose interfaces (`IRepository<T>`)
- Use constructor-based dependency injection; avoid Service Locator
- Use `IOptions<T>` for strongly typed configuration
- Prefer `Result<T>` or `OneOf` over exceptions for expected control-flow outcomes

## Async/Await

- All I/O methods should be `async Task` or `async Task<T>`; never use `async void` except for event handlers
- Use `ConfigureAwait(false)` in class libraries; omit it in ASP.NET Core applications
- Pass `CancellationToken` to all async methods that support it

## Documentation

- Document public types and members with XML docs using `/// <summary>`
- Include `/// <param>`, `/// <returns>`, and `/// <exception>` when useful
- Do not document the obvious; prefer clear naming over excessive comments

## Tests
- Name tests with the pattern `UnitOrMethod_Scenario_ExpectedResult`
- Use xUnit; organize with `[Fact]` for single cases and `[Theory]` + `[InlineData]` for parameterized cases
- Follow Arrange / Act / Assert, with section comments when tests exceed 10 lines
- Place test projects under `tests/<ProjectName>.Tests/`

## File organization

- One primary type per file; the filename must match the type name
- Order members as: 1. Fields; 2. Constructors; 3. Properties; 4. Public static methods; 5. Public methods; 6. Protected static methods; 7. Protected methods; 8. Private static methods; 9. Private methods
- Group `using` directives as: `System.*`, third-party packages, project namespaces; remove unused usings
