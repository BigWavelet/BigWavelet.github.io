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

## 启动
完成tool－box的安装后，下面介绍如何启动docker。

至此，在终端中输入docker，可以看到docker的help信息，这表示我们已经完成了docker的安装，然后如果我们输入

	docker version

或者


	docker info


时，会得到如下提示信息

	yuandbdeMacBook-Air:~ yuandb$ docker info
	Cannot connect to the Docker daemon. Is the docker daemon running on this host?
	yuandbdeMacBook-Air:~ yuandb$ 
	

别着急，这表示机器上并未检测到Docker的daemon守护进程，因为该进程根本就并没有启动啊。

打开dashboard，看到如上图所示的两个图标，一个是Docker Quickstart Terminal，另一个是Kitematic（Beta）。
点击左边的
Docker Quickestart Terminal，其会打开一个终端，启动虚拟机，并开启Docker daemon守护进程，终端输出信息如下


	
	Starting "default"...
	(default) Check network to re-create if needed...
	(default) Waiting for an IP...
	Machine "default" was started.
	Waiting for SSH to be available...
	Detecting the provisioner...
	Started machines may have new IP addresses. You may need to re-run the `docker-machine env` command.
	Regenerate TLS machine certs?  Warning: this is irreversible. (y/n): Regenerating TLS certificates
	Waiting for SSH to be available...
	Detecting the provisioner...
	Copying certs to the local machine directory...
	Copying certs to the remote machine...
	Setting Docker configuration on the remote daemon...
	
	
	
	
	
	
	
	
	
	
	
	                        ##         .
	                  ## ## ##        ==
	               ## ## ## ## ##    ===
	           /"""""""""""""""""\___/ ===
	      ~~~ {~~ ~~~~ ~~~ ~~~~ ~~~ ~ /  ===- ~~~
	           \______ o           __/
	             \    \         __/
	              \____\_______/
	
	
	docker is configured to use the default machine with IP 192.168.99.100
	For help getting started, check out the docs at https://docs.docker.com


至此，完成了Docer daemon进程的启动。

接下来，我们来尝试第一个hello world

```
yuandbdeMacBook-Air:~ yuandb$ docker run ubuntu echo "hello world"
hello world
yuandbdeMacBook-Air:~ yuandb$
```

测试无误！再试一个！

```
yuandbdeMacBook-Air:~ yuandb$ docker run -it ubuntu bash
root@703a3dfa454b:/# ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
root@703a3dfa454b:/# 
```

测试无误！轻松完成MAC OSX上的Docker环境搭建

## 反馈
如果有任何疑问，欢迎交流反馈  [yuandingbo90@gmail.com]




	


