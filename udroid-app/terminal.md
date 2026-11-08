---
description: Use terminal tabs, appearance profiles, fonts, and shell integration
---

# Terminal and appearance

The terminal stays alive when you move between uDroid pages. Open the installed
Linux system and use **Stop** only when you want to end Linux or change a
setting that requires it to be stopped.

## Tabs and shell integration

Terminal tabs can follow titles reported by shells and applications. A manual
tab name remains in place until you choose **Follow shell title**.

Interactive Bash, Zsh, and Fish sessions receive uDroid shell integration:

- A new tab for the same Linux system starts in the current guest directory
  when that path is still accessible.
- uDroid tracks foreground commands and warns before closing a busy tab.
- Closing a tab shows its shutdown state. A failed close remains available to
  retry, and closing the final tab stops the Linux runtime.
- Supported hyperlinks are underlined and offer confirmed **Open** and **Copy**
  actions.

Tracking cannot see a background job after the prompt returns. A prompt
framework that replaces registered shell hooks may also disable tracking.

## Color profiles

Select the palette button in **Terminal**, open **Terminal appearance**, then
choose **Colors**. Built-in profiles include uDroid, Breeze, Solarized,
Dracula, Catppuccin Mocha, Gruvbox Dark, Nord, Tokyo Night, Rosé Pine, and
Ubuntu. You can create a profile or edit a built-in profile as a custom copy.

**Import** accepts:

- Termux `colors.properties` with `background`, `foreground`, optional
  `cursor`, and `color0` through `color15`.
- Ghostty themes with `background`, `foreground`, optional `cursor-color`, and
  `palette = 0` through `palette = 15`.
- iTerm2 `.itermcolors` files.

Foreground, background, and all 16 ANSI colors are required. Imported files
must be no larger than 1 MiB. Font, command, key-binding, and window settings
inside theme files are ignored and never executed. **Export selected** writes a
Termux-compatible `colors.properties` file.

Compatible palettes are available from
[Termux:Styling](https://github.com/termux/termux-styling/tree/master/app/src/main/assets/colors),
[iTerm2 Color Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes/releases),
and [Ghostty themes](https://ghostty.org/docs/features/theme). Base16 and
Base24 files are not imported directly; use their Termux, Ghostty, or iTerm2
versions.

## Fonts and text

Open **Terminal appearance → Font & text** to change the font, text size, line
height, cursor shape, and cursor blinking. Pinching inside the terminal changes
the same saved text-size setting from 4sp to 96sp.

uDroid includes JetBrains Mono, Fira Code, and Source Code Pro. **Import font**
accepts one or more `.ttf` or `.otf` files up to 16 MiB each. uDroid validates
the files, reads their embedded names, and copies them into private app storage.
Moving the downloaded source file does not remove the imported font.

Use a monospaced font to preserve terminal columns. Imported fonts can be
removed from the font list. **Reset font & text** restores Android's system
monospace and other defaults without deleting imported fonts. Downloadable
monospaced fonts are available from
[Google Fonts](https://fonts.google.com/?categoryFilters=Appearance:%2FMonospace%2FMonospace).

## OSC compatibility

Operating System Command (OSC) sequences let terminal programs communicate
outside the text grid.

| Sequence | Support | uDroid behavior |
| --- | --- | --- |
| OSC 0, 1, 2 | Supported | Sets the shell title unless the tab has a manual name. |
| OSC 4 | Supported | Changes indexed colors for the current session. |
| OSC 10, 11, 12 | Supported | Changes foreground, background, and cursor colors. |
| OSC 52 | Write only | Copies Base64-encoded text to the Android clipboard. |
| OSC 104, 110, 111, 112 | Supported | Resets indexed colors, foreground, background, or cursor color. |
| OSC 133 A/B/C/D | Bash, Zsh, Fish | Tracks prompt and command lifecycle for close warnings. |
| OSC 7 | Bash, Zsh, Fish | Tracks the guest directory for new tabs. |
| OSC 8 | Supported | Underlines hyperlinks and offers **Open** or **Copy**. |
| OSC 9, 777 | Not supported | Android notifications are not created. |
| OSC 9;4 | Not supported | Progress is not shown in the Android UI. |
| OSC 1337 images | Not supported | Inline image rendering is not implemented. |

Supported sequences may end with BEL or ST. OSC 7 accepts local `file://` and
`kitty-shell-cwd://` URIs; remote hosts and unsafe or missing paths fall back to
the Linux home directory. OSC 8 opens only `http`, `https`, and `mailto` links
after confirmation. OSC 52 can replace the Android clipboard, so treat
untrusted terminal output with care.

See the [xterm control-sequence reference](https://invisible-island.net/xterm/ctlseqs/ctlseqs.html)
and [VS Code shell integration](https://code.visualstudio.com/docs/terminal/shell-integration)
for the underlying protocols.
