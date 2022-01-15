---
description: creating and managing non-root users
---

# 🔓 Non-root Users

here is a step by step guide to creating a non-root user in any Linux

#### prerequisite

* A working Linux with `useradd` & `openssl` installed
* a terminal to access Linux

### Creating non-root user

there are two ways to create a non-root user ( thanks to tools in Linux ) one shows a prompt that asks all the details required & sets up everything itself and the other is more like linuxy way ( we are doing the second way cause it's good for one-liners )&#x20;

### <mark style="color:orange;">`useradd`</mark>

> useradd is a low level utility for adding users

* make sure to install OpenSSL with `apt install -y openssl`

for this guide let's say the username you want to create is **ubuntu** and the password for it is **foxy1.** add username and password to a variable to make the process easier

```bash
username="ubuntu"
password="foxy1"
```

then copy-paste the below command in your terminal

```bash
useradd -m \
    -p "$(openssl passwd -1 ${password})" \
    -G sudo \
    -d /home/${username} \
    -k /etc/skel \
    -s /bin/bash \
    $username
```

{% hint style="success" %}
Now you successfully created a non-root user
{% endhint %}

### Adding <mark style="color:blue;">`SUDO`</mark> rules for new user

you may observe that the traditional way for adding a user to the sudo group won't cause sudo daemon service can't start in proot. but adding rules to `sudoers.d` will do the job as a workaround

to do this add username to variable

```bash
username="ubuntu"
```

then add sudo rules with this command

```bash
echo $username ALL=\(root\) ALL:ALL > /etc/sudoers.d/$username
chmod 0440 /etc/sudoers.d/$username
```

{% hint style="info" %}
Now you see sudo working when you login to you new non-root user
{% endhint %}
