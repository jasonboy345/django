# 第一天

## 知识点
* web的整个流程开发从前到后
* web静态网站 动态网站
* flask 搭建一个动态网站
* docker是一个软件
* docker特点 环境隔离,隔离操作系统环境,自动化部署,测试
* docker基本命令

```
查看docker版本		docker -v 
拉取镜像			docker pull 
创建一个容器		docker run -it(交互 终端) --rm(临时) -p(端口) 8090:80 -name(容器名) py3 -d(安装软件版本) python:latest /bin/bash/(稍后进入bash交互)

docker run -it --rm  -p 8090:80 -name py3 -d  python:latest /bin/bash/ 

删除容器   			docker rm 容器名
启动容器进入交互	docker start -i 容器名
启动容器        	docker start 容器名
进入容器        	docker attach 容器名
什么是镜像			类 静止的
什么是容器 			对象
docker做镜像        docker commit 镜像名
查看本地镜像        docker images
ssh端口号			22端口
https端口号			443端口
Ubuntu软件安装      更新 apt-get update 安装软件 apt-get install
wget curl
```

* git分支

```




```


## 方向

* web开发
* 网络安全和架构
	* (linux 网络编程 网络拓扑 防火墙 路由 )
	* (运维要负责,linux 开发 测试 生成环境的搭建)
* 大数据

## 任务

### 通用任务

* 阿里云注册(或者腾讯云注册)
* [阿里云docker环境安装](http://dev.aliyun.com) 
* docker中安装mysql 安装wordpress
* 本地安装docker
* 容器中安装python
* docker使用
* git分支管理用熟
* pro git前三章(版本控制 git基本操作 git分支管理)

### 大数据方向

* 拉去youku三层

### web方向

* 网页+css 
* 慕课+极客学院
* 页面还原度100% 
