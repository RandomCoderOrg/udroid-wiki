---
description: A guide to install chromium
---

# 🌍 Chromium Installation

### Pre-Reading

In the newest version of ubuntu, chromium is set to be installed as a snap package and `snap` only works with `systemd` which won't start in an `proot` environment.

systemd needs to be started with PID 1 ( i.e at boot ), even if we found a hack to start systemd there are a whole lot of other problems like fuse file systems. like `proot` inability to mount images.

so workaround to install chromium is to switch to Debian repos and add an apt rule to install and upgrade chromium only from Debian repo.

{% hint style="info" %}
Don't worry we made a script to take care of the installation
{% endhint %}

### Installation

just use this line after **starting your udroid**

```bash
bash < <(curl -s https://raw.githubusercontent.com/RandomCoderOrg/udroid-app-ports/main/chromium/install.sh)
```

easy as that

![easy](../../.gitbook/assets/SpongebobDoneGIF.gif)

### Usage note

> By default, chromium is set to run without its sandbox feature cause of issues in root user and proot work better in root.&#x20;

> to run chromium as a root user from terminal user `chromium-nosandbox`&#x20;

### Extra sources

{% embed url="https://github.com/RandomCoderOrg/udroid-app-ports" %}
where we try to make scripts to solve issues like this
{% endembed %}

{% embed url="https://github.com/RandomCoderOrg/ubuntu-on-android/wiki/chromium-in-udroid" %}
old chromium installation wiki udroid
{% endembed %}
