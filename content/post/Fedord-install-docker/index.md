---
title: Fedord install docker
description: Fedord install docker
date: 2022-09-06
slug: Fedora-install-docker
image: 
categories:
    - Fedord
    - linux
    - docker
    - docker-compose

lastmod: '2022-09-06'
---

# install
```shell
sudo dnf -y install dnf-plugins-core

sudo dnf config-manager \
    --add-repo \
    https://download.docker.com/linux/fedora/docker-ce.repo
    
sudo dnf install containerd.io docker-compose-plugin docker-compose

sudo systemctl start docker

docker -v 

docker-compose -v
```

# User Groups
```shell
sudo groupadd docker

sudo usermod -aG docker alicefox

newgrp docker 
```
