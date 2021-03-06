# 微服务完整集群部署引导

项目主要是这次[微服务系列实践](https://github.com/zengqinglei/microservice-deploy/wiki)的完整集群部署方案，docker 编排的镜像用意都可以在文章中找到介绍。

## 完整部署架构图


1. centos-02：192.168.0.102 应用集群节点-2
2. centos-03：192.168.0.103 应用集群节点-3
3. ubuntu-04：192.168.0.104 应用集群节点-4
4. ubuntu-05：192.168.0.105 数据库节点-5

![main-1](https://user-images.githubusercontent.com/7374317/50370193-2f3dc780-05dd-11e9-960d-5d8efcd32cef.png)

![mic-service-arc](https://user-images.githubusercontent.com/7374317/50370197-3f55a700-05dd-11e9-986d-442db78258ea.png)

## 部署引导教程

本部署教程需要一定运维、开发知识体系，如果在实践过程中遇到各种问题，可以在issues 提出你的问题，我会尽快帮你们解答。

### 推荐部署条件

* 3台服务器保证高可用
* 服务器硬件推荐：4核8G内存
* 云环境：可使用云环境提供的负载代替keepalived，否则需要申请虚拟IP

### 部署步骤
1. 将对应的文件夹下载到各自对应IP的服务器中
2. 配置 Makefile 文件中配置
3. 启动所有镜像：make run
4. 停止所有镜像：make stop
