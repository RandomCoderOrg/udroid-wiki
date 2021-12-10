---
description: guide for setting termux-x11 for udroid GUI
---

# setting up termux-x11

### Prerequisites

* Termux dev build from [<mark style="color:orange;">Github actions</mark>](https://github.com/termux/termux-app/actions/workflows/debug\_build.yml)<mark style="color:orange;"></mark>
* termux-x11 app from [<mark style="color:orange;">Github actions</mark>](https://github.com/termux/termux-x11/actions/workflows/debug\_build.yml)<mark style="color:orange;"></mark>

### Setting up termux

`xwayland` ( binaries for Wayland ) & `termux-x11` ( scripts to start termux-x11 app from termux ) are in `x11-repo`

```bash
pkg install x11-repo -y
pkg install xwayland termux-x11
```

#### Change termux properties

set property `allow-external-apps` to `true` in `~/.termux/termux.properties`

```
echo 'allow-external-apps = true' >> ~/.termux/termux.properties
```

> based on [<mark style="color:yellow;">issue 87</mark>](https://github.com/RandomCoderOrg/ubuntu-on-android/issues/87)<mark style="color:yellow;"></mark>

> Setting termux is done ✌️

### Using Termux-x11 to run `proot-distro` Linux

assuming you installed ubuntu with proot-distro with xfce4 installed

in your termux execute

```bash
termux-x11
```

this starts termux-x11 with all the required ENV variables

1. now back to termux and login to udroid with `--shared-tmp` option.&#x20;

{% hint style="info" %}
by default, Wayland socket is stored in termux `$TMPDIR` so using `--shared-tmp` bind `/tmp` in proot Linux to `$TMPDIR` of termux app
{% endhint %}

```bash
proot-distro login udroid --shared-tmp
```

1. Now export `DISPLAY` environment variable with the value `:0`&#x20;

{% hint style="info" %}
&#x20;`termux-x11` starts display at `:0` ( default )
{% endhint %}

```bash
export DISPLAY=:0
```

1. finally start your Desktop Environment ( xfce4 works better )

```bash
dbus-launch --exit-with-session startxfce4
```

That's all now if you open minimized Termux:x11 app you see xfce4 running

### Further sources

Official termux-x11 repo

{% embed url="https://github.com/termux/termux-x11" %}

&#x20;Official wayland sources

{% embed url="https://github.com/wayland-project/wayland" %}

&#x20;Docs Wayland implementation in android

{% embed url="https://at.projects.genivi.org/wiki/display/DIRO/Wayland+Application+on+Android" %}
