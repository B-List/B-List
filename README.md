<div align="center">

# B-List

一个高性能的 WebDAV 服务器，提供 Web 管理控制台和 WebDAV 文件共享功能。

<image src="./images/create-resource.png" width="80%">

</div>

## 功能特性

- ✅ **WebDAV 协议支持** - 完整的 WebDAV 协议实现
- ✅ **用户认证** - 支持多用户和权限管理
- ✅ **Web 管理控制台** - 现代化的 Web 界面管理
- ✅ **高性能** - 基于 Go 语言和 Gin 框架
- ✅ **轻量级数据库** - 使用 SQLite 数据库
- ✅ **Docker 支持** - 容器化部署
- ✅ **权限控制** - 读写权限分离
- ✅ **多用户支持** - 每个用户独立的根目录

## 快速开始

### 使用 Docker Compose（推荐）

``` bash
services:
  app:
    image: blist2team/b-list:latest
    container_name: b-list-app
    restart: unless-stopped
    ports:
      # HTTP 管理端口
      # - "8180:80"     
      # HTTPS 管理端口
      - "8128:8128"   
    volumes:
      - ./data:/app/data
      - ./config:/app/config
      # 挂载本地目录
      - /usb_hdd/:/webdav-storage
      # 自定义 SSL 证书
      # - /root/cert/b-list.org.crt:/b-list.org.crt
      # - /root/cert/b-list.org.key:/b-list.org.key
    environment:
      - TZ=Asia/Shanghai
```
