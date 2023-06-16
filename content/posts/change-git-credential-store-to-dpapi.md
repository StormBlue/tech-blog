---
title: "修改Git凭据存储模式为Dpapi"
date: 2023-06-16T10:00:38+08:00
tags:
  - 通用技术
  - Git
  - Windows
draft: false
---

### 背景
在Windows中使用Git时，有时会提示```fatal: Failed to write item to store. [0x8]```

### 原因
未知

### 解决方案
修改Git凭据存储模式，在Windows中可使用如下命令修改为Dpapi  
```shell
git config credential.credentialStore dpapi
```
