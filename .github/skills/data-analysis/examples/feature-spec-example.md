# Feature Spec Example: Scoring Service

## Context
The system must calculate an AI adoption score per organizational unit.

## Design
- Service: `IAdoptionScoringService` / `AdoptionScoringService`
- Dependencies: metrics repository, system clock, logger
- Output: normalized score between 0 and 100

## Contracts

```csharp
public sealed record AdoptionScoringRequest(string UnitId, DateOnly Period);
public sealed record AdoptionScoringResponse(string UnitId, decimal Score, string Band);
```

## Acceptance criteria
1. If required metrics are missing, return a descriptive domain error.
2. If data is valid, return a score rounded to two decimals.
3. The calculation must be deterministic for the same input.

## References
- `docs/architecture.md`
- `tests/Scoring.Tests/`
