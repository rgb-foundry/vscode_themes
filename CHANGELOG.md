# Changelog

All notable changes to **Hypnotic Copper** will be documented in this file.

## [1.5.0] - 2026-10-15

### Added

- Set modern UI colors for the active activity-bar item, tab hover, and sash grip.

### Changed

- Gave Metal and Glow one shared syntax palette, calming Glow's loud purple and returning copper to the lead in Metal.
- Separated Dark's namespaces from its functions, and Metal's comments from its numbers.
- Gave warnings and errors their own colors, apart from numbers and copper keywords, with a shared crimson error in the light variants.
- Rebuilt the bracket-pair colors on one copper-led hue pattern that meets WCAG AA in every variant.

### Fixed

- Fixed below-AA bracket colors, number/warning color collisions, Metal's offset bracket guides, Glow's invisible active activity-bar item, faint hover states, and a low-contrast sash grip.

## [1.4.1] - 2026-10-14

### Fixed

- Reduced the extension icon to meet the Visual Studio Marketplace's 1024 KB icon size limit.

## [1.4.0] - 2026-10-14

### Added

- Added decorator, deprecated-symbol strikethrough, and Pylance `self`/`cls` and built-in constant colors.

### Changed

- Aligned TextMate and semantic token colors so tokens no longer change color when a language server loads.
- Gave each variant one type color for all type-like symbols and a consistent Blue Steel and bronze, and updated the README palette to describe colors by role.
- Changed Metal's Python docstrings to its comment color, matching Glow and Dark.

### Fixed

- Fixed Dark constants blending into keywords, C++ primitive types rendering as invalid code, Glow's navy Python strings, below-AA search line numbers, and invisible `region.whitish` text on light variants.

## [1.3.0] - 2026-10-14

### Added

- Added Visual Studio Code modern UI support with a unified neutral window frame, borderless floating cards, and a quieter unfocused-window state across all three variants.

### Changed

- Rebuilt the copper accents of all three variants on a single burnished copper ladder, replacing Dark's many one-off copper shades.
- Lightened the Status Bar copper, darkened its hover states, and made the debugging Status Bar bright yellow.
- Merged the title bar into the window frame and restyled the command center as a floating pill.
- Raised Metal's Status Bar, button, menu, link, and command center contrast to WCAG AA.

### Fixed

- Fixed amber terminal ANSI blue in Glow and Dark, non-yellow chart yellow, and below-AA button hover contrast.

## [1.2.4] - 2026-08-15

### Added

- Added dedicated Go, YAML, and Markdown syntax rules across all three variants.

### Changed

- Rebuilt Metal's syntax palette for WCAG AA contrast and clear separation between neighboring token colors, while preserving its blue-gray background and focus accent.
- Cleaned up scope conflicts and dead rules across all three variants.

### Fixed

- Fixed a stray non-palette color in Glow's C++ return-keyword highlighting.

## [1.2.3] - 2026-08-06

### Added

- Added explicit Starlark and Bazel highlighting for callable names, keyword arguments, and function parameters across all three variants.

### Changed

- Improved Metal's function, string, and terminal ANSI contrast while preserving its blue-gray backgrounds and copper accents.

### Fixed

- Separated terminal warning annotations from the red reserved for errors, including bright-color terminal output.

## [1.2.2] - 2026-08-05

### Fixed

- Improved ignored Git resource readability across all three variants.

## [1.2.1] - 2026-08-05

### Added

- Added palette-specific compact Status Bar hover backgrounds across all three variants.

### Changed

- Refined Metal's copper accents across inputs, lists, scrollbars, buttons, and Status Bar interactions.

## [1.2.0] - 2026-08-05

### Added

- Expanded workbench and TextMate token coverage across Metal, Glow, and Dark.
- Added Markdown screenshots for all three variants.

### Changed

- Reworked Metal with soft blue-gray surfaces, navy text, blue interaction states, and restrained copper foreground accents.
- Removed italic styling and updated token rule metadata across all variants.
- Migrated deprecated theme colors and corrected overlay transparency.
- Refreshed the Python and C++ screenshots for the current palettes.

### Fixed

- Removed unsupported token backgrounds and eliminated VS Code color-theme schema warnings.

## [1.1.1] - 2026-07-13

### Added

- Added Hypnotic Copper Glow screenshots.

### Changed

- Refined README wording for the current Metal, Glow, and Dark lineup.

## [1.1.0] - 2026-07-13

### Added

- Added Hypnotic Copper Glow as a crisp white light variant.

### Changed

- Removed dark theme terminal ANSI overrides so terminal tools keep native signal colors.
- Refined dark theme copper accents and remote status bar colors.
- Aligned theme color keys and token structures across Metal, Glow, and Dark.

## [1.0.0] - 2026-07-09

### Added

- Initial release
- Hypnotic Copper Metal theme
- Hypnotic Copper Dark theme
- Semantic token highlighting
- Copper-inspired UI accents
- Refined terminal and GitLens integration
