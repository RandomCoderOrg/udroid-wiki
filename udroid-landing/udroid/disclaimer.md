# ⚠️ Disclaimer




**📝 Note before trying**

* Since many of them are preinstalled, you can log in and get started right after installation.
* To install, you need 5-6 GB of free space and a stable Internet.
* Since this works on termux and on software rendering, the performance is clearly dependent on the read/write speed, CPU, RAM, and storage.
* Don't try heavy apps if you don't have a good device.
* If you have any questions or suggestions please make sure I know at https://github.com/RandomCoderOrg/ubuntu-on-android/issue (post issue)

**⚠️ Disclaimer**

* We do not work with any Ubuntu company or organization or any third party that contributed to fs (but we welcome you).
* This project works according to SElinux android. and the whole goal of the project is to just run Linux on Android without direct pivot root and this project gets better over time with your support and motivation.
* The Linux you are trying to install from this repository is not fully functional in the target space due to SElinux policies and increasing Linux requirements, and because the project is configured to run with low-level ptrace () access. in android core
* Graphics performance in vnc is poor, but it is better to experience a smooth session - this is termux: wayland app. check this [doc](https://github.com/RandomCoderOrg/ubuntu-on-android/wiki/XWayland-in-proot)
* This project comes without warranty or data protection.
* The Linux you are trying to install from this repository is not fully functional in the target space due to SELinux policies and increasing Linux requirements, and because the project is set to work with ptrace () at a low level. access in android kernel
* This leads to:
* No direct hardware access, service fluctuations, performance overhead, sudo issues, etc.

**🖥️ Display**

* The display / control of the desktop environment can be accessed in a variety of ways, for example
• Termux: Wayland **Recommended**
* xRDP
* Vncserver (RealVnc Viewer, Bvnc, Nethunter Vnc, etc.)
* Xserver XSDL

**🔊 Audio**

* Audio works by turning on the pulse server with tcp receiver module at 127.0.0.1 and the udroid manager will take care of starting the audio service (some applications require additional configuration).

**🖱️ HID Interfaces**

* Keyboard and mouse emulation depends on the applications you use to access the desktop environment. Bvnc / nethunter KEX app provides the best hardware and mouse interface.

**🌆 Graphics**

* There is currently no standardized way to access or fully utilize a GPU device, so llvm channels are used! (OpenGL version may vary depending on device OS). Most of the solutions are vendor specific performance or implementation gimmicks (such as kernel graphics / DRI support).
* The best way to experience the performance of native Linux is to use the Termux-X11 app, which is an Android port.

**🛠️ Other**

* PRoot for Android is still under development and not ready for everyday Linux use. all Linux codes and applications are not intended for PRoot. popular apps like Snap Flatpack that depend on Systemd (which is impossible without root and the Hallium project on Android) will not work. Proot on the Android platform is being developed primarily through the efforts of termux and many casual developers, as well as a significant portion of the Linux / Android user community. This project is also the result of a lot of experimentation and a combination of tricks and gimmicks to get anything up and running on Android.
