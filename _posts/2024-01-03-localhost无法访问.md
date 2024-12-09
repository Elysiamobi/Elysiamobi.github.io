---
date created: 2024-01-03 10:22
date updated: 2024-01-11 15:13
tags:
  - WSL
---


> [\wsl.localhost 无法访问_wsl 你可能没有权限使用网络资源-CSDN博客](https://blog.csdn.net/qq_42059060/article/details/130945732)

但还是有个问题，重启后问题回复现，有点麻烦
## `\\wsl.localhost 无法访问`

在打开Windows 资源管理器侧边栏wsl2的时候报错：

![img](https://img-blog.csdnimg.cn/img_convert/9879b8e5ad863ebc70c57f58efbf5ccd.webp?x-oss-process=image/format,png)

> \wsl.localhost 无法访问。你可能没有权限使用网络资源。请与这台服务器的管理员联系以查明你是否有访问权限。

系统资源不足，无法完成请求的服务。

将注册表`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\NetworkProvider\Order`

和`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\NetworkProvider\HwOrder`

两个键值中`ProviderOrder`的值从 `cbfs6,P9NP,RDPNP,LanmanWorkstation,webclient` 改为 `P9NP,RDPNP,LanmanWorkstation,webclient`

![image-20230421181915179](https://img-blog.csdnimg.cn/d9f850fa3b4a45a4b7bb5cb46ea67234.png)
