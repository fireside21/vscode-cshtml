# Change Log
All notable changes to the "HTML (C#)" extension will be documented in this file.

## [Unreleased][]
### Fixed
- Changelog 0.1.2 and 0.1.3 links

## [0.1.3][] - 2018-09-21
### Added
- Detection for Application directives
- To-Do list

### Changed
- `<script runat="server"` no longer case-sensitive

## [0.1.2][] - 2018-09-15
### Added
- A simple icon

### Changed
- Package metadata
- Known Issues in ReadMe

### Fixed
- Changelog version links

## [0.1.1][] - 2018-09-04
### Changed
- Avoid injecting C# into C# comments.

### Removed
- Some unhelpful bracket behavior.

## [0.1.0][] - 2018-08-23
### Added
- Highlighting for directives: `<%@ Page %>`, etc.
- Highlighting for `<script runat="server">`
- Highlighting for block comments: `<%-- --%>`
- Highlighting for `Response.Write` expressions: `<%=`, `<%#`, `<%:`, and `<%$`
- Snippets for `Response.Write` expressions and some common Directives


[keep-a-changelog]: https://keepachangelog.com/

[Unreleased]: https://github.com/fireside21/vscode-cshtml/compare/v0.1.3...HEAD
[0.1.3]: https://github.com/fireside21/vscode-cshtml/compare/v0.1.2...v0.1.3
[0.1.2]: https://github.com/fireside21/vscode-cshtml/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/fireside21/vscode-cshtml/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/fireside21/vscode-cshtml/compare/6240d17dc690c44f68b62f21c71492501fc259e2...v0.1.0
