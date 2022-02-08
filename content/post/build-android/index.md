---
title: How to compile Android Open Source Project
description: How to build Android Open Source Project
date: 2022-02-08
slug: builder-AOSP
image: facebook_cover_photo_1.png
categories:
    - Build
    - Android Open Source Project
lastmod: '2022-02-08'
---

# 系統環境

我的是 Manjaro KDE Plasma 21.2.2 和 Arch KDE  

# 工具和依賴

> lib32-gcc-libs git gnupg flex bison gperf sdl wxgtk2 squashfs-tools curl ncurses zlib schedtool perl-switch zip unzip libxslt bc rsync ncurses5-compat-libs lib32-zlib lib32-ncurses lib32-readline lib32-ncurses5-compat-libs aosp-devel lineageos-devel  

> [openjdk](https://wiki.archlinux.org/title/java)  

# 同步 Android Open Source Project 和 device tree

- ROM [參考](https://github.com/Project-Elixir/manifest) projrct-elixir  
 - mkdir projrct-elixir && cd projrct-elixir  
 - repo init -u https://github.com/Project-Elixir/manifest -b snow  
 - repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags  

- device tree [參考](https://github.com/AOSP-12)  
- git clone https://github.com/AOSP-12/device_xiaomi_sagit.git device/xiaomi/sagit  
- git clone https://github.com/AOSP-12/device_xiaomi_msm8998-common.git device/xiaomi/msm8998-common  
- git clone https://github.com/AOSP-12/vendor_xiaomi.git vendor/xiaomi
- git clone https://github.com/AOSP-12/kernel_xiaomi_msm8998.git kernel/xiaomi/msm8998

# 修改文件

參考你要編譯 ROM device 官方倉庫
比如 [OctaviOS-Devices](https://github.com/OctaviOS-Devices)  
隨便找一個 device_xxxxx_xxxx  
把 AndroidProducts.mk 和 aosp_sagit.mk 改成官方倉庫的樣子
- aosp_sagit.mk > octavi_sagit.mk
- 打開 AndroidProducts.mk 和 aosp_sagit.mk，按照下面的來改
- PRODUCT_NAME := aosp_sagit > PRODUCT_NAME := octavi_sagit
- $(LOCAL_DIR)/aosp_sagit.mk > $(LOCAL_DIR)/octavi_sagit.mk

# 開始編譯

. build/envsetup.sh

lunch aosp_$device-userdebug

brunch $device
