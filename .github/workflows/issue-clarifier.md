---
on:
  issues:
    types: [opened]
permissions: read-all
safe-outputs:
  add-comment:
---
# Research Issue Classifier and Clarifier

Analyze the newly opened issue and determine whether it contains enough
information to begin a research task.

## Steps

1. Read the issue title and description.
2. Check whether it includes:
   - A clear research question
   - Target sector or use case
   - Available data or suggested sources
   - Success criteria or expected deliverable
3. If any required element is missing, add a concise, friendly comment requesting
   the missing information.
4. If the issue is complete, add the `ready-for-research` label and a short
   confirmation comment indicating the issue is well-defined.

Do not close the issue or perform any other action.
