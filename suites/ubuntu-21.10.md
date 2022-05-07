---
description: ubuntu impish 21.10 @udroid
---

# Ubuntu 21.10

### Prebuild support Table

> &#x20; "-"    -> Supported but not released yet
>
> "❌"  -> Not supported
>
> "✅"  -> Supported and avalible to install

|  SUITE NAME  | XFCE4 | MATE | RAW |
| :----------: | :---: | :--: | :-: |
| UBUNTU 21.10 |   ✅   |   ✅  |  -  |

### Installation

#### XFCE4

```bash
udroid --suite impish --install xfce4
```

#### Mate

```bash
udroid --suite impish --install mate
```

#### raw

```bash
udroid --suite impish --install raw
```

### Release Notes ( v03 )

introducing udroid v3

> warning these filesystems are beta! things may be missing or lot of unwanted things all around!

![Mate](https://user-images.githubusercontent.com/68287637/151699054-af7c4a5a-46d5-411b-a0e7-0351fb7af4f8.png)

![XFCE4](https://cdn.discordapp.com/attachments/835483235517071363/923960736869384252/Screenshot\_2021-12-24\_15-27-44.png)

> we moved to ubuntu IMPISH (21.10)

* the next version of udroid comes with a new **mate** pre-build ubuntu impish made by @GxmerSam .
* ubuntu impish raw build
* new revamped udroid xfce4

### new in xfce4

* `plank` is removed in Xfce ( issues in termux-x11 while screen orientation/resolution changes )
* new xfce4 layout
* new icon pack [tela](https://github.com/vinceliuice/Tela-circle-icon-theme)
* all fonts are changed to ubuntu
* removed hardware driver packages ( for more lite fs )

#### RootFS links

| Architecture |                                                                  XFCE4                                                                 |                                                               Mate                                                              |
| :----------: | :------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|   `aarch64`  |    [Download XFCE4 arm64](https://github.com/RandomCoderOrg/ubuntu-on-android/releases/download/v3/udroid-arm64-xfce4-V3MBB2.tar.gz)   | [Download Mate arm64](https://github.com/RandomCoderOrg/ubuntu-on-android/releases/download/v3/udroid-mate-arm64-betav2.tar.gz) |
|    `amd64`   | [Download XFCE4 amd64](https://github.com/RandomCoderOrg/ubuntu-on-android/releases/download/v3/udroid-xfce4-impish-v3-build01.tar.gz) |                                                                -                                                                |

