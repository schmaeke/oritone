# Oritone

Oritone is a mature light/dark color theme for editors, terminals, and
application interfaces.

- Version: `0.1.0`
- License: MIT
- Reference: Okabe & Ito color-blind-friendly palette, used as a color
  direction source only: <https://siegal.bio.nyu.edu/color-palette/>

The theme name, install names, palette exports, and generated preview files are
all `oritone`.

## Color Preview

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="palette/oritone-palette-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="palette/oritone-palette-light.svg">
  <img alt="Oritone palette preview" src="palette/oritone-palette-light.svg">
</picture>

For the browser preview with responsive HTML/CSS cards, open
[`palette/oritone-palette.html`](palette/oritone-palette.html).

## Included Files

```text
codex/
  oritone-dark.tmTheme
  oritone-light.tmTheme
helix/
  oritone_dark.toml
  oritone_light.toml
  oritone_dark_transparent.toml
  oritone_light_transparent.toml
palette/
  oritone-design-tokens.json
  oritone-palette.ase
  oritone-palette.css
  oritone-palette.gpl
  oritone-palette.html
  oritone-palette.json
  oritone-palette.scss
  oritone-palette-dark.svg
  oritone-palette-light.svg
  oritone-palette.toml
LICENSE
README.md
```

## Palette Structure

The palette is split into dark and light variants. Each variant contains:

- `neutral`: base background, foreground, muted, and border ramps.
- `accent`: named colors derived from the Okabe & Ito color direction and tuned
  for Oritone.
- `semantic`: UI role tokens such as background, surface, primary, success,
  warning, danger, selection, focus ring, cursor, and text levels.
- `terminal`: terminal foreground/background/cursor values and a full ANSI 16
  color map.

Use `palette/oritone-palette.json` or `palette/oritone-design-tokens.json` for
machine-readable integration. Use the CSS or SCSS exports for application UI,
and the GPL or ASE exports for design tools that support palette imports.

## Helix

Copy the Helix themes:

```sh
mkdir -p ~/.config/helix/themes
cp helix/oritone_*.toml ~/.config/helix/themes/
```

Use one theme directly:

```toml
theme = "oritone_dark"
```

Or use Helix light/dark theme selection:

```toml
[theme]
dark = "oritone_dark"
light = "oritone_light"
fallback = "oritone_dark"
```

Transparent variants are also included:

```toml
[theme]
dark = "oritone_dark_transparent"
light = "oritone_light_transparent"
fallback = "oritone_dark_transparent"
```

The transparent variants unset full-screen editor backgrounds so the terminal
emulator's own background, opacity, or wallpaper can show through. Menus,
popups, statusline, selections, and cursor accents remain solid for readability.

## TextMate-Compatible Themes

The `codex/` directory contains XML `.tmTheme` files:

```text
codex/oritone-dark.tmTheme
codex/oritone-light.tmTheme
```

Use these with TextMate-compatible consumers that accept `.tmTheme` files. The
themes define global editor colors, common syntax scopes, markup scopes, search
and selection colors, gutter colors, bracket colors, and diff-related styling.

## CSS Variables

Import the CSS export and use the generated custom properties:

```css
@import "./palette/oritone-palette.css";

.panel {
  color: var(--oritone-dark-text);
  background: var(--oritone-dark-surface);
  border-color: var(--oritone-dark-border);
}
```

Variable names follow this pattern:

```text
--oritone-{mode}-{token}
--oritone-{mode}-terminal-{token}
--oritone-{mode}-ansi-{token}
```

Examples:

```text
--oritone-dark-background
--oritone-dark-primary
--oritone-dark-ansi-bright-blue
--oritone-light-background
--oritone-light-primary
--oritone-light-ansi-bright-blue
```

## Palette Exports

| File | Purpose |
| --- | --- |
| `palette/oritone-palette.json` | General-purpose JSON palette data. |
| `palette/oritone-design-tokens.json` | Design Tokens Community Group style color tokens. |
| `palette/oritone-palette.css` | CSS custom properties. |
| `palette/oritone-palette.scss` | SCSS variables. |
| `palette/oritone-palette.toml` | TOML export for tools that prefer TOML. |
| `palette/oritone-palette.gpl` | GIMP/Inkscape palette import. |
| `palette/oritone-palette.ase` | Adobe Swatch Exchange palette import. |
| `palette/oritone-palette.html` | Browser palette preview. |
| `palette/oritone-palette-dark.svg` | Dark GitHub theme vector palette preview. |
| `palette/oritone-palette-light.svg` | Light GitHub theme vector palette preview. |

## License

Oritone is MIT licensed. See [`LICENSE`](LICENSE).
