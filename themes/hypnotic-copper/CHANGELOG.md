# Changelog

All notable changes to **Hypnotic Copper** will be documented in this file.

## [1.6.2] - 2026-10-28

### Changed

- Dark is one step darker. The editor, Side Bar, and Activity Bar now share one surface, `#111519`, and the window frame drops to `#0A0D10`, so the floating panels stand out clearly against it. Focused list rows, unfocused selections, the unfocused window frame, unchanged diff regions, and notebook cell editors use `#1A1F24` so they stay visible on the darker surface.

### Fixed

- C++ word operators now use the copper keyword color: `sizeof`, `alignof`, `alignas`, `typeid`, `noexcept`, `delete`, the casts such as `static_cast`, and the alternative tokens such as `and`, `or`, and `not`. They had used the operator color. `new` was already copper.

## [1.6.1] - 2026-10-27

### Fixed

- Python and Starlark word operators (`and`, `or`, `not`, `in`, `is`) now use the copper keyword color, as in `if path not in items:`. They had used the operator color, which made them look like plain text, especially in Dark. Symbol operators such as `==` and `+` keep the operator color.

## [1.6.0] - 2026-10-16

### Added

- Rebuilt every color in all three variants on twelve 12-step color ramps (neutral, copper, crimson, amber, emerald, azure, gold, olive, teal, steel, plum, and a separate gray ramp for code), plus a few fixed constants such as white text on copper. Each interface key now uses a named job (surface, border, muted text, focus, warning, and so on) instead of a one-off color. Dark drops from 101 distinct base colors to 45, and its near-duplicate color pairs from 136 to 5.
- Status Bar error and warning items are now solid chips: crimson with white text in Metal and Glow and vivid red `#FC5045` with dark text in Dark, and bright amber (`#F39A20` in Metal and Glow, `#FC995F` in Dark) with dark text. They stand apart from the copper bar and from the yellow debugging bar.
- Terminal colors now follow the palette, so build tools such as Bazel read consistently: INFO and PASSED in emerald, DEBUG in amber, WARNING and FLAKY in plum (magenta), SUBCOMMAND in azure, and ERROR and FAILED in crimson. In Dark, bold errors use a true red.

### Changed

- Metal's focus rings, active indicators (activity bar, panel titles, tabs, radio buttons), word and find highlights, and links now use copper, like Glow and Dark. Metal's bright blue `#457BE2` now marks info.
- Success, added lines, and passed tests use emerald (`#0C7253` in Metal and Glow, `#269E75` in Dark), and info and modified use azure (`#457BE2` in Metal and Glow, `#1A95D8` in Dark). Both are now clearly distinct from strings and namespaces. Modified files in the Explorer change from copper to azure.
- List hover in Metal now uses a faint tint of the text color instead of copper. Copper is kept for selection.
- Primary buttons and badges in Metal and Glow move to the Status Bar copper `#A85843` and darken to `#9A4A39` on hover. Keywords stay `#9A4A39`, matching Dark's split between button and keyword copper.
- Dark's Status Bar uses the same copper as Metal and Glow (`#A85843`), with `#864333` on hover.
- The Status Bar of an unfocused window uses a lighter copper, `#CF8268`, in all three variants, so a background window is easy to tell apart.
- Borders now come in three strengths (subtle, default, strong) in every variant. Glow's inputs and popups get a faint outline, Metal's input border is gray instead of copper, and Dark's widget and input borders are slightly quieter.
- Muted text is slightly darker in Metal (`#4B5276`, navy-tinted) and Glow (`#656A71`).
- Outline, breadcrumb, and suggest icons and debug variable colors now match the code colors for each symbol kind.
- Class names in Dark keep their plum color when semantic highlighting loads, instead of switching from periwinkle.
- CSS classes, Markdown links, inserted diff text, and constructors in Metal use the function plum, matching Glow.
- Bracket-pair colors now reuse palette colors. In Metal and Glow, level 2 becomes the type teal. In Dark, level 3 becomes the palest copper. Every level still meets WCAG AA, and levels stay at least ΔE 14 apart. Source Control graph lanes follow the bracket colors.
- Terminal yellow is amber instead of copper, and terminal green is emerald instead of the string color. Terminal magenta in Glow is plum instead of GitHub's purple. Terminal black, white, and their bright versions follow the usual order in every variant.

### Fixed

- Fixed interface text below WCAG AA contrast, found by checking every text color against the background it actually sits on:
  - sidebar view titles in all three variants (1.3:1 to 1.6:1 before)
  - section headers and inactive tabs in Metal and Glow
  - Quick Open text in all three
  - Metal's added and untracked file names, warning text in lists, inputs, the Debug Console, and the Status Bar
  - Metal's input placeholders, suggest list, notification text, and inactive panel titles
- Fixed Glow's terminal black, which was almost white, and Dark's terminal black, which was almost invisible.
- Fixed Metal's active activity-bar indicator falling below the 3:1 contrast minimum.

## [1.5.0] - 2026-10-15

### Added

- Set three modern UI keys explicitly: `modernActivityBarItem.activeBackground`, `modernTab.hoverBackground`, and `modernSash.gripForeground`.

### Changed

- Metal and Glow now share one syntax palette. Copper keywords use `#9A4A39`, functions plum `#874D95`, types teal `#18667C`, namespaces and constants steel `#4C5A9B`, numbers bronze `#765F3C`, and strings olive `#51682F`. The two light variants now differ only in surface.
  - Metal keywords moved from `#864333` to the R1 ladder's `#9A4A39`, so copper leads again.
  - Metal types moved from slate `#566181` to teal, which had sat too close to the steel.
  - Glow functions moved from GitHub Light's `#8250DF` (chroma 84) to plum.
  - Glow types moved from `#267F99` to a deeper teal (4.59 → 6.50:1).
  - Glow numbers and strings moved to Metal's bronze and olive.
  - The accent chroma spread falls from 56 to 23 in Glow and from 35 to 23 in Metal, close to Dark's 24, so no single accent dominates.
- Namespaces, constants, readonly symbols, and macros in Metal and Glow use a grayer steel, `#4C5A9B`, in place of Blue Steel `#415FB9`. Workbench UI keys keep `#415FB9`, which matches the blue-gray palette that inspired Metal.
- Moved Dark's namespaces and constants from `#83AFC9` to periwinkle `#9AB8EC`. They had nearly matched the cyan function color (ΔE 9.1).
- Moved Metal's comments from warm taupe `#6B6258` to sage gray `#445A4E`. This separates them from the bronze numbers and raises their contrast from 4.62:1 to 5.76:1.
- Moved Dark's warnings from `#D69A59`, which numbers also used, to golden amber `#EBC15A`. Moved its errors from `#F06B5D`, close to the copper keywords, to rose `#F06B8A`.
- Metal now uses Glow's amber warning, `#A15C16`, in place of the muted bronze `#876D45`, which sat too close to the numbers.
- Metal and Glow share a crimson error color, `#B0244A`. It replaces `#E14167` (3.15:1) in Metal and `#B42318` in Glow, moves error squiggles away from copper keywords, and passes WCAG AA as text on every light surface.
- Rebuilt the six bracket-pair levels in all three variants on one hue pattern: copper, teal, gold, blue, green, plum. Each level starts on the R1 copper ladder and passes WCAG AA. Every pair of levels is ΔE 13.7 or more apart. Dark uses deeper shades than before. Metal and Glow use the lightest shades their backgrounds allow.
- Bracket pair guides now use their own level's color in every variant.
- Glow no longer uses the off-ladder `#D97757`.

### Fixed

- Fixed bracket-pair colors below WCAG AA: all six levels in Metal, four in Glow, and two in Dark.
- Fixed numbers and enum members in Dark and Glow sharing their exact color with warning squiggles.
- Fixed Metal's bracket pair guides, which were shifted by one level.
- Fixed Glow's active activity-bar item, which was invisible (`#F2F2F2` on `#F3F3F3`). It now has a copper tint.
- Fixed faint tab and activity-bar hover backgrounds in Glow and Dark.
- Fixed the sash grip falling below the 3:1 non-text contrast minimum in all three variants.

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
