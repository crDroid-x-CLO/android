# crDroid-x-CLO #

crDroid 17.0 features on top of [LineageOS-x-CLO](https://github.com/LineageOS-x-CLO)
(LineageOS 24.0 rebased onto Qualcomm CodeLinaro `LA.QSSI.17.0` sources).

> **Status: experimental / not build-tested yet.**

How it is put together
----------------------

* Repositories that both crDroid and LineageOS-x-CLO modify are forked here, on branch `17.0`.
  Each one is LineageOS-x-CLO `lineage-24.0` with crDroid `17.0` merged in.
* `vendor/lineage` is crDroid's `vendor_crdroid`, with LineageOS-x-CLO's `vendor_lineage` changes merged in.
* `art`, `external/bouncycastle`, `frameworks/opt/net/wifi` and `system/memory/libmeminfo` come from
  CodeLinaro in LineageOS-x-CLO. Here they are CodeLinaro's pinned revision with crDroid's own commits
  cherry-picked on top.
* crDroid-only apps and services are pulled straight from [crdroidandroid](https://github.com/crdroidandroid).
  See `snippets/crdroid-x-clo.xml`.
* Everything else comes from LineageOS-x-CLO, LineageOS and CodeLinaro, exactly as upstream.

Not ported: crDroid's `external/jemalloc_new`. It is a different jemalloc snapshot rather than a
patch series, and nothing in the tree depends on it, so the CodeLinaro version is used.

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
