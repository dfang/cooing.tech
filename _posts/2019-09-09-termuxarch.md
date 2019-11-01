---
layout:	post
title:	"Termux Arch"
date: 2019-09-09 00:03:03 +0800
categories: linux
author: Certe Kim
image: https://raw.githubusercontent.com/TermuxArch/imgsTermuxArch/master/IMG_20171019_190414.jpg
---

# Termux 上通过 proot 安装 Arch
> 来自 SDRausty 的[**这个 repo**](https://github.com/SDRausty/TermuxArch)

## 安装 Termux
略

## 准备脚本
```
wget https://raw.githubusercontent.com/SDRausty/TermuxArch/master/setupTermuxArch.sh
chmod +x setupTermuxArch.sh
```

## 安装
```
./setupTermuxArch.sh
```

## 后续步骤
### 更新 archlinux-keyring
Please follow ArchWiki 的 [这篇文章](https://wiki.archlinux.org/index.php/Pacman/Package_signing)
