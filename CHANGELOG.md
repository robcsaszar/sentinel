# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.7.0] - 2026-08-15

Upstreamed from working use of the skill in a real codebase.

### Added

- Phase 5 (Remediate FAILs) and Phase 6 (Work through MANUAL-REVIEWs) — the skill now acts on its own report instead of ending at it. FAILs are fixed one at a time under per-item approval; MANUAL-REVIEW items are expanded from a one-line action into followable instructions with a disposition captured for each. Phase 4 ends by asking whether to proceed, so an audit-only run stays a first-class outcome.
- `references/remediation-workflow.md` — interaction protocols for both phases, loaded only once remediation begins.
- Phase 3 capability probe — check for credentials, an authenticated vendor CLI, and config-as-code before declaring anything user-only, then state the agent boundary explicitly in the finding. Handing back work the agent could have done costs a round trip.
- Phase 1 now captures the project's verification command, which Phase 5 runs after every fix.
- Runtime-verification table for fixes that change request-time behavior. A type-check and build both pass on a CSP that blanks every page in production, so headers, auth, middleware, rate limits, and schema changes must be exercised with a real request before being marked fixed. Written after exactly that regression shipped — a hand-written policy that blocked SvelteKit's own inline hydration script. Fixes that can't be exercised locally are marked verified-by-build-only rather than passing as verified.
- Three NEVER rules covering the capability probe, the verification command, and the green-build trap.

### Fixed

- Phase 5 committed each fix before asking for approval, so `(r)evise` and `(s)kip` implied unwinding a commit that should not have existed. The commit now follows the answer, and the diff is shown before the question. Verification still precedes the question, since it informs the decision.
- The quit key was `(q)uit` in four prompts while `remediation-workflow.md` required uppercase `Q` — lowercase `q` sits next to `a` and would otherwise fall through to approve.

### Removed

- `NEVER write a finding block for a category you haven't read the source file for` — redundant with the PASS-requires-reading and FAIL-requires-a-snippet rules, whose rationale it restated almost verbatim.

## [0.6.0] - 2026-08-14

### Fixed

- Frontmatter `description` was an unquoted YAML plain scalar containing `": "` sequences (`Use when: …`, `Keywords are …`), which is a mapping-value parse error. The colons are now removed entirely rather than escaped, so the value parses quoted or unquoted and conforms to the house no-colons rule.

### Changed

- Description: replaced the quoted keyword list with a plain coverage sentence. The skill sets `disable-model-invocation: true`, so its description is human-facing only and carries no router keywords.

## [0.5.0] - 2026-07-10

### Added

- Initial release: sentinel skill.

[0.5.0]: https://github.com/robcsaszar/sentinel/releases/tag/v0.5.0
