---
title: Arch Linux Uses OneDrive
description: OneDrive
date: 2022-03-24
slug: onedrive-Linux
image:
categories:
    - Linux
    - Arch Linux
    - OneDrive
lastmod: '2022-03-24'
---

# install

> paru -S onedrive-abraunegg

## Edit config

- 同步配置  
- nano ~/.config/onedrive/config
- sync_dir = "~/OneDrive"        
- log_dir = "~/.config/onedrive/logs/"   
- sync_dir_permissions = "755"            
- sync_file_permissions = "644"

- 選擇性文件同步  
編輯 ~/.config/onedrive/sync_list 文件，一行寫一個文件夾或文件名字  

## Sync
stop auto sync  
systemctl --user disable onedrive  
systemctl --user stop onedrive  

Manual sync  
onedrive --synchronize --download-only    
onedrive --synchronize --upload-only  
