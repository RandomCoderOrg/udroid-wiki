---
description: udroid command line options for basic usage
---

# 👩‍💻 Basic Usage

| **Command**                               | **Usage**                                         |
| ----------------------------------------- | ------------------------------------------------- |
| `udroid -l <DE_name>`                     | To Login to specific distro                       |
| `udroid -S`                               | to upgrade fs or to get new features if available |
| `udroid -i <DE_name>`                     | To install udroid suite of DE name specified      |
| `udroid --suite <suite name> [ options ]` | to install different suites                       |

**Environment Variables**

* `OVERRIDE_REMOTE_PLUGIN_DIR` to point plugin directory name for the installation
* `UDROID_SUITE` to change the default suite name for login

> refer [https://github.com/RandomCoderOrg/ubuntu-on-android/tree/modified/pd-plugins](https://github.com/RandomCoderOrg/ubuntu-on-android/tree/modified/pd-plugins)\
> for directory name

#### Examples

* To install default stable `xfce4` distro

```bash
udroid -i xfce4
```

* To install a different suite ( for example: `impish` )&#x20;

```bash
udroid --suite impish -i xfce4
udroid --suite impish -l xfce4
```

{% hint style="info" %}
by default /tmp is shared with termux and dbus fix is hardcoded
{% endhint %}
