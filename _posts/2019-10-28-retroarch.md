---
layout: post
title:  "Linux 的十八般武艺"
date:   2019-10-28 03:43:50 +0800
categories: Linux
author: Certe Kim
image: https://certe.kim/img/retroarch.webp
---

### Linux的十八般武艺 课程报告
制作一个 Linux 复古游戏主机

### Linux的介绍
Linux是一种自由和开放源码的类UNIX 操作系统。
* 链接：[**维基百科**](https://zh.wikipedia.org/wiki/Linux) [**(English Page)**](https://en.wikipedia.org/wiki/Linux)

> **Linux** 是一种自由和开放源码的 **类 UNIX** 操作系统。该操作系统的内核由**林纳斯·托瓦兹**在1991年10月5日首次发布，在加上用户空间的应用程序之后，成为 Linux 操作系统。Linux 也是自由软件和开放源代码软件发展中最著名的例子。  
> *只要遵循 **GNU 通用公共许可证（GPL）** ，任何个人和机构都可以自由地使用 Linux 的所有底层源代码，也可以自由地修改和再发布。*   
> 大多数 Linux 系统还包括像提供 GUI 的 X Window 之类的程序。  
> _*除了一部分专家之外，大多数人都是直接使用 Linux 发行版，而不是自己选择每一样组件或自行设置。*_

> Linux 内核是 Linux 系统的一个非常重要的组成部分。目前， Linux 主要用于多种服务器和超级计算机等。它也被用于手机操作系统，比如 Android 操作系统是基于 Linux 内核的。  
> 在早期，Linux 作为一个免费的操作系统被用于基于 Intel ×86 的个人电脑上。因为 Linux 是一个开源操作系统，所以它的源代码可以被修改或使用，也可以在有 **GPL（通用公共许可证）** 这样许可证下被任何人发布。简而言之，如果具备一定知识，知道自己在干什么，那么任何人都可以从 Linux 那儿获得自己的操作系统。正因此，才有了许多 Linux 发行版。

### [Distribution](https://en.wikipedia.org/wiki/Linux_distribution) [(发行版)](https://zh.wikipedia.org/wiki/Linux%E5%8F%91%E8%A1%8C%E7%89%88)


**Linux 发行版**（英语：**Linux distribution**），为一般用户预先集成好的 Linux 操作系统及各种应用软件。一般用户不需要重新编译，在直接安装之后，只需要小幅度更改设置就可以使用，通常以软件包管理系统来进行应用软件的管理。Linux 发行版通常包含了包括桌面环境、办公包、媒体播放器、数据库等应用软件。这些操作系统通常由 Linux 内核、以及来自 GNU 计划的大量的函数库，和基于 X Window 的图形界面。有些发行版考虑到容量大小而没有预装 X Window，而使用更加轻量级的软件，如：busybox, uclibc 或 dietlibc 。现在有超过300个 Linux 发行版( Linux 发行版列表)。大部分都正处于活跃的开发中，不断地改进。


### 常见的 Linux 发行版：


### Android 安卓
  - Android Open Source Project(AOSP) 安卓开源计划
    - Android x86
    - Android IA
    - Cyaongen Mod
      - Cyaongen OS
      - Lineage OS
    - Mokee 魔趣开源项目
    - Android ONE
    - Android TV
    - Wear OS


### 计算机上的 Linux

#### Arch 系
  - ArchLinux
    - Manjaro
    - BlackArch
    - ArcoLinux
    - ArchBang
  - ArchLinuxARM*

> 注：ArchLinuxARM 并非由 ArchLinux.org 官方支持

#### Debian 系

- Debian
  - Ubuntu 乌班图
  - Deepin 深度
  - Kali Linux
    - Kali Linux NetHunter

#### Debian - Ubuntu 补充

  - Ubuntu 乌班图
    - Ubuntu Touch
    - Ubuntu Server
    - UbuntuKylin 优麒麟
      - NeoKylin 中标麒麟
    - Linux Mint
    - KDE Neon
      - Plasma Mobile

#### Red Hat 系

- Red Hat 红帽
  - Fedora Core
    - Fedora
      - Red Star OS 붉은별 红星
  - Red Hat Enterprise
    - CentOS

#### Enoch 系

- Enoch
  - Gentoo
    - Chrome OS
      - Chromium OS

#### Slackware 系

- Slackware
  - S.u.S.E
    - SuSE
      - SUSE
        - openSUSE

#### “其他我也不知道的系”

- 鸿蒙 Hongmeng OS、HomonOS、HMOS
- 红旗Linux

### 路由器上的 Linux
- OpenWRT
  - LEDE
  - Asuswrt
    - Merlin 梅林
- DD-WRT
- Tomato

### 参考资料
[Linux 发行版分支图](https://cooing.tech/distro.html)

### 开始正题

### 制作一个 Linux 复古游戏主机

假设你已经拥有了：
- 一个用于制作Linux主机的设备（**树莓派用户请直接跳到最后**）
- 屏幕
- 输入设备(aka Keyboard || Mouse || Joystick)
- 扬声器 / 喇叭
- 网络环境

### ArchLinux 的安装教程

1. 你去看 [**ArchWiki**](https://wiki.archlinux.org/index.php/Installation_guide_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)) 啊！

1. 你去看 [**Archlinuxarm**](https://archlinuxarm.org/platforms) 啊！

### 额外步骤
其实ArchWiki有一些东西没有强调出来，为了防止在安装之后翻车，所以有一些额外的步骤最好还是跟你们说一下比较好。

### 在 pacstrap 之前，先更换为中国境内的的源，来加速安装时下载软件的过程。

软件源的配置通过修改 **/etc/pacman.d/mirrorlist** 文件即可。

``` bash
nano /etc/pacman.d/mirrolist
```

![Alt text](https://github.com/CerteKim/BNG/blob/master/NOTE/os/linux/Base/Installation/Arch/img/mirrorlisto.png?raw=true)

在光标所在处添加

>清华Tuna源
```
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinux/$repo/os/$arch
```

>中科大源
```
Server = https://http://mirrors.ustc.edu.cn/archlinux/$repo/os/$arch
```

>[还有其他的源](https://wiki.archlinux.org/index.php/Mirrors_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E4%B8%AD%E5%9B%BD)

如图所示

![Alt text](https://github.com/CerteKim/BNG/blob/master/NOTE/os/linux/Base/Installation/Arch/img/mirrorlist.png?raw=true)

这样我们就添加好了一个清华Tuna源

按 **Ctrl+O** 写入， **Crtl+M** 保存为 UTF-8， **Ctrl+X** 退出编辑

接下来使用 pacstrap 安装 Arch

#### 安装好 pacstrap 并且配置了时区和语言之后
我们需要安装 **grub** 作为启动器来启动我们的 Archlinux，否则是不能启动的。

首先让我们安装：

``` bash
pacman -S efibootmgr grub
```

然后直接就可以按照 [**这个步骤**](https://wiki.archlinux.org/index.php/GRUB_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E5%AE%89%E8%A3%85) 来安装grub

### RetroArch 介绍

> RetroArch是一款电玩模拟器，开放源码采用GNU通用公共许可证的共享软件。 其采用类似SONY PS3游戏机的XMB界面、网络更新，统整了诸多电玩模拟器，让使用者单一一套软件中就能模拟各种游戏，同时除了电脑和安卓手机外，能透过第三方固件破解后安装在诸多游戏主机上。

### RetroArch 可以模拟的 主机

除了 ```Play Station 3``` ```Play Station 4``` ```XBOX360``` ```XBON ONE```以外的 **几乎全部**

### RetroArch 可以运行的 平台

- **Windows** 从 _Windows 95_ 到 _Windows 10_
- **Linux** (原生 以及 Flatpak)
- **Raspberry Pi** (单独适配)
- **Microsoft** _Xbox_ / _Xbox 360_ / _Xbox ONE_
- **Android**
- **Apple** _iOS_ / _Apple TV_ / _OS X_ / _macOS_
- **Sony** _PSP_ / _PSV_ / _PSTV_ / _PS2_ / _PS3_ / _PS4_
- **Nintendo** _GameCube_ / _2DS_ / _3DS_ / _Wii_ / _Wii U_ / _Switch_
- **网页浏览器** 和 **Steam Link**

### 给```pacman```包管理加入 Archlinuxcn 源

编辑 _/etc/pacman.conf_

加入
```
[archlinuxcn]
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

### 导入 GPG key

```
sudo pacman -S archlinuxcn-keyring
```

### 安装 AUR* 助手程序

```
sudo pacman -S yay
```

or

```
sudo pacman -S trizen
```

* AUR = Archlinux User Repository
> 假设你装的是 _yay_

### 安装 Xorg

```
sudo pacman -S xorg-server
```

### 安装输入驱动

```
sudo pacman -S libinput
```

### 安装开源显卡驱动

#### 检查你的设备

```
lspci | grep -e VGA -e 3D
```

#### 搜索驱动

```
pacman -Ss xf86-video
```

选择对应的包并```sudo pacman -S xf86-video*xxx```安装

### 安装闭源显卡驱动

#### Nvidia

```
sudo pacman -S nvidia nvidia-utils 
```

#### AMD

```
yay -S catalyst catalyst-libgl
```

### 安装 OpenGL

```
sudo pacman -S mesa
```

### 安装 Vulkan Runtime

```
sudo pacman -S vulkan
```

### 安装 声音设备驱动

```
sudo pacman -S alsa
```

#### 安装额外声卡固件包

```
sudo pacman -S alsa-firmware
```

#### 安装 ALSA 工具

```
sudo pacman -S alsa-utils
```

### 安装 RetroArch

```
sudo pacman -S retroarch retroarch-assets-xmb
```

### 安装 libretro Core(s)

如果你打算开启 RetroArch 联网下载功能，建议不要安装 libretro 包集

```
sudo pacman -S libretro
```

### 从独立 X 服务器 启动 RetroArch

```
sudo pacman -S xterm
startx /usr/bin/retroarch
```

### 配置 RetroArch

#### 全局配置

创建并修改 ```/etc/retroarch.cfg```
```
# 加载 retroarch-assets-xmb 主题
assets_directory = "/usr/share/retroarch/assets"
# 加载 libretro-core-info
libretro_info_path = "/usr/share/libretro/info"
# 加载 libretro cores
libretro_directory = "/usr/lib/libretro"
```

#### 导入全局配置

修改 ```~/.config/retroarch/retroarch.cfg```
```
#include "/etc/retroarch.cfg"
```

#### 用户配置

修改 ```~/.config/retroarch/retroarch.cfg```

#### 修复字体错误

复制一份 cjk 字体：例如 ```wqy-microhei```  ```noto-fonts-cjk```  ```ttf-sasara-gothic```

替换 ```/usr/share/retroarch/assets/xmb/monochrome/font.ttf``` 文件

#### 开启 RetroArch 联网下载

编辑 ```~/.config/retroarch/retroarch.cfg```

找到 ```menu_show_core_updater```

修改值为 ```true```

> 如果在之前的步骤中安装了```libretro```,请不要开启这个功能

### 让 RetroArch 成为"桌面环境"

```
yay -S retroarch-standalone-service
```

然后

```
sudo systemctl enable retroarch-standalone.service
sudo systemctl start retroarch-standalone.service
```

RetroArch 成为"桌面环境"之后

你就成功得到了一个 Linux 复古游戏主机

### 如果你是树莓派用户

从 http://www.lakka.tv/get/ 下载属于你的 Lakka OS

Lakka 包含 RetroArch 的设备：树莓派

### 后续步骤

#### 假如你已经有一个 Display Manager

添加```/etc/share/Xsession/retroarch.xsession```
```
[Desktop Entry]
Name=RetroArch
Comment=RetroArch StandAlone
Exec=/usr/bin/retroarch
TryExec=/usr/bin/retroarch
Icon=retroarch
Type=Application
```

之后从 Display Manager 中选择 RetroArch 启动

#### 假如上述步骤不成功

```
yay -S xinit-xsession
```

添加```~/.xinitrc```
```
startx /usr/bin/retroarch
```

之后从 Display Manager 中选择 RetroArch 启动

#### 输入设备无响应

```
usermod -a -G input <你的用户名>
```

### 开始今天的快乐

1. 前往 https://romsmode.com/ 下载游戏ROM文件

1. 下载对应的 libretro 核心  
  比如说我要玩 GBA 上面的 口袋妖怪
> ```
> sudo pacman -S libretro-mgba
> ```

接下来，设置一下按键直接玩就好啦
