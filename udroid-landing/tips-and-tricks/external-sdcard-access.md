---
description: A guide to access content of external sdcard in termux
---

# 📇 External Sdcard Access

## Prerequisites

* An android device with version 10 or above with termux installed
* A pc with [<mark style="color:orange;">`android-platform-tools`</mark>](https://developer.android.com/studio/releases/platform-tools) installed. or any **adb OTG** app
* Also, android device is connected to pc and ready for [usb debugging](https://developer.android.com/studio/debug/dev-options#enable)

{% hint style="warning" %}
This method only works with Android version 10 or above with API LEVEL 29+

only Android versions ( 11, 12, 13 ) are tested and working fine
{% endhint %}

## Process

{% hint style="info" %}
Assuming the user has already configured platform tools and adb in pc and connected device successfully
{% endhint %}

### Granting permissions to termux

this method involves granting permission `WRITE_EXTERNAL_STORAGE` and `READ_EXTERNAL_STORAGE` to termux app with adb explicitly. in your command prompt execute

```bash
adb shell pm grant com.termux android.permission.READ_EXTERNAL_STORAGE
adb shell pm grant com.termux android.permission.WRITE_EXTERNAL_STORAGE
```

Then you need to find out the external sdcard location to change the directory. this can be done by df&#x20;

usually, all storage devices are mounted under \`/storage\` directory so using this

```bash
df | grep /storage | cut -d "/" -f 4-
```

this show all mounted at /storage. Now the one which is in pattern line \`716D-83Z0\` is your sdcard. change your directory to there and vola you can access external sdcard
