---
title: "Git配置代理"
date: 2023-06-16T10:10:43+08:00
tags:
  - Git
  - 通用技术
  - Flutter
draft: false
---

### 背景
如果仓库在```Github```等地方时，即使切换为```ssh```链接，通过```git```命令也可能无法
访问。  
典型的是，通过```fvm```对```Flutter```进行不同版本的安装与升级。

### 解决方案
为```git```设置代理。  
#### 设置全局代理
```shell
git config --global https.proxy http://127.0.0.1:7890
git config --global https.proxy https://127.0.0.1:7890
```

#### 取消设置全局代理
```shell
git config --global --unset http.proxy
git config --global --unset https.proxy
```

#### 对指定地址设置代理
```shell
git config --global http.http://github.com.proxy socks5://127.0.0.1:7890
git config --global http.https://github.com.proxy socks5://127.0.0.1:7890
```

#### 对指定地址取消代理
```shell
git config --global --unset http.http://github.com.proxy
git config --global --unset http.https://github.com.proxy
```

#### 配置gitconfig
```ini
#对所有请求代理 方案1
[http]
    proxy = socks5://192.168.10.120:7890
#只对github.com 方案2
[http "https://github.com"]
    proxy = socks5://192.168.10.120:7890
```
