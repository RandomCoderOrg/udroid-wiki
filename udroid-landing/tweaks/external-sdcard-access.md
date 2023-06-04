---
description: A guide to access content of external sdcard in termux
---

# 📇 External Sdcard Access

## Prerequisites

* Android version 10 or above and termux installed.
* A PC with [<mark style="color:orange;">`android-platform-tools`</mark>](https://developer.android.com/studio/releases/platform-tools) installed. or any **adb OTG** app, is REQUIRED.
* Also, device must be connected to pc and ready for [usb debugging](https://developer.android.com/studio/debug/dev-options#enable)

{% hint style="warning" %}
It requires API LEVEL 29+, so it will not work for devices with android 9 or below.

only Android versions ( 11, 12, 13 ) are tested and working fine
{% endhint %}

## Process

{% hint style="info" %}
Assuming the user has already configured platform tools and adb in pc and connected device successfully.
{% endhint %}

### Granting permissions to termux

This method involves granting permission `WRITE_EXTERNAL_STORAGE` and `READ_EXTERNAL_STORAGE` to termux app with adb explicitly, so that termux access external storage. 

```bash
adb shell pm grant com.termux android.permission.READ_EXTERNAL_STORAGE
adb shell pm grant com.termux android.permission.WRITE_EXTERNAL_STORAGE
```

Then you need to find out the external sdcard location to change the directory. this can be done via df&#x20;
Usually, all storage devices are mounted under \`/storage\` directory, so using this

```bash
df | grep /storage | cut -d "/" -f 4-
```

It will show all mounted at `/storage`. Now the one which is in pattern line \`716D-83Z0\` is your sdcard. Or you could use Zarchiver instead to find it's codename. Then  change your directory to there and bingo you're on your external storage in termux.
