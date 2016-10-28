
title: AppRTC服务器部署资料整理
date: 2016-08-17 10:00:32
tags:
  - AppRTC
  - WebRTC
  - 音视频
  - 部署
categories:
  - WebRTC
  - AppRTC
---

# AppRTC介绍

# AppRTC服务组件

## 业务服务器 [AppRTC](https://github.com/webrtc/apprtc)

* 参数：https://appr.tc/params.html

## 信令服务器 [Collider](https://github.com/webrtc/apprtc/blob/master/src/collider/README.md)

## TURN（ICE）服务器 [Coturn](https://github.com/coturn)

# AppRTC部署过程

## 部署AppRTC [参考](https://github.com/webrtc/apprtc#deployment)
> AppRTC是需要用到[Google App Engine SDK for Python ](https://cloud.google.com/appengine/downloads#Google_App_Engine_SDK_for_Python)和[Grunt](http://gruntjs.com/)

1. 源码下载 
> git clone https://github.com/webrtc/apprtc.git

2. 

## 部署Collider [参考](https://github.com/webrtc/apprtc/blob/master/src/collider/README.md)
> Collider是GO开发的，所以需要安装Go环境，安装参考 http://golang.org/doc/install and http://golang.org/doc/code.html

1. 源码位于apprtc/src/collider/collider

2. 确定你已经设置`GOPATH`环境变量，例如：`export GOPATH=$HOME/goWorkspace`

3. 复制一份源码到$GOPATH/src
> cp -r apprtc/src/collider $GOPATH/src

4. 安装依赖性 
> go get collidermain

5. 安装 collidermain 
> go install collidermain

6. 启动 collidermain 
> $GOPATH/bin/collidermain -port=8089 -tls=false -room-server=http://47.88.32.224:8080

## 部署Coturn

1. 源码下载 `http://turnserver.open-sys.org/downloads/v4.5.0.3/`

2. 生成加密用的密钥 
> sudo openssl req -x509 -newkey rsa:2048 -keyout /usr/local/etc/turn_server_pkey.pem -out /usr/local/etc/turn_server_cert.pem -days 99999 -nodes


# 启动服务

## 启动apprtc
1. cd到apprtc目录，执行：
> dev_appserver.py --host 0.0.0.0 ./out/app_engine

## 启动collider
1. cd到$GOPATH/bin目录，执行：
> $GOPATH/bin/collidermain -port=8089 -tls=false -room-server="http://47.88.32.224:8080"

## 启动coturn

### 命令行参数启动
> turnserver -a -v -n --no-dtls --no-tls -u linzq:linzq -r "apprtc"

### 配置文件启动
> turnserver -c /etc/turnserver/turnserver.conf

### 服务启动
> service turnserver start


## 测试

* https://test.webrtc.org/

# 参考
1.[自建 AppRTC](http://www.jianshu.com/p/c55ecf5a3fcf)
2.[第六章 WebRTC服务器搭建](http://io.diveinedu.com/2015/02/05/%E7%AC%AC%E5%85%AD%E7%AB%A0-WebRTC%E6%9C%8D%E5%8A%A1%E5%99%A8%E6%90%AD%E5%BB%BA.html)
3.[实战rfc5766-turn-server和ice4j广域网通讯](http://www.hankcs.com/program/network/actual-rfc5766-turn-server-and-ice4j-wide-area-network-communication.html)
4.[WebRTC samples](https://webrtc.github.io/samples/)
