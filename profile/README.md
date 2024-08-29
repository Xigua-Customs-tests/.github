# Build LineageOS for OnePlus Ace 2 Pro

## Prerequisites
- refer to [AOSP](https://source.android.com/docs/setup/start/requirements)

## Build
1. Initialise repo with [LineageOS](https://github.com/LineageOS/android) source code.
    ```
    repo init -u https://github.com/LineageOS/android.git -b lineage-21.0 --git-lfs
    ```

2. Clone [local_manifests](https://github.com/Xigua-Customs-tests/local_manifests)
    ```
    git clone https://github.com/Xigua-Customs-tests/local_manifests -b lineage-21 .repo/local_manifests
    ```

3. Sync
    ```
    repo sync -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
    ```

4. Build
    ```
    . build/envsetup.sh
    lunch lineage_xigua-ap2a-userdebug
    mka bacon
    ```
    Compiling source can take anywhere from 30 mins - 4hrs depending on how powerful your hardware is,
    After successful build, you can find your flashable rom zip at ```out/target/product/aston/```
