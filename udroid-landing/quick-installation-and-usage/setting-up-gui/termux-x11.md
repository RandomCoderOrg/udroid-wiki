---
description: guide for setting termux-x11 for udroid GUI
---

# setting up termux wayland

### Prerequisites

* Termux dev build from [<mark style="color:orange;">Github actions</mark>](https://github.com/termux/termux-app/actions/workflows/debug\_build.yml)<mark style="color:orange;"></mark>
* termux-x11 app from [<mark style="color:orange;">Github actions</mark>](https://github.com/termux/termux-x11/actions/workflows/debug\_build.yml)<mark style="color:orange;"></mark>

### Setting up termux

`xwayland` ( binaries for Wayland ) & `termux-x11` ( scripts to start termux-x11 app from termux ) are in `x11-repo`

```bash
pkg install x11-repo -y
pkg install xwayland termux-x11
```

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

> https://github.com/RandomCoderOrg/ubuntu-on-android ubuntu-on-android ( udroid )

> https://github.com/termux/termux-x11 Official termux-x11 repo

> https://github.com/wayland-project/wayland Official wayland sources

> https://at.projects.genivi.org/wiki/display/DIRO/Wayland+Application+on+Android Docs Wayland implementation in android
