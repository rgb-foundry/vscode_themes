# Changelog

All notable changes to **Hypnotic Copper** will be documented in this file.

## [1.2.4] - 2026-08-15

### Added

- Added dedicated Go builtin-type, YAML anchor/alias, Markdown strikethrough, and Markdown list-bullet syntax rules across all three variants.

### Changed

- Darkened Metal's comment, punctuation, type, enum, and error text colors in place (same hues, lower lightness) to clear WCAG AA contrast against its blue-gray background, while leaving its blue focus accent untouched.
- Resolved a scope conflict in Metal where the dedicated Namespace rule was silently shadowed by the Constants rule; namespaces now consistently use Metal's blue.
- Trimmed Metal's Functions rule scope to match Glow and Dark, removing an overly broad `meta.function-call` match that risked tinting call arguments.
- Removed a dead, shadowed `storage.type` rule from all three variants (a later bulk Keywords rule already owned that scope).

### Fixed

- Fixed Glow's C++ Return Keywords rule, which rendered in a stray violet (`#AF00DB`) outside the theme's palette instead of Glow's copper.

## [1.2.3] - 2026-08-06

### Added

- Added explicit Starlark and Bazel syntax rules for rule and function names, keyword arguments, and function parameters across all three variants.

### Changed

- Improved **Hypnotic Copper Metal** function-name and string contrast while separating callable names from copper keywords and declarations.
- Refined Metal's terminal ANSI colors for clearer info, progress, warning, and error output.

### Fixed

- Prevented bright magenta warning annotations from rendering with the same red used for terminal errors, improving cross-platform warning separation.

## [1.2.2] - 2026-08-05

### Fixed

- Improved ignored Git resource readability in the Explorer and active or inactive tabs across all three variants.

## [1.2.1] - 2026-08-05

### Added

- Added palette-specific compact hover backgrounds for grouped Status Bar items in Metal, Glow, and Dark.

### Changed

- Strengthened the copper character of **Hypnotic Copper Metal** across secondary button hover, input borders, list selections and hovers, scrollbar states, and the Status Bar.
- Refined Metal's standard, prominent, and remote Status Bar hover states for a more cohesive copper treatment.

## [1.2.0] - 2026-08-05

### Added

- Expanded all three variants with comprehensive workbench coverage for Chat, inline editing, diff and merge views, debugging, notebooks, testing, settings, terminal states, and Source Control graphs.
- Added broader TextMate scope coverage for programming languages, markup, Git output, regular expressions, documentation, and language-specific syntax.
- Added Markdown screenshots for Metal, Glow, and Dark.

### Changed

- Reworked **Hypnotic Copper Metal** around soft blue-gray surfaces, deep navy text, blue interaction states, and carefully restored copper foreground accents.
- Removed italic styling throughout the theme family while preserving meaningful underline and markup styling.
- Moved token rule labels to the schema-supported rule-level `name` property.
- Updated overlay colors with the transparency required by VS Code.
- Migrated deprecated or removed workbench color keys to their current equivalents.
- Refreshed the Python and C++ screenshots to show the current palettes.

### Fixed

- Removed unsupported TextMate token backgrounds and invalid `fontStyle` values.
- Eliminated all color-theme schema warnings reported by Visual Studio Code 1.131.

## [1.1.1] - 2026-07-13

### Added

- Added screenshots for **Hypnotic Copper Glow**.

### Changed

- Refined README wording for the current Metal, Glow, and Dark lineup.

## [1.1.0] - 2026-07-13

### Added

- Added **Hypnotic Copper Glow**, a crisp white light theme built from the Dark variant's contrast language and copper identity.

### Changed

- Removed dark theme terminal ANSI overrides so build tools and shells keep their native signal colors.
- Reworked dark theme remote status bar colors with a deeper copper treatment and a brighter copper hover state.
- Promoted the signature copper accent into more dark theme selection and badge surfaces while preserving readable foreground contrast.
- Aligned color keys, token rule names, and semantic token keys across all three theme files.
- Added targeted Python and C++ token refinements for stronger light-theme contrast.

## [1.0.3] - 2026-07-12

### Added

- Expanded semantic token color coverage for standard VS Code semantic token types.
- Added explicit semantic rules for platform-sensitive token families so equivalent symbols render consistently across language servers.

### Changed

- Aligned related semantic token colors for functions and methods, type-like symbols, value-like symbols, and enum-like symbols.
- Harmonized remote status bar item backgrounds with the copper status bar palette while preserving strong foreground contrast.

## [1.0.2] - 2026-07-11

### Added

- Fixed screenshot URLs

## [1.0.1] - 2026-07-11

### Added

- Screenshots

## [1.0.0] - 2026-07-09

### Added

- Initial release
- Hypnotic Copper Metal theme
- Hypnotic Copper Dark theme
- Semantic token highlighting
- Copper-inspired UI accents
- Refined terminal and GitLens integration
