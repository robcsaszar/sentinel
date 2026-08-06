# Contributing

Thanks for considering a contribution to `sentinel`. This repo publishes a single skill; contributions are welcome, but keep changes proportionate to that scope.

## Before you start

- **Bug in a check?** Open an issue with the exact false-positive or false-negative example: which category, what the skill got wrong.
- **New checklist category or phase change?** Open an issue first so the scope is agreed before you write it up.

## Making a change

1. Fork and branch from `main`.
2. Keep the skill's phase structure (Stack Triage -> Scan -> Classify -> Report) intact unless the issue you opened specifically proposes changing it.
3. Make sure the skill still reads as generic guidance: no assumptions specific to one codebase or framework.

## Quality bar

The skill should stay generically useful outside the project it was originally built for. A PR that ties its instructions to one repo's conventions, or that softens the PASS/FAIL/MANUAL-REVIEW evidence discipline, will be asked to fix that before merge.

## Questions

Open an issue. There's no separate chat or forum for this project.
