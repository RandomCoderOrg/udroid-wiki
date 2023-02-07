---
description: this is how you can install udroid in termux
---

# 📖 Installation & Usage

### Before installing:-

* Get termux from [termux.com](https://termux.com) or [F-Droid.](https://f-droid.org/en/packages/com.termux/)
* [Vnc Viewer](https://play.google.com/store/apps/details?id=com.iiordanov.freebVNC), [Xserver XSDL](https://play.google.com/store/apps/details?id=x.org.server) or [Termux:X11](https://github.com/termux/termux-x11) for Display


#### Getting Sources and install scripts

```bash
# download installer
curl -L -o install.sh https://git.io/hippo-installer
# run the installer
bash install.sh
# Install ubuntu with this command
udroid --install
```

#### Uninstalling

For uninstalling rootfs you can use

```bash
proot-distro remove udroid
```

Downloaded Tarballs are stored in `$PREFIX/var/lib/proot-distro/dlcache`, you can remove it too.
