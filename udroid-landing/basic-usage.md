---
description: udroid command line options for basic usage
---

# 👩‍💻 Basic Usage

| **Command**           | **Usage**                                         |
| --------------------- | ------------------------------------------------- |
| `udroid -l <DE_name>` | To Login to specific distro                       |
| `udroid -S`           | to upgrade fs or to get new features if available |
| `udroid -i <DE_name>` | To install udroid suite of DE name specified      |

**Environment Variables**

* `OVERRIDE_REMOTE_PLUGIN_DIR` to point plugin directory name for the installation
* `UDROID_SUITE` to change default suite name for login

> refer [https://github.com/RandomCoderOrg/ubuntu-on-android/tree/modified/pd-plugins](https://github.com/RandomCoderOrg/ubuntu-on-android/tree/modified/pd-plugins)\
> for directory name

#### Examples

* To install default `xfce4` distro

```bash
udroid -i xfce4
```

* To install a different suite `impish`

```bash
export OVERRIDE_REMOTE_PLUGIN_DIR=impish
export UDROID_SUITE=impish
udroid -i xfce4
udroid -l xfce4
```

{% hint style="info" %}
by default /tmp is shared with termux and dbus fix is hardcoded
{% endhint %}
