# Changelog

All notable changes to **Hypnotic Copper** will be documented in this file.

## [1.4.1] - 2026-10-14

### Fixed

- Reduced the extension icon from 1254 × 1254 px (3 MB) to 256 × 256 px (116 KB) to meet the Visual Studio Marketplace's 1024 KB icon size limit, which blocked publishing 1.4.0.

## [1.4.0] - 2026-10-14

### Added

- Added a dedicated Decorators rule so decorator names and `@` markers use copper before and after semantic highlighting loads.
- Added a strikethrough for deprecated symbols through the `*.deprecated` semantic modifier.
- Added Pylance `selfParameter` and `clsParameter` semantic colors that match the quiet TextMate color for `self` and `cls`, and a `builtinConstant` color so `None`, `True`, and `False` use Blue Steel.

### Changed

- Aligned TextMate and semantic token colors in all three variants, so enums, enum members, parameters, decorators, macros, type parameters, labels, readonly symbols, and Glow's types no longer change color when a language server finishes loading.
- Gave every type-like symbol (types, classes, interfaces, enums, type parameters, and primitive types) a single type color per variant: plum in Dark, teal in Glow, and slate in Metal.
- Gave Glow a true Blue Steel (`#415FB9`, shared with Metal) for namespaces, constants, readonly symbols, macros, TODO tags, Git hashes, and YAML anchors, replacing a rose-brown that did not match the documented palette.
- Moved numbers and enum members to each variant's bronze, matching the documented palette and the semantic number color.
- Colored macros with Blue Steel instead of red, and Python string prefixes with copper.
- Rendered parameters in the variable color while keeping `self` and `cls` quiet.
- Changed Metal's Python docstrings from the string color to its comment color to match Glow and Dark.
- Unified Dark's function and method colors, and its operator and punctuation colors, which had drifted into near-duplicate shades.
- Changed Metal's arrow functions, `extends`, Rust lifetimes and visibility modifiers, regular expression delimiters, link titles, and deleted diff lines from a below-AA blue to Metal's copper, matching Glow and Dark.
- Updated the README syntax palette to describe each color by role, including Metal's slate type color.

### Fixed

- Fixed Dark's constants, which had become almost indistinguishable from copper keywords; they now use Blue Steel.
- Fixed C++ primitive types such as `int` and `float` rendering in the invalid-code red in all three variants.
- Fixed Glow's Python strings rendering in navy instead of the sage used for every other language, and Glow's regular expressions rendering in navy.
- Fixed Glow and Dark search-result line numbers falling below WCAG AA contrast.
- Fixed `region.whitish` text being invisible on Metal and Glow's light backgrounds.
- Restored identical token rule order across all three variants.

## [1.3.0] - 2026-10-14

### Added

- Added support for the Visual Studio Code modern UI: `modernUI.shellBackground` and `modernUI.inactiveShellBackground` now give the gaps between the floating Explorer, editor, panel, and Status Bar cards the same neutral as the title bar in each variant (Metal `#C5C8D8`, Glow `#ECECEC`, Dark `#1A1F24`), so the window reads as one calm frame instead of a pale strip above the Status Bar.
- Added borderless floating cards through a transparent `surface.border`, letting each variant's surface colors separate the cards on their own.
- Added an unfocused-window state with a quieter frame, a muted copper Status Bar (`statusBar.inactiveBackground`), and warm-gray inactive title text.

### Changed

- Rebuilt the copper accents of all three variants on a single burnished ladder (`#74392D`, `#864333`, `#9A4A39`, `#A85843`, `#B4604B`, `#CF8268`, `#E6AA94`). This replaces roughly thirty one-off copper shades in Dark and unifies keyword, selection, badge, button, link, cursor, scrollbar, and Status Bar copper across the family. Bracket-pair colors remain independent so nesting levels stay distinguishable.
- Lightened the Status Bar copper (Metal and Glow `#A85843`, Dark `#9E5340`) and darkened every Status Bar hover state, including compact grouped items and the remote indicator, so hovered items clearly sink into the bar.
- Changed the debugging Status Bar to bright yellow with dark text, so a debug session is unmistakable and no longer shares its color with warning text (Metal and Glow) or with the normal copper bar (Dark).
- Merged the title bar into the window frame and restyled the command center as a floating pill in the editor's surface color.
- Gave Glow's title text a warm near-black (`#3A2723`).
- Switched Metal's Status Bar, remote indicator, and primary button text to white for WCAG AA contrast on copper, and made Metal's primary button opaque.
- Brought Metal's menu selection, text links, and command center text up to WCAG AA using Metal's information blue (`#415FB9`) and a deeper blue-gray (`#5A6189`), and raised Dark's command center text contrast.

### Fixed

- Fixed `terminal.ansiBlue` and `terminal.ansiBrightBlue` rendering as amber in Glow and Dark; they now use blue (`#2B5CB3` in Glow, `#7E9FE0` in Dark).
- Fixed `charts.yellow` rendering as copper in Glow and Dark and as the warning khaki in Metal; it is now a true yellow in all three variants.
- Fixed the inline-edit success indicator border in Glow and Dark, which did not use the success green.
- Fixed primary button hover contrast, which fell below WCAG AA in all three variants.
- Removed Metal's near-duplicate copper (`#9E4B3B`).

## [1.2.4] - 2026-08-15

### Added

- Added dedicated Go builtin-type, YAML anchor/alias, Markdown strikethrough, and Markdown list-bullet syntax rules across all three variants.

### Changed

- Rebuilt Metal's syntax token palette for WCAG AA contrast against its blue-gray background: comments, punctuation, types, enums, and errors are all readable at a comfortable margin, and previously near-identical neighboring tokens (comments, punctuation, and types had collapsed into the same color) are now clearly distinct from one another.
- Gave Metal's function and method names a more saturated violet so they read as a deliberate accent instead of blending into the surrounding syntax colors, and moved comments and punctuation out of the blue-gray family into warm-taupe and neutral-gray tones respectively, while keeping Metal's signature blue focus accent and background untouched.
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
