# 📖 Installation & Usage

### Before installing:-

* Get termux from [termux.com](https://termux.com) or [F-Droid.](https://f-droid.org/en/packages/com.termux/)
* [Vnc Viewer](https://play.google.com/store/apps/details?id=com.iiordanov.freebVNC), [Xserver XSDL](https://play.google.com/store/apps/details?id=x.org.server), or [Termux: X11](https://github.com/termux/termux-x11) for Display

### Quick Install

{% hint style="info" %}
Install all dependencies and developer-selected Distro
{% endhint %}

```bash
. <(curl -Ls https://bit.ly/udroid-installer)
```

#### From sources (manual install)

```bash
apt update && apt install git -y
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

### Removing a Distro

udroid cli tool has an argument `remove` that takes care of wiping the suite installation from the device, and `--clear-cache` option to remove any download (if present) for max release of device storage &#x20;

{% code title="Example:" fullWidth="false" %}
```bash
udroid remove jammy:xfce4
udroid --clear-cache
```
{% endcode %}

