# C# Service Template

## Objective
Describe the business problem this service solves.

## Contract

```csharp
public interface IExampleService
{
    Task<Result<ExampleResponse>> ExecuteAsync(ExampleRequest request, CancellationToken cancellationToken);
}
```

## Implementation (skeleton)

```csharp
public sealed class ExampleService : IExampleService
{
    private readonly IExampleRepository _repository;

    public ExampleService(IExampleRepository repository)
    {
        _repository = repository;
    }

    public async Task<Result<ExampleResponse>> ExecuteAsync(
        ExampleRequest request,
        CancellationToken cancellationToken)
    {
        // Input validation
        // Business logic
        // Response mapping
        return Result<ExampleResponse>.Success(new ExampleResponse());
    }
}
```

## Checklist
    - Nullability enabled
    - Async methods with CancellationToken
    - Expected errors modeled as Result
    - Unit tests for critical scenarios
