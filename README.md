# Local manifests for the Redmi Pad SE (xun)

```bash
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone https://github.com/decoder-dev/local_manifests -b lineage-24.0 .repo/local_manifests
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
source build/envsetup.sh
breakfast xun
m bacon
```
