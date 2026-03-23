# LineageOS-x-CLO #

How to build LineageOS-x-CLO for your device - Tutorial
==============================================

Downloading LineageOS-x-CLO Source Codes
-------------------------------

To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).


# Initialize local repository
```bash
repo init -u git@github.com:LineageOS-x-CLO/android.git -b lineage-23.0 --git-lfs
```
To save time, space and internet data during sync, use a command like this:

```bash
repo init --depth=1 -u git@github.com:LineageOS-x-CLO/android.git -b lineage-23.0 
```
# Sync
```bash
repo sync --force-sync --no-clone-bundle --no-tags
```

# Build

# Set up environment
```bash
. build/envsetup.sh
```
# Choose a target
```bash
lunch lineage_$device-bp2a-userdebug
```
# Build the code
```bash
mka bacon -jX
```
