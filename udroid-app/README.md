---
description: Install and use the standalone uDroid Android app
---

# uDroid Android app

uDroid installs and runs Linux systems from one Android app. It manages Linux
images, terminals, X11 desktops, installed applications, storage, audio, and
device-specific compatibility options without requiring root.

{% hint style="warning" %}
The app is in early testing. Expect incomplete features and breaking changes,
and keep important Linux files backed up.
{% endhint %}

## Download the app

[Download the newest prerelease from GitHub](https://github.com/RandomCoderOrg/udroid-app/releases),
then open the `.apk` asset. Compare it with the attached `SHA256SUMS` before
installing. Android may ask for permission to install apps from the browser or
file manager used to open it.

The source and issue tracker are in the
[uDroid app repository](https://github.com/RandomCoderOrg/udroid-app).

## Main areas

| Area | Use it for |
| --- | --- |
| **Home** | See the active Linux system and open common actions. |
| **Linux** | Install, open, reset, or delete Linux systems. |
| **Terminal** | Run commands, install packages, and manage terminal tabs. |
| **Apps** | Open graphical or terminal applications installed in Linux. |
| **About** | Check for updates, get support, and inspect diagnostic logs. |

Some areas appear only after a Linux system is installed. **Device
compatibility** on Home shows which optional features are available before you
change graphics settings.

## Install a Linux system

1. Open **Linux** and choose a distribution.
2. Review its download size and file access.
3. Select **Download image**.
4. Follow the installation stages until **Linux is ready**.
5. Select **Open terminal**.

You can leave the page while installation continues. Its notification returns
to the same installation page. A paused download resumes without starting from
zero. If installation stops, read the active-stage message and open **View
install log** before selecting **Try again**.

Multiple Linux systems can stay installed. Each has its own controls and
settings, but uDroid currently runs one active Linux runtime and one X11
display at a time.

## User guides

- [Terminal and appearance](terminal.md)
- [Desktops, applications, input, and audio](desktop.md)
- [Files, environment, and PRoot compatibility](files-and-runtime.md)
- [Updates and troubleshooting](troubleshooting.md)

## Current limitations

- Wayland sessions are not supported yet; desktop sessions currently use X11.
- PRoot is not a virtual machine. Docker, LXC, Snap, Flatpak sandboxes,
  systemd services, and software requiring privileged kernel features may not
  work.
- Desktop and graphics compatibility varies by device. Graphics acceleration
  is experimental; Venus, VirGL, ANGLE, or Mali profiles may work on compatible
  hardware. Turnip is not supported yet.
- Multiple Linux systems cannot run desktop sessions concurrently.

The Android app and the existing Termux-based uDroid setup are separate. The
app does not replace or migrate an existing Termux installation.

## Get help

When [filing an issue](https://github.com/RandomCoderOrg/udroid-app/issues),
include the app version, Android version, phone model, selected Linux image,
and the relevant installation or runtime logs.
