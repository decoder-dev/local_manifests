# Shared local manifest: fog and xun, LineageOS 24.0

Both devices are defined in one file, `manifest.xml`, on the `lineage-24.0` branch.
The same manifest is maintained in `Xun-Development/local_manifests` and
`decoder-dev/local_manifests`. Xun projects and shared dependencies are hosted in
Xun-Development; the fog device/vendor/prebuilt and its separate Dolby stack remain in decoder-dev.

For a fresh LineageOS checkout:

```bash
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone https://github.com/Xun-Development/local_manifests -b lineage-24.0 .repo/local_manifests
repo sync -c -j8 --no-clone-bundle --no-tags
source build/envsetup.sh
breakfast xun
m bacon
```

Use `breakfast fog` to select fog. Existing checkouts can update this local-manifest
repository on `lineage-24.0`; Git removes the former three XML files as part of that update.
All overrides below are pinned. The main LineageOS platform still follows its configured upstream branch.

## Published project revisions

| Project | Repository | Branch | Revision |
|---|---|---|---|
| `device/xiaomi/fog` | [decoder-dev/device_xiaomi_fog](https://github.com/decoder-dev/device_xiaomi_fog/tree/fog-fixes) | `fog-fixes` | `4347bbd4ccfae85228c406829f0c82b1efd94e33` |
| `vendor/xiaomi/fog` | [decoder-dev/vendor_xiaomi_fog](https://github.com/decoder-dev/vendor_xiaomi_fog/tree/fog-fixes) | `fog-fixes` | `93f5caf5e2d743d4c5eff5e2af13e2e0e0c9def7` |
| `device/xiaomi/fog-kernel` | [decoder-dev/device_xiaomi_fog-kernel](https://github.com/decoder-dev/device_xiaomi_fog-kernel/tree/fog-fixes) | `fog-fixes` | `d31bdf2c7745f9f8dd4ed5ecef7fbf08a73ebff2` |
| `hardware/dolby` | [decoder-dev/hardware_dolby](https://github.com/decoder-dev/hardware_dolby/tree/fog-fixes) | `fog-fixes` | `b7c92b9e9e8005a5ef8ce8d0f5ef75d6f125aa9e` |
| `frameworks/av` | [Xun-Development/android_frameworks_av](https://github.com/Xun-Development/android_frameworks_av/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `2b4b0b551df1a9b9ea6b4628af3b52c634c35a5d` |
| `packages/apps/Settings` | [Xun-Development/android_packages_apps_Settings](https://github.com/Xun-Development/android_packages_apps_Settings/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `97a3e2bc0048f82637f13bc9f6a8ec7c97335c15` |
| `device/xiaomi/xun` | [Xun-Development/device_xiaomi_xun](https://github.com/Xun-Development/device_xiaomi_xun/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `e8d0628a73cb2d610783a20161e173e2d5c3ec99` |
| `device/xiaomi/xun-kernel` | [Xun-Development/device_xiaomi_xun-kernel](https://github.com/Xun-Development/device_xiaomi_xun-kernel/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `c46837a626fb489d695013f423601b6c268d5731` |
| `vendor/xiaomi/xun` | [Xun-Development/vendor_xiaomi_xun](https://github.com/Xun-Development/vendor_xiaomi_xun/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `5f405b1d67206fa136163ec822e6ffc8eb591f28` |
| `hardware/xiaomi` | [Xun-Development/android_hardware_xiaomi](https://github.com/Xun-Development/android_hardware_xiaomi/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `6c12251713d74a01636482c9ffbdd9943addbfbf` |
| `packages/apps/DolbyAtmos` | [Xun-Development/android_packages_apps_DolbyAtmos](https://github.com/Xun-Development/android_packages_apps_DolbyAtmos/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `41cadfcc9660b601bccc3a696bca535444873213` |
| `hardware/qcom-caf/common` | [Xun-Development/hardware_qcom-caf_common](https://github.com/Xun-Development/hardware_qcom-caf_common/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `8aa1bb4889f874194f54392c19563f2b5d3ddbd9` |
| `hardware/qcom-caf/sm6225/audio/agm` | [Xun-Development/android_vendor_qcom_opensource_agm](https://github.com/Xun-Development/android_vendor_qcom_opensource_agm/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `0994e9e38fab32ffd884ad86e3ebd5c49c1139db` |
| `hardware/qcom-caf/sm6225/audio/graphservices` | [Xun-Development/android_vendor_qcom_opensource_audioreach-graphservices](https://github.com/Xun-Development/android_vendor_qcom_opensource_audioreach-graphservices/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `1d2e82222dbc35b9b2cff966281cd2b7a26d081a` |
| `hardware/qcom-caf/sm6225/audio/pal` | [Xun-Development/android_vendor_qcom_opensource_arpal-lx](https://github.com/Xun-Development/android_vendor_qcom_opensource_arpal-lx/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `e9d7a93cdffdf64f3ecd2a0dc8834c22521f6c9a` |
| `hardware/qcom-caf/sm6225/audio/primary-hal` | [Xun-Development/android_hardware_qcom_audio-ar](https://github.com/Xun-Development/android_hardware_qcom_audio-ar/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `9a14fc9162c0295239dc0a583feb2c4f63dc6dc7` |
| `hardware/qcom-caf/sm6225/data-ipa-cfg-mgr` | [Xun-Development/android_vendor_qcom_opensource_data-ipa-cfg-mgr](https://github.com/Xun-Development/android_vendor_qcom_opensource_data-ipa-cfg-mgr/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `508824715ee8d3f98d87f4d066a89016324d963f` |
| `hardware/qcom-caf/sm6225/dataipa` | [Xun-Development/android_vendor_qcom_opensource_dataipa](https://github.com/Xun-Development/android_vendor_qcom_opensource_dataipa/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `a964339653ed78a7638b391487aa63b932ce80b6` |
| `hardware/qcom-caf/sm6225/display` | [Xun-Development/hardware_qcom_display](https://github.com/Xun-Development/hardware_qcom_display/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `e09b41c709cb5e9916d767941d35c89cd3809566` |
| `packages/apps/FaceUnlock` | [Xun-Development/platform_packages_apps_FaceUnlock](https://github.com/Xun-Development/platform_packages_apps_FaceUnlock/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `ea3714d76796b51fb8d42fcd6748a522a7444dd5` |
| `external/yifan` | [Xun-Development/platform_external_yifan](https://github.com/Xun-Development/platform_external_yifan/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `b3996763c3f4bea151c52fa49a4ced2b7f4e26b8` |
| `frameworks/base` | [Xun-Development/android_frameworks_base](https://github.com/Xun-Development/android_frameworks_base/tree/lineage-24.0-xun) | `lineage-24.0-xun` | `899b393d4395ebdecabdd06b08b1209719ecf336` |

## Kernel sources

ROM builds use the two prebuilt-kernel repositories listed above. Their sources are
published separately:

- fog: [decoder-dev/kernel_xiaomi_sm6225](https://github.com/decoder-dev/kernel_xiaomi_sm6225/tree/Kuroha/BakaSU-update), `83e24d23cff266c3df773710691d1b1939caab2b`.
- xun: [Xun-Development/kernel_xiaomi_xun](https://github.com/Xun-Development/kernel_xiaomi_xun/tree/android13-5.15-xun), `e6654bf2f6c2c3c7b6af8897baa2a86991d3b5ac`.

See [AUDIT_XUN.md](AUDIT_XUN.md) for the xun findings, fixes and validation limits.
The fog stability OTA passed build/VINTF/archive/boot checks. The xun loader fixtures
and DolbyAtmos resource/Kotlin compilation passed. A full xun OTA and runtime on a
phone/tablet have not been tested by the builder; these checks do not establish that
all freezes or reboots are resolved.
