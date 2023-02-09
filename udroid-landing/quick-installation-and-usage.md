---
description: this is how you can install udroid in termux
---

# 📖 Installation & Usage

### Before installing:-

* Get termux from [termux.com](https://termux.com) or [F-Droid.](https://f-droid.org/en/packages/com.termux/)
* [Vnc Viewer](https://play.google.com/store/apps/details?id=com.iiordanov.freebVNC), [Xserver XSDL](https://play.google.com/store/apps/details?id=x.org.server), or [Termux: X11](https://github.com/termux/termux-x11) for Display

#### Quick Install

```bash
. <(curl -Ls https://bit.ly/udroid-installer)
```

Install all dependencies and the best current distro

#### From sources (manual install)

```bash
git clone https://github.com/RandomCoderOrg/fs-manager-udroid
cd fs-manager-udroid
bash install.sh
```

then use `udroid --list` to get a table of available distros and the names of their suites ( something like **jammy:xfce4** ) then use `udroid install jammy:xfce4` (or the suite you like) to install.

Here are some examples that show both install and login commands of popular distros

{% tabs %}
{% tab title="XFCE4" %}
```bash
udroid install jammy:xfce4
udroid login jammy:xfce4
```
{% endtab %}

{% tab title="GNOME" %}
```bash
udroid install jammy:gnome
udroid login jammy:gnome
```
{% endtab %}
{% endtabs %}

#### Removing a distro

udroid cli tool has argument `remove` that takes care of wiping the suite installation from device, and `--clear-cache` option to remove any download (if present) for max release of device storage &#x20;

```
udroid remove jammy:xfce4
udroid --clear-cache
```

