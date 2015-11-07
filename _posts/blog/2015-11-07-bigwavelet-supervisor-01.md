---
layout: post
title: Supervisor使用心得
description: 简述了Supervisor的使用心得，方便新手快速上手使用 
category: blog

---

## 概述
相信在做后端的同学经常会碰到要跑一些守护进程的情况，那这种情况下应该怎么办呢？tmux么？关掉shell服务岂不就挂掉了？那样太不爽啦。。。

因此，本文介绍的主角supervisor就该登场啦。supervisor是一个CS架构的工具，包括服务器程序和客户端程序两个部分。服务端程序为supervisord
主要用于管理进程信息，响应客户端的请求。客户端的程序supervisorctl，主要用户与不同的supervisord通信，获取查看并操作进程信息。详细信息可以参考 ／(http://supervisord.org).

## 安装

（以下适用于linux用户）
    pip install -U supervisor




