---
description: Installation
---

# 📖 Quick Installation and usage

### Before installing:-

* Get termux from [termux.com](https://termux.com) or [F-Droid.](https://f-droid.org/en/packages/com.termux/)
* [Vnc Viewer](https://play.google.com/store/apps/details?id=com.iiordanov.freebVNC), [Xserver XSDL](https://play.google.com/store/apps/details?id=x.org.server) or [Termux:X11](https://GitHub.com/termux/termux-x11) for Display 

#### Video tutorial

{% embed url="https://youtu.be/iVF0swfqsKo" %}

#### Getting Sources and install scripts

```bash
# download installer
curl -L -o install.sh https://git.io/hippo-installer
# run the installer
bash install.sh
# Install ubuntu with this command
udroid --install
```


#### Alt way to login
```bash
proot-distro login udroid --bind /dev/null:/proc/sys/kernel/cap_last_cap
```

#### Uninstalling 
For uninstalling rootfs you can use
```bash
proot-distro remove udroid
```
Downloaded Tarballs are stored in `$PREFIX/var/lib/proot-distro/dlcache`, you can remove it too.


