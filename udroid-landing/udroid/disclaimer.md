# 👀 Disclaimer



### Note & Disclaimer!

**A note before you try**

* As lot of it is preinstalled you can login and start right after you install.
* Before installation, be sure that you're on stable internet and your device have 5-6gb free space for neat installation.
* As this runs on termux and on software rendering so performence clearly depends on CPU, ram and storage read-write speed!
* Consider not to try heavy apps unless you got a good device.
* If you have any issues or suggestions make sure i know at https://github.com/RandomCoderOrg/ubuntu-on-android/issue (create an issue)

**Disclaimer**

* we don't work with any company or organization of ubuntu or any third-party sources that took in making fs(but we are welcome).
* This project works by complying with SElinux android. and all aim of the project is just to run Linux on android without direct root with a twist and this project improves time by time with your support and motivation.
* the Linux you trying to install from this repo is not fully functional in the target space because of the SElinux policies, and increasing requirement in Linux requirements and also because the project is set to run with `ptrace()` a low-level access in android kernel
* Graphic performance is bad in vnc but a better to experience a smooth session is termux:wayland app. check this [doc](https://github.com/RandomCoderOrg/ubuntu-on-android/wiki/XWayland-in-proot)&#x20;
* **(Update)** see https://github.com/RandomCoderOrg/ubuntu-on-android/wiki/XWayland-in-proot to run a smooth and fast session
* This project comes without warranties or data protection
* The Linux you're trying to install from this repo is not fully functional in the target space because of the SELinux policies, and increasing requirement in Linux requirements, and also because the project is set to run with ptrace() low-level access in android kernel
* That lead to:
* No direct access to hardware, fluctuations in services, performance overheads, sudo issues etc.

**Display**

* Access to display/control Desktop environment can be accomplished by various methods like
* Termux:Wayland **Recommended**
* xRDP
* Vncserver ( RealVnc Viewer, Bvnc, Nethunter Vnc etc )
* Xserver XSDL

**Audio**

* Audio works by enabling pulseserver with a tcp reciver module at `127.0.0.1` and `udroid` manager takes care on starting audio service ( additional setup mamy require for some apps ).

**HID interfaces**

* Keyboard and mouse emulation depends on apps you use to access desktop environment. Bvnc/nethunter KEX app provides better interface with hardware and mouse

**Graphics**

* For this time being there is no standardized way of accessing or using device GPU at its full potential so llvm pipes are used! (OpenGL version may depend on device OS). Most of the solutions are tricks to get more performence or vendor specific implementaions (like kernel graphics support layer/DRI ).
* Best way to experience native Linux like performence is using Termux:Wayland app which is wayland port to android

**Others**

* PRoot for android is still in developing stage and not ready for using daily life linux. all the linux codes and apps are not devoloped for PRoot. popular apps like snap flatpack which depends on Systemd (which is not possible without root and Hallium project in android) wont work. proot on android platform is devoloping mostly by the efforts of termux and many random devolopers and a big part of linux/android user community. this projects is also result of so many experiments and a mixture of hacks and tricks to start things in android.
