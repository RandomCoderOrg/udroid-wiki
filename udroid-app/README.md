---
description: Install and use the standalone uDroid Android app
---

# uDroid Android app

uDroid is building a standalone Android app for installing and using Linux
systems without making a terminal the main interface. The app is currently in
early development and is intended for testing rather than daily use.

{% hint style="warning" %}
Expect incomplete features and breaking changes. Keep important files backed
up while the app is in early development.
{% endhint %}

## Download the app

[Download the newest uDroid prerelease from GitHub](https://github.com/RandomCoderOrg/udroid-app/releases)
and open the `.apk` file from the release assets. Android may ask for permission
to install apps from the browser or file manager used to open it.

The source code and current development status are available in the
[uDroid app repository](https://github.com/RandomCoderOrg/udroid-app).

## Getting started

1. Open **Linux** to browse or search available systems.
2. Select a distribution or compatible official container image.
3. Review the image and start the installation.
4. Follow the normal progress view, or open the terminal panel for complete
   installation logs.
5. Select the installed system to open its status and controls page.
6. Start its terminal, desktop environment, or an installed Linux application.

Multiple Linux systems can remain installed. Each installed system has its own
page, but the current app runs one active Linux runtime and one X11 display at
a time.

## What currently works

- Installing images from uDroid, PRoot-Distro, and supported official container
  repositories.
- Resumable downloads, archive or OCI digest verification, installation
  progress, and detailed logs.
- A bundled Termux terminal emulator with a supervised Linux session.
- A bundled Termux:X11 server and display, so the separate Termux:X11 Android
  app is not required.
- Discovery and lifecycle controls for installed X11 desktop sessions.
- Direct-pointer, trackpad-style, keyboard, and native multi-touch input.
- Discovery of freedesktop `.desktop` applications inside the selected Linux
  system.
- Launching Linux applications from uDroid and pinning selected applications to
  the Android launcher.
- Update checks and verified APK downloads from the app's **About** page.

## Current limitations

- Wayland desktop sessions are not launched; desktop support currently targets
  X11 sessions.
- Multiple installed systems cannot run desktop sessions concurrently.
- Desktop compatibility varies because PRoot does not provide a normal
  systemd, logind, or hardware environment.
- General-purpose GPU acceleration is not yet a supported app feature.
- Audio integration, multiple displays, and automatic desktop recovery are
  still incomplete.

Turning off desktop compositing can significantly improve responsiveness on
some devices. See [Smooth Termux:X11 performance](../udroid-landing/setting-up-gui/smooth-desktop-performance.md)
for the existing desktop-side guidance. That guide documents the official
Termux:X11 setup; uDroid app-specific controls will be documented here as they
stabilize.

## uDroid app or the existing Termux setup?

| Choose | When it fits |
| --- | --- |
| **uDroid Android app** | You want a single graphical app that manages installation, terminals, desktops, and Linux applications. |
| **Existing uDroid scripts in Termux** | You prefer the established terminal-driven setup and direct control over Termux and Termux:X11. |

Both approaches are part of uDroid. Installing the Android app does not replace
or migrate an existing Termux installation.

## Help the project

If something fails, include the app version, Android version, selected Linux
image, and the relevant installation or runtime logs when
[filing an issue](https://github.com/RandomCoderOrg/udroid-app/issues).

You can also support development by
[starring the repository](https://github.com/RandomCoderOrg/udroid-app) or
[sponsoring the organization](https://github.com/sponsors/RandomCoderOrg).
