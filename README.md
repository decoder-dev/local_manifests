# Local manifests for fog and xun, LineageOS 24.0

The `lineage-24.0-fog` branch publishes the fog stability sources used on 2026-11-13.
It includes the existing xun/shared HAL definitions. The xun source trees are unchanged.
The changed fog, Dolby, FaceUnlock and framework projects are pinned to the revisions below.
Other LineageOS/shared projects still follow their configured upstream branches.

For a fresh source checkout:

```bash
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone https://github.com/decoder-dev/local_manifests -b lineage-24.0-fog .repo/local_manifests
repo sync -c -j8 --no-clone-bundle --no-tags
source build/envsetup.sh
breakfast fog
m bacon
```

For xun, select `breakfast xun` instead. Review the shared FaceUnlock/framework revisions before changing an existing checkout.

## Published revisions

| Project | Repository | Branch | Revision |
|---|---|---|---|
| `device/xiaomi/fog` | [device_xiaomi_fog](https://github.com/decoder-dev/device_xiaomi_fog/tree/fog-fixes) | `fog-fixes` | `4347bbd4ccfae85228c406829f0c82b1efd94e33` |
| `vendor/xiaomi/fog` | [vendor_xiaomi_fog](https://github.com/decoder-dev/vendor_xiaomi_fog/tree/fog-fixes) | `fog-fixes` | `93f5caf5e2d743d4c5eff5e2af13e2e0e0c9def7` |
| `device/xiaomi/fog-kernel` | [device_xiaomi_fog-kernel](https://github.com/decoder-dev/device_xiaomi_fog-kernel/tree/fog-fixes) | `fog-fixes` | `d31bdf2c7745f9f8dd4ed5ecef7fbf08a73ebff2` |
| `hardware/dolby` | [hardware_dolby](https://github.com/decoder-dev/hardware_dolby/tree/fog-fixes) | `fog-fixes` | `b7c92b9e9e8005a5ef8ce8d0f5ef75d6f125aa9e` |
| `packages/apps/FaceUnlock` | [platform_packages_apps_FaceUnlock](https://github.com/decoder-dev/platform_packages_apps_FaceUnlock/tree/fog-stability-20261113) | `fog-stability-20261113` | `ea3714d76796b51fb8d42fcd6748a522a7444dd5` |
| `frameworks/base` | [android_frameworks_base_fog](https://github.com/decoder-dev/android_frameworks_base_fog/tree/lineage-24.0-faceunlock) | `lineage-24.0-faceunlock` | `899b393d4395ebdecabdd06b08b1209719ecf336` |
| `kernel source (separate checkout)` | [kernel_xiaomi_sm6225](https://github.com/decoder-dev/kernel_xiaomi_sm6225/tree/Kuroha/BakaSU-update) | `Kuroha/BakaSU-update` | `83e24d23cff266c3df773710691d1b1939caab2b` |

The ROM uses `device/xiaomi/fog-kernel/Image`, not an automatic kernel-source build.
The kernel-source repository is published separately to document and retain the source of that prebuilt.

The stability OTA built successfully, including VINTF, ZIP/payload, kernel-content and AVB checks.
It has not been runtime-tested on a phone by the builder; these checks do not prove that the reported freezes are resolved.
