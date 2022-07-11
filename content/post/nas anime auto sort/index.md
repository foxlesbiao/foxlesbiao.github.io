---
title: nas 全自动动漫下载并整理
description: nas automatic anime downloads and organizes
date: 2022-07-12
slug: nas anime auto sort
image: 
categories:
    - NAS
    - anime

lastmod: '2022-07-03'
---

# 安装 docker and edit container file

windows 直接在官网下载安装重启就可以了  

编辑 docker compose 文件，可以使用官方的 docker compose 文件 [link](https://github.com/EstrellaXD/Auto_Bangumi/tree/main/docs/docker-compose)
或者使用我的文件 [link](https://github.com/foxlesbiao/foxlesbiao.github.io/blob/main/content/post/nas%20anime%20auto%20sort/docker-compose.yml)

# 启动 dokcer 容器

```powershell
docker-compose up -d
```

# 浏览器浏览端口

qBittorrent: host:8989  
AutoBangumi: host:7892  
Plex/jellyfin: host:8096  

# jellyfin 安装

在[这里](https://hub.docker.com/r/nyanmisaka/jellyfin)下载 jellyfin Windows 
解压缩点击 jellyfin.exe 就可以了
