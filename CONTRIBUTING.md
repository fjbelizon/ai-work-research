# Contribution Guide

Thank you for contributing to `ai-work-research`.

## Branch policy

- The main branch of this repository is `main`.
- Direct commits and pushes to `main` are not allowed.
- If a `master` branch is ever created or used in the future, the exact same rule applies: direct commits and pushes are also not allowed.
- Every change must be made in a separate branch created from the main branch.

## Issue-first requirement

Every contribution must be linked to an issue created in this repository.

- Before creating any branch or starting any work, check whether an issue already exists for the change you want to make.
- If no issue exists, create it first and wait until it is accepted/assigned before starting.
- Work branches and pull requests that are not linked to an issue will not be accepted.
- The branch name must include the issue number (for example, `feature/42-description` or `fix/7-typo`).

## Required contribution workflow

1. Open or identify the issue that justifies the change.
2. Create a branch for your work that includes the issue number (`feature/<number>-description`, `fix/<number>-description`, `docs/<number>-description`, etc.).
3. Make your changes in that branch.
4. Use clear, specific commits with an easy-to-review scope.
5. Open a Pull Request linked to the issue (use `Closes #<number>` or `Fixes #<number>` in the description).
6. Wait for review before merging.

## Requirements for each Pull Request

Each Pull Request must include:

- an explicit reference to the issue it addresses (use `Closes #<number>` or `Fixes #<number>` in the description),
- a clear description of the change,
- the motivation or problem it solves (usually already covered by the issue itself),
- validations performed (for example, manual review, tests, or other applicable checks),
- confirmation that these guidelines were followed.

No PR will be merged without a linked issue.

## Collaboration best practices

- Keep commits clear, small, and easy to review.
- Review your own change before requesting review.
- Avoid mixing unrelated changes in the same PR.
- Respond to review comments and update the PR when needed.
- Keep communication clear about the scope and impact of the change.

## Local safeguards and real branch protection

This repository includes a versioned hook at `.githooks/pre-push` that helps detect attempts to push directly to `main` or `master` from your local environment.

To enable it in your local clone:

```bash
git config core.hooksPath .githooks
```

Important:

- this hook is a local safeguard and does not replace real branch protection,
- effective prevention of direct commits or pushes must be configured in GitHub,
- configure that protection in **GitHub Settings → Rules → Rulesets** or in **Branch protection rules** for `main`, and also for `master` if that branch is ever created.
