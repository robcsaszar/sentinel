# AGENTS.md

## Mission

This repo publishes the `sentinel` skill: a single skill under `skills/sentinel/`. There is no build, no tests, no runtime of its own. The deliverable is the contents of that one directory. Changes should be judged by: would a stranger who installs this skill into their own project get a correct, evidence-backed security audit out of it, one that doesn't assume Orakl's codebase, stack, or conventions?

## Judgment boundaries

ASK:
- Ask before removing the skill or restructuring its phases; this repo has exactly one skill and no fallback if it regresses.

ALWAYS:
- Don't let the skill's content drift toward assumptions specific to any one codebase or framework; remediation guidance should stay generic enough to adapt to whatever stack the installing project actually uses.
