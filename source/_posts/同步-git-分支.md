---
title: 同步 git 分支
date: 2017-12-04 11:03:12
category:
- Develop
tags:
- git
- fork
- sync
---

### 添加上游项目 git 地址

  ```bash
  git remote add upstream {upstream-git-url}
  # {upstream-git-url} 替换为项目原始仓库地址
  ```

### 查看 git 信息

  ```bash
  git remote -v
  # 返回信息类似：
  # origin  git@github.com:YOU/YOUR-PROJECT.git (fetch)
  # origin  git@github.com:YOU/YOUR-PROJECT.git (push)
  # upstream  git@github.com:SOMEONE/UPSTREAM-PROJECT.git (fetch)
  # upstream  git@github.com:SOMEONE/UPSTREAM-PROJECT.git (push)
  ```

### 获取上游项目更新

  ```bash
  git fetch upstream
  ```

### 本地切换到主分支

  ```bash
  git checkout master
  ```

### 合并上游项目代码到本地分支

  ```bash
  git merge upstream/master
  ```
