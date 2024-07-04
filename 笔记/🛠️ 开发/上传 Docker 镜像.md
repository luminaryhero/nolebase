---
tags:
  - docker
  - docker镜像
status: 已完成
---
# 上传 Docker 镜像

1. **登录 Docker Hub**: 如果还没有账号，先在 Docker Hub 注册一个账号。然后使用 `docker login` 命令登录。
```sh
docker login
```
输入你的 Docker Hub 用户名和密码。

2. **标记镜像**: 使用 `docker tag` 命令给本地的镜像添加远程仓库的标签。
```sh
docker tag my-image:latest username/repository:tag
```
其中 `username/repository:tag` 是你在 Docker Hub 上的用户名、仓库名和标签。

3. **上传镜像**: 使用 `docker push` 命令将标记的镜像上传到 Docker Hub。
```sh
docker push username/repository:tag
```

4. **验证上传**: 在 Docker Hub 的仓库页面可以看到刚刚上传的镜像。