# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.6.0] - 2026-08-14

### Fixed

- Frontmatter `description` was an unquoted YAML plain scalar containing `": "` sequences (`Use when: …`, `Keywords are …`), which is a mapping-value parse error. The value is now single-quoted, so the frontmatter parses.

### Changed

- Description: replaced the quoted keyword list with a plain coverage sentence. The skill sets `disable-model-invocation: true`, so its description is human-facing only and carries no router keywords.

## [0.5.0] - 2026-07-10

### Added

- Initial release: sentinel skill.

[0.5.0]: https://github.com/robcsaszar/sentinel/releases/tag/v0.5.0
