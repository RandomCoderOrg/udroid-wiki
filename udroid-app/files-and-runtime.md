---
description: Configure Android storage, Linux files, environment variables, and PRoot options
---

# Files, environment, and PRoot compatibility

## Android files available inside Linux

Open an installed Linux system and select **File access**. Internal shared
storage can be exposed at `/mnt/shared`, and custom mounts can map other
Android paths that uDroid can read. Stop Linux before changing mounts.

Display, audio, and graphics session mounts are managed automatically and are
added only while their owning feature needs them.

## Linux files available in Android

Android's Files app and compatible document pickers list each installed Linux
system as a read-only location with its distribution name and icon. Open the
Files navigation drawer and select the Linux system to browse or open its
files.

This is useful on Android desktop devices because Android editors, file
pickers, and productivity applications can read Linux files without exposing
the entire filesystem as shared storage. Modify those files from Linux; the
Android provider is deliberately read-only.

## Environment variables

Open **Environment variables** from the Linux system page to view or change
values used by new terminal, app, and desktop launches. Restart Linux when an
existing process needs the new values. **Reset** restores uDroid-managed values
without deleting custom variables.

## PRoot compatibility

The Linux system page includes two per-system compatibility switches:

- **System V IPC** adds PRoot's `--sysvipc` emulation for shared memory,
  semaphores, and message queues.
- **memfd compatibility** adds `--ashmem-memfd`, using Android shared memory
  when software cannot create memfd objects directly.

Both are disabled by default. Enable only the option required by an
application, then restart the Linux session. The setting applies to terminals,
desktops, and Linux applications launched for that system.

## Additional PRoot flags

Advanced users can add global PRoot arguments in:

```text
/storage/emulated/0/udroid-launch-flags.txt
```

Put one complete argument on each line. Blank lines and lines beginning with
`#` are ignored. An option and its value use two lines:

```text
-b
/storage/emulated/0/Projects:/mnt/projects
```

The file is read again for every terminal, desktop, and Linux application
launch and requires Android storage access. Arguments are added after
uDroid-managed options, so duplicates can override app defaults.

{% hint style="danger" %}
The file is intentionally unrestricted. Invalid flags can prevent every Linux
launch, and another application with all-files access could modify it. Remove
or rename the file to return to uDroid's managed launch options.
{% endhint %}

## Reset or delete a Linux system

Stop its terminal and desktop first.

- **Reset** erases the private Linux filesystem and installs a fresh copy.
- **Delete** removes the Linux system without reinstalling it.

Android folders shared with Linux are outside its private filesystem and are
not erased by reset or delete.
