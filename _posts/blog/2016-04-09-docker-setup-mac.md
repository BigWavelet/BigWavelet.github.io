---
layout: post
title: Mac Docker安装指南
description: 本文介绍了如何在Mac OSX上安装Docker环境 
category: blog

---



## 概述

之前都是在Linux的机器上使用Docker，今天心血来潮，想在自己的MAC上也搭建一下Docker的开发环境。这里记录一下搭建过程，有需要的小伙伴可以
参考一下。

Docker是一个C／S架构的程序，包括了服务端的docker daemon进程和客户端docker。由于Docker引擎使用了Linux内核特定的一些特性，所以要想在MAC上搭建Docker环境，需要用到虚拟机，在虚拟机中启动服务端daemon程序。

## 下载
为了简化安装过程，我们可以从官网（https://www.docker.com/products/docker-toolbox ）下载Mac docker－toolBox安装包。

## 安装
下载完成后，点击打开该docker－toolbox安装包，进行安装。安装界面如下图所示。
![install_docker](http://bigwavelet.github.io/images/post/install_docker01.png)

完成安装后，我们在dash board中可以看到如下所示的两个图标。至此，完成了MAC上Docker的安装。
![install_docker](http://bigwavelet.github.io/images/post/install_docker02.png)



	


