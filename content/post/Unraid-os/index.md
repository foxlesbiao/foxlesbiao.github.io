---
title: unraid installs jellyfin and auto_bangumi to download anime automatically
description: unraid 安装 jellyfin 和 auto_bangumi 自动下载动漫
date: 2022-09-11
slug: Unraid-os
image: 
categories:
    - Unraid
    - linux
    - docker
    - docker-compose
    - jellyfin
    - NAS

lastmod: '2022-09-11'
---

# jellyfin install

选择 lscr.io/linuxserver/jellyfin 

```shell
touch /boot/config/modprobe.d/ast.conf     AST
touch /boot/config/modprobe.d/i915.conf    Intel
touch /boot/config/modprobe.d/amdgpu.conf  AMD APU
touch /boot/config/modprobe.d/radeon.conf  AMD RADEON
modprobe i915 Intel
modprobe amdgpu AMD
reboot
ls /dev/dri
```
![Photo by Settings](Snipaste_2022-09-11_16-31-05.png)  
![Photo by Settings](Snipaste_2022-09-11_16-35-52.png)  

安装即可  

## auto_bangumi install
install docker-compose  
![Photo by Settings](Snipaste_2022-09-11_16-38-58.png)  

upload docker-compose.yml  
> *[office yml](https://github.com/EstrellaXD/Auto_Bangumi/tree/main/docs/docker-compose)*  

compose up

![Photo by Settings](Snipaste_2022-09-11_16-45-02.png)  
