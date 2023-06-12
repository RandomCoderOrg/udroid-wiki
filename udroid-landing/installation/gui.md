
## VNC (Virtual Network Computing)
VNC stands for Virtual Network Computing. It is across-platform screen sharing system that was created to remotely control another computer. This means that a computer's screen, keyboard, and mouse can be used from a distance by a remote user from a secondary device as though they were sitting right in front of it. It is the primary method used by udroid for GUI.
### For beginners
Udroid comes with scripts (`startvnc` and `stopvnc`) to start or stop vnc server with ease.
After creating a server, open a VNC viewer app and connect to `localhost:1`

### For advanced users
You can customise the resolution, change startup session, etc.

```bash
tigervncserver \
    -geometry 2560x1080 \
    -xstartup /usr/bin/xfce4-session \
    -listen tcp :1 
```

## Display over other devices

It is possible to forward the server to other device, if connected in same network. First start vncserver with localhost disabled.
```bash
tigervncserver \
    -geometry 2560x1080 \
    -localhost no \
    -xstartup /usr/bin/xfce4-session \
    -listen tcp :1 
```

And in another device use `WLAN IP:port` for connecting. ( use `ip a` in termux and copy the 192.168.xx.xx)

## Setting up xRDP

RDP is another great way to get gui, even much better input and resolution setups automatically. For using it first install xRDP. (note it'll use VNC for backend and might bugs while rendering).

```
sudo apt install xRDP
```

Now need to configure a bit, first need to create xsession.

```bash
echo "xfce4-session > ~/.xsession
```

The second file we need to edit is the startup file for XRDP, so it will start the desktop.

```bash
nano /etc/xrdp/startwm.sh
```

Delete all the content there and paste this: #!/bin/sh

```bash
if [ -r /etc/default/locale ]; then
  . /etc/default/locale
  export LANG LANGUAGE
fi

xfce4-session 
```



Now start xRDP with

```
sudo service xrdp start
```

Connect it to `localhost:3389` with RDP client.

##

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
