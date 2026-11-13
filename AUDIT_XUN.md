# Xun stability audit, 2026-11-13

## Confirmed defects fixed

1. **System DLKM metadata path.** The device makefile installs modules.load directly
   in /system_dlkm/lib/modules, while the previous loader searched only inside a
   release subdirectory. The loader now supports both layouts, keeps blocklists,
   avoids loading a one-entry list twice and propagates foreground/background errors.
   [Commit e8d0628](https://github.com/Xun-Development/device_xiaomi_xun/commit/e8d0628a73cb2d610783a20161e173e2d5c3ec99).
   Shell syntax, whitespace validation and eight functional fixtures passed.
   This is not proof of missing swap: zram/zsmalloc are also in the early ramdisk load list.

2. **DolbyAtmos unavailable-effect failures.** Xun uses packages/apps/DolbyAtmos,
   a different app from fog's hardware/dolby. Failed AudioEffect construction and
   saved-state application previously escaped from persistent/background entry points.
   Services now stop cleanly without retry loops; temporary/lifecycle effect handles
   are closed. Existing error UI and an unavailable tile are used when DAP is absent.
   [Background fix 2b3b7cb](https://github.com/Xun-Development/android_packages_apps_DolbyAtmos/commit/2b3b7cbbd3bbc87306418c506bd0b18efd8b352e)
   and [UI/tile fix 41cadfc](https://github.com/Xun-Development/android_packages_apps_DolbyAtmos/commit/41cadfcc9660b601bccc3a696bca535444873213).
   Resource processing and actual Kotlin module compilation passed. Effect recovery
   requires recreating the Activity/ViewModel or tile service; no automatic retry loop
   was introduced. DAP parameters and default settings were preserved.

## Similar fog issues checked

- Shared FaceUnlock includes the camera self-join, stale-callback and model/camera/storage
  exception fixes. Xun's weak-face overlay, HAL/service contexts and facedata permissions
  are wired consistently. This manifest pins the corrected shared source.
- The real xun GKI is 5.15.194. Its bytes equal the clean AOSP common build at
  e6654bf2f6c2c3c7b6af8897baa2a86991d3b5ac; embedded config equals the real build config.
  The former fog stock-config substitution was not found.
- 267 base FCM requirements and six applicable conditional groups passed.
  SCS, strict CFI, Clang LTO, PAN/software PAN, PSI and MEMCG are enabled.
- All 469 kernel-module files and 24,770 versioned symbol imports were independently
  checked: no CRC mismatches, missing symbols or conflicting vendor CRC exports.
  An older release token in module vermagic is accepted by this versioned GKI/KMI path;
  the remaining fields and CRCs agree.
- No confirmed duplicate/ABI mismatch in the checked xun audio HAL wiring was found.

## Limits

No device runtime logs or tablet were available. The exact cause of a hypothetical
xun freeze or reboot is not established. These fixes address demonstrable code and
packaging failures; the full xun OTA has not been rebuilt or runtime-tested here.
