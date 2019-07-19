---
layout: page.hbs
title: 通过包管理器安装 Node.js
---

# 通过包管理器方式安装 Nodejs

***注意：*** 此页面上所有的安装包均有它们各自作者，**而非** Node.js 核心团队负责进行维护和支持。如遇任何问题，请直接向有关作者报告。 如你的问题被证实是因为 Nodejs 的缺陷引发的，维护者将直接向 Nodejs 汇报此问题。

----------------------------

* [Android](#android)
* [Arch Linux](#arch-linux)
* [基于 Linux 的 Debian 和 Ubuntu 发行版，Enterprise Linux/Fedora 和 Snap packages](#debian-and-ubuntu-based-linux-distributions-enterprise-linux-fedora-and-snap-packages)
* [FreeBSD](#freebsd)
* [Gentoo](#gentoo)
* [IBM i](#ibm-i)
* [NetBSD](#netbsd)
* [nvm](#nvm)
* [OpenBSD](#openbsd)
* [openSUSE 和 SLE](#opensuse-and-sle)
* [macOS](#macos)
* [SmartOS 和 illumos](#smartos-and-illumos)
* [Solus](#solus)
* [Void Linux](#void-linux)
* [Windows](#windows)

----------------------------

## Android

因为 Android 版的 Nodejs 目前处于实验阶段，所以当下不提供预编译版本。

但是你有一些第三方的解决方案可供选择：拿 [Termux](https://termux.com/) 来说，它为安卓提供了终端模拟器和 Linux 环境，以及内置的包管理器和 [可扩展应用集](https://github.com/termux/termux-packages)，其中包含了大量预编译的应用。在 Termux 中，以下的命令将会安装最新版 Nodejs：

```bash
pkg install nodejs
pkg install nodejs-current
```

目前，Termux 的 Node.js 二进制程序包与 `system-icu` （依赖于 `libicu` 包）相关联。

## Arch Linux

Node.js 以及 npm 包管理器在社区库中可如下方式使用：

```bash
pacman -S nodejs npm
```

<!--
If your title has non-English characters, please
put your anchor name into the comment symbol before
your real title.
-->
## <!--debian-and-ubuntu-based-linux-distributions-enterprise-linux-fedora-and-snap-packages--> 基于 Linux 的 Debian 和 Ubuntu 发行版，Enterprise Linux/Fedora 和 Snap packages

[Node.js 官方二进制发行版](https://github.com/nodesource/distributions/blob/master/README.md) 由 NodeSource 提供。

## FreeBSD

可以通过 [www/node](http://freshports.org/www/node) 获取最近的 Node.js。

通过 [pkg](https://www.freebsd.org/cgi/man.cgi?pkg) 安装二进制文件包：

```bash
pkg install node
```

或通过 [ports](https://www.freebsd.org/cgi/man.cgi?ports) 进行构建。

```bash
cd /usr/ports/www/node && make install
```

## Gentoo

可以在 portage tree 中获得 Node.js：

```bash
emerge nodejs
```

## IBM i

Node.js 长期支持版（LTS）各类版本可以通过 IBM 处获得，使用 ['yum' 包管理器](http://ibm.biz/ibmi-rpms)。包名字的组成是 `nodejs` 加上一个主版本号（举个例子，`nodejs8`，`nodejs10`，`nodejs12` 等)。

如果你要通过命令行安装 Node.js 12.x，请以\*ALLOBJ 特殊权限方式进行：
```bash
yum install nodejs12
```
Node.js 也可以通过客户端访问解决方案产品（IBM i Access Client Solutions）安装。具体参考 [支持文档](http://www-01.ibm.com/support/docview.wss?uid=nas8N1022619)。

## NetBSD

可以在 pkgsrc 目录树中获得 Node.js：

```bash
cd /usr/pkgsrc/lang/nodejs && make install
```

或者使用 pkgin 安装一个二进制文件包 (如果它支持你的系统)：

```bash
pkgin -y install nodejs
```

## nvm
Node 版本管理器是一个用于管理多个已发布的 Node.js 不同版本的 bash 脚本。它允许你执行诸如“安装”、“卸载”以及“版本切换”等诸多功能。
使用 [安装脚本](https://github.com/creationix/nvm#install-script) 安装 nvm。

对于 Unix / OS X 系统，Node.js 从源代码构建，并通过 [nvm](https://github.com/creationix/nvm) 安装到你所期望的地方。

```bash
$ env VERSION=`python tools/getnodeversion.py` make install DESTDIR=`nvm_version_path v$VERSION` PREFIX=""
```

随后你可以通过 `nvm` 在“发布版本”和“从源代码构建版本”中选择。

举个例子，如果你的 Node.js 版本是 v8.0.0-pre：

```bash
$ nvm use 8
```

一旦官方发布了版本，并且你希望卸载从源代码编译的版本，可以这样做：

```bash
$ nvm uninstall 8
```

## OpenBSD

Node.js 也可以通过 ports 系统获取。

```bash
/usr/ports/lang/node
```

在 OpenBSD 上中使用[pkg_add](http://man.openbsd.org/OpenBSD-current/man1/pkg_add.1)：

```bash
pkg_add node
```

## <!--opensuse-and-sle-->openSUSE 和 SLE

在以下安装包中，Node.js在以下主版本库中可用：

* **openSUSE Leap 42.2**: `nodejs4`
* **openSUSE Leap 42.3**: `nodejs4`, `nodejs6`
* **openSUSE Tumbleweed**: `nodejs4`, `nodejs6`, `nodejs8`
* **SUSE Linux Enterprise Server (SLES) 12**: `nodejs4`, `nodejs6`
  （“Web 和 Scripting 模块” [安装前必须添加](https://www.suse.com/documentation/sles-12/book_sle_deployment/data/sec_add-ons_extensions.html)。）

举个例子，在 openSUSE Leap 42.2 上安装 Node.js，用 root 角色运行命令：

```bash
zypper install nodejs4
```

## macOS

从 [nodejs.org](https://nodejs.org) 官网直接下载 [macOS Installer](https://nodejs.org/#download)。

_如果你想用 bash 命令下载：_

```bash
curl "https://nodejs.org/dist/latest/node-${VERSION:-$(wget -qO- https://nodejs.org/dist/latest/ | sed -nE 's|.*>node-(.*)\.pkg</a>.*|\1|p')}.pkg" > "$HOME/Downloads/node-latest.pkg" && sudo installer -store -pkg "$HOME/Downloads/node-latest.pkg" -target "/"
```

### 可替代方案

使用 **[Homebrew](http://brew.sh/)**:

```bash
brew install node
```

使用 **[MacPorts](http://www.macports.org/)**:

```bash
port install nodejs<major version>

# Example
port install nodejs7
```

使用 **[pkgsrc](https://pkgsrc.joyent.com/install-on-osx/)**:

安装二进制文件包：

```bash
pkgin -y install nodejs
```

或者通过 pkgsrc 手动构建：

```bash
cd pkgsrc/lang/nodejs && bmake install
```

## <!--smartos-and-illumos-->SmartOS 和 illumos

SmartOS 镜像随 pkgsrc 预装。在其它的 illumos 发布版中，先安装 **[pkgsrc](https://pkgsrc.joyent.com/install-on-illumos/)**，然后你可以正常安装二进制文件包：

```bash
pkgin -y install nodejs
```

或通过 pkgsrc 手动构建：

```bash
cd pkgsrc/lang/nodejs && bmake install
```


## Solus

在主版本库中，Solus 提供了 node.js。

```bash
sudo eopkg install nodejs
```


## Void Linux

在主版本库中 Void Linux 发布稳定的 node.js。

```bash
xbps-install -Sy nodejs
```

## Windows

直接通过 [nodejs.org](https://nodejs.org) 下载 [Windows Installer](https://nodejs.org/#download) 安装。

### 可替代方案

使用 **[Chocolatey](http://chocolatey.org)**:

```bash
cinst nodejs
# or for full install with npm
cinst nodejs.install
```

使用 **[Scoop](http://scoop.sh/)**:

```bash
scoop install nodejs
```
