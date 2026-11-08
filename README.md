# crDroid-x-CLO #

crDroid 17.0 features on top of [LineageOS-x-CLO](https://github.com/LineageOS-x-CLO)
(LineageOS 24.0 rebased onto Qualcomm CodeLinaro `LA.QSSI.17.0` sources).

> **Status: experimental / not build-tested yet.**

How it is put together
----------------------

* Repositories that both crDroid and LineageOS-x-CLO modify are forked here, on branch `17.0`.
  Each one is LineageOS-x-CLO `lineage-24.0` with crDroid `17.0` merged in.
* `vendor/lineage` is crDroid's `vendor_crdroid`, with LineageOS-x-CLO's `vendor_lineage` changes merged in.
* crDroid-only apps and services are pulled straight from [crdroidandroid](https://github.com/crdroidandroid).
  See `snippets/crdroid-x-clo.xml`.
* Everything else comes from LineageOS-x-CLO, LineageOS and CodeLinaro, exactly as upstream.

Not ported yet: crDroid's changes to `art`, `external/bouncycastle`, `external/jemalloc_new`,
`frameworks/opt/net/wifi` and `system/memory/libmeminfo`. These use the CLO versions for now.

Credits: [LineageOS-x-CLO](https://github.com/LineageOS-x-CLO), [crDroid](https://github.com/crdroidandroid),
[LineageOS](https://github.com/LineageOS), [CodeLinaro](https://git.codelinaro.org/clo/la).

Downloading the source
----------------------

```bash
repo init -u https://github.com/crDroid-x-CLO/android.git -b 17.0 --git-lfs
```

To save time, space and data:

```bash
repo init --depth=1 -u https://github.com/crDroid-x-CLO/android.git -b 17.0
```

```bash
repo sync --force-sync --no-clone-bundle --no-tags
```

Building
--------

```bash
source build/envsetup.sh
brunch devicecodename
```
