# twrp_device_xiaomi_davinci
TWRP device tree for Xiaomi Redmi K20 / Mi 9T

## Features

Works:

- ADB
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore
- USB OTG
- Android T Support
- Vibration support
- Decryption of /data (policy V1)

## Compile

First checkout minimal twrp with aosp tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/davinci" name="adi8900/twrp_device_xiaomi_davinci" remote="github" revision="twrp-12.1" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_davinci-eng
mka recoveryimage
```

To flash it:

```
fastboot flash recovery out/target/product/davinci/recovery.img
```

## Other Sources
LineageOS kernel

## Thanks
@mauronofrio

@pipipig233666
