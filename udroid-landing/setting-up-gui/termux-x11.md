---
description: guide for setting termux-x11 for udroid GUI
---

# setting up termux-x11

### Prerequisites

* Get termux from [termux.com](https://termux.com) or [F-Droid.](https://f-droid.org/en/packages/com.termux/)
* termux-x11 app from [<mark style="color:orange;">Github actions</mark>](https://github.com/termux/termux-x11/actions/workflows/debug\_build.yml) <mark style="color:orange;"></mark> ( prefer downloading one with a green tick mark )
  * <img src="../../../.gitbook/assets/image (3).png" alt="" data-size="original">![](<../../../.gitbook/assets/image (2).png>)

### Setting up termux

`xwayland` ( binaries for Wayland ) is in `x11-repo` & `termux-x11` ( available as zip in action builds )

```bash
pkg install x11-repo -y
pkg install xwayland termux-x11
```

#### Change termux properties

set property `allow-external-apps` to `true` in `~/.termux/termux.properties`

```
echo 'allow-external-apps = true' >> ~/.termux/termux.properties
termux-reload-settings
```

{% hint style="info" %}
Recommended to restart termux
{% endhint %}

#### Installing termux-x11 starter

The zip you installed from[ STEP 2](termux-x11.md#prerequisites) contains a `.deb` file. to start `termux-x11` the server we need to install it in `termux` session

```
termux-setup-storage
cp /sdcard/Download/termux-x11.zip ~
unzip termux-x11.zip
cd termux-x11
dpkg -i --force-depends termux-x11.deb
```

Setting termux is done ✌️

### Using Termux-x11 to run `proot-distro` Linux

assuming you installed ubuntu with proot-distro with xfce4 installed, in your termux execute

```bash
termux-x11
```

this starts termux-x11 with all the required ENV variables

{% hint style="info" %}
by default, the Wayland socket is stored in termux `$TMPDIR` so using --shared-tmp binds `/tmp` in proot Linux to `$TMPDIR` of termux app \[ udroid manages to do this by default )
{% endhint %}

Log in to your favorite udroid distro

```bash
udroid -l xfce4
```

Now export `DISPLAY` environment variable with the value `:0`&#x20;

```bash
export DISPLAY=:0
```

finally, start your Desktop Environment ( xfce4 works better )

```bash
dbus-launch --exit-with-session startxfce4
```

That's all now if you open minimized Termux:x11 app you see xfce4 running

### Further sources

Official termux-x11 repo

{% embed url="https://github.com/termux/termux-x11" %}

&#x20;Official wayland sources

{% embed url="https://github.com/wayland-project/wayland" %}

#### Check this section for suites

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}
