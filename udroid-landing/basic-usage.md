---
description: udroid command line options for basic usage
---

# 👩‍💻 Basic Usage

| **Command**                | **Usage**                                                                                                               |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `udroid`                   | To login to shell                                                                                                       |
| `udroid upgrade`           | to upgrade fs or to get new features if available                                                                       |
| `udroid --enable-dbus`     | To start udroid with dbus hack enabled                                                                                  |
| `udroid --enable-dbus-vnc` | To start vnc session with dbus hack enabled                                                                             |

**Environment Variables**

* `DEFAULT_VNC_PORT` to set vnc port for scripts
* `HIPPO_BRANCH` to set custom branch for cloning code

## Alt way to login

```bash
proot-distro login udroid --bind /dev/null:/proc/sys/kernel/cap_last_cap
```
