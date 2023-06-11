#### Quick Install (for everyone)

```bash
. <(curl -Ls https://bit.ly/udroid-installer)
```

#### Manual Install (for advanced users)
```bash
git clone https://github.com/RandomCoderOrg/fs-manager-udroid
cd fs-manager-udroid
bash install.sh
```

then use `udroid --list` to get a table of available distros and the names of their suites ( something like **jammy:xfce4** ) then use `udroid install jammy:xfce4` (or the suite you like) to install.

Here are some examples that show both install and login commands of popular distros

{% tabs %}
{% tab title="No GUI" %}
```bash
udroid install jammy:raw
udroid login jammy:raw
```

{% tabs %}
{% tab title="XFCE4" %}
```bash
udroid install jammy:xfce4
udroid login jammy:xfce4
```
{% tabs %}
{% tab title="MATE" %}
```bash
udroid install jammy:mateRaw
udroid login jammy:xfce4
```

{% tabs %}
{% tab title="KDE" %}
```bash
udroid install jammy:kdeRaw
udroid login jammy:kdeRaw
```
{% endtab %}

{% tab title="GNOME" %}
```bash
udroid install jammy:gnome
udroid login jammy:gnome
```
{% endtab %}
{% endtabs %}

#### Removing a distro

udroid cli tool has argument `remove` that takes care of wiping the suite installation from device, and `--clear-cache` option to remove any download (if present) for max release of device storage &#x20;

```
udroid remove jammy:xfce4
udroid --clear-cache
```
