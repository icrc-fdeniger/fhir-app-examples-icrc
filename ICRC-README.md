new host file to import:
```
127.0.0.1       localhost
::1             ip6-localhost
10.0.2.2 local.dcmsaccess.org
```

To be able to change `/etc/hosts`:

```bash
adb root
> adb shell avbctl disable-verification
Successfully disabled verification. Reboot the device for changes to take effect.
> adb disable-verity
using overlayfs
Successfully disabled verity
Now reboot your device for settings to take effect
> adb reboot
> adb root && adb remount
remount succeeded
> adb push hosts /etc
> adb reboot
```

instead of `adb push` you can use `Device Explorer` view from IntelliJ.