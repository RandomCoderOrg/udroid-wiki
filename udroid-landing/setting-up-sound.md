---
description: setting up audio in termux proot environment
---

# 🔊 Audio

pulseaudio starts every time you invoke start commands with `udroid`

> You can start audio manually with this command

```bash
pulseaudio --start \
    --load="module-native-protocol-tcp auth-ip-acl=127.0.0.1 auth-anonymous=1" \
    --exit-idle-time=-1
```
