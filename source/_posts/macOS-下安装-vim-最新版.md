---
title: macOS 下安装 vim 最新版
date: 2017-12-13 14:01:07
category:
- Develop
tags:
- vim
- macOS
---

### 安装 Homebrew

#### 关于 Homebrew

Homebrew 是 macOS 下最常用、最强大的软件包管理器，每一台 macOS 系统都应该安装一份。

- [Homebrew 官方网站 - https://brew.sh/](https://brew.sh/)
- [GitHub 项目地址 - https://github.com/SpaceVim/SpaceVim](https://github.com/Homebrew/brew/)

#### 安装 Homebrew

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

### 安装 vim

#### 安装前

你可以先用 `brew info vim` 命令查看一下 `vim` 安装参数，大概会得到如下结果：

```
vim: stable 8.0.1350 (bottled), HEAD
Vi 'workalike' with many additional features
https://vim.sourceforge.io/
Conflicts with:
ex-vi (because vim and ex-vi both install bin/ex and bin/view)
Not installed
From: https://github.com/Homebrew/homebrew-core/blob/master/Formula/vim.rb
==> Dependencies
Optional: lua ✘, luajit ✔, gettext ✔
==> Requirements
Required: ruby >= 1.8 ✔, perl >= 5.3 ✔
Recommended: python ✔
Optional: python3 ✔
==> Options
--with-client-server
  Enable client/server mode
--with-custom-perl
  Build with a custom Perl instead of the Homebrew version.
--with-custom-python
  Build with a custom Python 2 instead of the Homebrew version.
--with-custom-ruby
  Build with a custom Ruby instead of the Homebrew version.
--with-gettext
  Build vim with National Language Support (translated messages, keymaps)
--with-lua
  Build vim with lua support
--with-luajit
  Build with luajit support
--with-override-system-vi
  Override system vi
--with-python3
  Build vim with python3 instead of python[2] support
--with-tcl
  Build vim with tcl support
--without-perl
  Build vim without perl support
--without-python
  Build vim without python support
--without-ruby
  Build vim without ruby support
--HEAD
  Install HEAD version
```

#### 根据你的需求安装 vim

以我的需求为例：

- 我需要覆盖 macOS 系统自带的 vi 编辑器
- 我要安装 [SpaceVim](https://github.com/SpaceVim/SpaceVim)（一套非常强大的 `vim` 配置方案），而 `SpaceVim` 需要依赖 `lua` 和 `python2/3`

所以，根据我的需求，我安装 `vim` 的命令是：

```
brew install vim --with-override-system-vi --with-lua --with-python3
```
