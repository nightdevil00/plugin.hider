# plugin.hider

A bar widget for [Omarchy](https://omarchy.org/) that lets you hide and show all plugins in the right bar section with a single click.

## Installation

```bash
omarchy plugin add git@github.com:nightdevil00/plugin.hider.git --enable
```

When prompted, choose **right** as the bar section placement.

## Usage

Click the chevron icon (`<` / `>`) in the right bar section:

- **`<`** — all other right-section plugins are hidden and the icon rotates to `>`
- **`>`** — hidden plugins are restored and the icon rotates back to `<`

The hidden state persists across shell restarts.

https://github.com/nightdevil00/plugin.hider/blob/main/screenrecording-2026-08-20_20-33-37.mp4

## How it works

The plugin reads `bar.layout.right` from `~/.config/omarchy/shell.json`. When hiding, it moves every other entry in that section into a `hiddenEntries` array on its own layout entry and filters them out of `bar.layout.right`. When showing, it moves them back. The shell hot-reloads on save, so no restart is needed.

## Settings

None. The widget has no user-configurable settings.

## License

MIT
