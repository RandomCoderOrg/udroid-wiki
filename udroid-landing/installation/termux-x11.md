---
description: guide for setting termux-x11 for udroid GUI
---

# Termux:X11
Termux:X11 is a termux addon providing android frontend for xwayland. It uses Wayland display protocol, which is aimed to become the successor of the X Window System. Note that it is not a fully fledged wayland server, its like a X system in wayland.

### 1.  How does it work?

Through its companion package, the executable creates socket through $XDG_RUNTIME_DIR in Termux directory by default.

The wayland sockets is the way for the graphical applications to communicate with. Termux X11 applications do not have wayland support yet, this kind of setup may not be straightforward and therefore additional packages should be installed in order for X11 applications to be run in Termux:X11.



### 2. Requirements

* Termux from workflows builds
* Termux:x11 companion app from [<mark style="color:orange;">Github actions</mark>](https://github.com/termux/termux-x11/actions/workflows/debug\_build.yml) <mark style="color:orange;"></mark> ( prefer downloading one with a green tick mark )
  * <img src="../../../.gitbook/assets/image (3).png" alt="" data-size="original">![](<../../../.gitbook/assets/image (2).png>)

### 3. Setup Instructions

Get xwayland and termux-x11 from x11 repository

```bash
pkg install x11-repo -y
pkg install xwayland termux-x11
```

Set property `allow-external-apps` to `true` in `~/.termux/termux.properties`

```
echo 'allow-external-apps = true' >> ~/.termux/termux.properties
termux-reload-settings
```

{% hint style="info" %}
Recommended to restart termux
{% endhint %}

The zip you installed from[ STEP 2](termux-x11.md#prerequisites) contains a `.deb` file. to start `termux-x11` the server we need to install it in `termux` session

```
termux-setup-storage
cp /sdcard/Download/termux-x11.zip ~
unzip termux-x11.zip
cd termux-x11
dpkg -i --force-depends termux-x11.deb
```


### 4. Using Termux-x11 to run udroid

Assuming you installed ubuntu with proot-distro with xfce4 installed, in termux session execute

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

### 5. Troubleshooting
will be updated soon... 

### References

Official termux-x11 repo

{% embed url="https://github.com/termux/termux-x11" %}

&#x20;Official wayland sources

{% embed url="https://github.com/wayland-project/wayland" %}

#### Check this section for suites

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}
