---
description: limits & warnings
---

# ⚠ Disclaimer

### **📝 Note before trying**

* **ITS NOT MADE FOR HACKING**. Termux itself is not for hacking, you can't expect/do any kind of hacking in udroid.
* Since many of them are preinstalled, you can log in and get started right after installation.
* To install, you need 5-6 GB of free space and a stable Internet.
* Since this works on termux and on software rendering, the performance is clearly dependent on the read/write speed, CPU, RAM, and storage.
* Don't try heavy apps if you don't have a good device.
* If you have any questions or suggestions please make sure I know at `https://github.com/RandomCoderOrg/ubuntu-on-android/issue` (post issue)

### **⚠️ Disclaimer**

* We do not work with any Ubuntu company or organization or any third party that contributed to fs (but we welcome you).
* This project works according to SElinux android. and the whole goal of the project is to just run Linux on Android without direct pivot root and this project gets better over time with your support and motivation.
* Graphics performance in vnc is poor, but it is better to experience a smooth session - this is Termux: X11 app. check this [doc](https://github.com/RandomCoderOrg/ubuntu-on-android/wiki/XWayland-in-proot)
* This project comes without warranty or data protection.
* The Linux you are trying to install from this repository is not fully functional in the target space due to SELinux policies and increasing Linux requirements, and because the project is set to work using `ptrace()` at a low level access in the android kernel so this leads to. No direct hardware access, service fluctuations, performance overhead, sudo issues, etc.

### **🖥️ Display**
**📺 Viewers**
* [Termux:X11](https://github.com/termux/termux-x11) • **Recommended**
* [Xserver XSDL](https://play.google.com/store/apps/details?id=x.org.server)
* [RealVNC Viewer](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android)
* [aVNC](https://github.com/gujjwal00/avnc)
* [bVNC](https://play.google.com/store/apps/details?id=com.iiordanov.freebVNC)

**🔊 Audio**
* Audio works by running the [PulseAudio](https://www.freedesktop.org/wiki/Software/PulseAudio) server over TCP at 127.0.0.1 and the Udroid Manager will take care of starting the audio service (some applications require additional configuration).

**🖱️ HID Interfaces**
* Keyboard and mouse emulation depends on the applications you use to access the desktop environment. bVNC / Nethunter KEX app provides the best hardware and mouse interface.

### **🌆 Graphics**
* There is currently no standardized way to access or fully utilize a GPU device, so LLVM pipes are used! (OpenGL version may vary depending on device OS). Most of the solutions are vendor specific performance or implementation gimmicks (such as kernel graphics / DRI support).
* The best way to experience the performance of native Linux is to use the [Termux:X11](https://github.com/termux/termux-x11) app.

### **🛠️ Other**
* [PRoot](https://github.com/termux/proot) for Android is still under development and not ready for everyday Linux use. All Linux codes and applications are not intended for PRoot. popular apps like Snap Flatpack that depend on [`systemd`](https://en.m.wikipedia.org/wiki/Systemd#:~:text=Systemd%20is%20a%20software%20suite,space%20and%20manage%20user%20processes.) (which is impossible without root and the Hallium project on Android) will not work. [PRoot](https://github.com/termux/proot) on the Android platform is being developed primarily through the efforts of termux and many casual developers, as well as a significant portion of the Linux / Android user community. This project is also the result of a lot of experimentation and a combination of tricks and gimmicks to get anything up and running on Android.
