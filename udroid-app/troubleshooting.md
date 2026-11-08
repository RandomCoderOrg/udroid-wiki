---
description: Update uDroid, collect logs, and resolve common problems
---

# Updates and troubleshooting

## Updates

Open **About** to check for updates. uDroid verifies a downloaded APK before
opening Android's installer, and Android asks for final confirmation. Release
downloads also include `SHA256SUMS` for manual verification.

## Diagnostic logs

The diagnostic viewer under **About** records app actions and supervised Linux
commands. Search it, select a log block to copy that block, or use **Copy
report** when asking for help.

Logs intentionally include command details needed for diagnosis. Review a
report before sharing it publicly if your commands contain private paths,
arguments, or environment values.

## Common problems

| Problem | What to try |
| --- | --- |
| Installation stopped | Read the active-stage message, open **View install log**, fix the reported problem, then select **Try again**. |
| A paused installation does not continue | Return through its notification or Linux-system card and select resume from the same installation page. |
| Android closes Linux | Follow the warning on the system page and review Android's child-process restriction setting. |
| Desktop is slow or visually damaged | Use **Automatic** or **Software** graphics, disable desktop compositing, or lower the display resolution. |
| An installed application is missing | Refresh **Apps** and verify that its package provides a `.desktop` entry. |
| One application has no sound | Install its distribution's PulseAudio client or compatibility package. |
| Linux no longer starts after adding flags | Remove or rename `/storage/emulated/0/udroid-launch-flags.txt`, then retry. |
| A terminal tab will not close | Wait for graceful shutdown or retry the close after the failed state appears. Force-close only when the process cannot exit normally. |

When [filing an issue](https://github.com/RandomCoderOrg/udroid-app/issues),
include the phone model, Android version, uDroid version, selected Linux image,
the action that failed, and a copied diagnostic report.
