# nkalai Theme

Nkalai is a paired light/dark Visual Studio Code theme designed to stay gentle on your eyes during long editing sessions. Both variants share the same earthy greens, soft neutrals, and muted oranges so flipping between day and night modes never feels jarring.

I originally tweaked Wes Bos’ Cobalt2 theme for personal use, but after so many changes it felt right to publish the result as its own palette. This is a passion project rather than a professional product—I’m simply sharing it in case others find the colours helpful.

## Theme Snapshot

| Variant | Background | Foreground | Accent notes |
| --- | --- | --- | --- |
| **nkalai Light** | `#F5F2E8` (parchment) | `#2F291F` (deep brown) | Sage greens for cursors/selections, terracotta strings, muted violets for operators. |
| **nkalai Dark** | `#2F353B` (charcoal) | `#D8D3C8` (warm sand) | Seafoam cursor/accents, amber numbers, rose-gold constants, teal UI highlights. |

Both JSON theme files enable semantic highlighting, so language servers can apply the palette to semantic token classifications such as classes, parameters, and readonly properties.

## Installation (Development)
1. Clone this repository and open it with VS Code or VSCodium.
2. Press `F5` (or Run → Start Debugging). The included `.vscode/launch.json` launches a second *Extension Development Host* window.
3. In the Dev Host, open the theme picker (`Cmd+K Cmd+T`) and choose **nkalai Light** or **nkalai Dark**.

## Installation (VSIX)
1. Install the VSCE CLI if you have not already:
   ```bash
   npm install -g @vscode/vsce
   ```
2. From the project root build the package:
   ```bash
   vsce package
   ```
3. In your primary VS Code window, open the Extensions view → “⋯” menu → *Install from VSIX…* and select the generated `.vsix` file.

## Palette Highlights
- **UI chrome:** Activity bar, status bar, tabs, and sidebars reuse the same green accents (`#8DC6AC` / `#7CB099`) to keep affordances consistent between themes.
- **Syntax:** Strings lean warm (`#E09B61` dark, `#C98652` light), keywords stay neutral, and data keys receive bold tints for JSON-heavy workflows.
- **Terminals:** Custom ANSI ramps ensure terminals match the editor background for both variants.

## Preview Assets
- `media/preview-light.png` – screenshot of the light theme using `samples/example.js`.
- `media/preview-dark.png` – screenshot of the dark theme using the same sample file for easy comparison.

## Working on the Theme
- Edit `themes/nkalai-light-color-theme.json` or `themes/nkalai-dark-color-theme.json`; both are plain JSON, so run `jq empty themes/*.json` (or rely on VS Code diagnostics) before relaunching.
- Reload the Dev Host via `Developer: Reload Window` to apply colour tweaks instantly.
- Use `Developer: Inspect Editor Tokens and Scopes` to understand which token scopes need new colour assignments.

## Publishing Checklist
1. Update `package.json` metadata (description, keywords, version, icon, gallery banner) before tagging a release.
2. Capture screenshots or GIFs of both variants, add them to `media/`, and reference them from this README and `package.json` for richer Marketplace previews.
3. Run `vsce package` followed by `vsce publish` (requires a Marketplace publisher named in `package.json`’s `publisher` field).

Enjoy the lighter feel without losing contrast, day or night.
