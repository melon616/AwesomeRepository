
# 1. 配置镜像源
添加下面字段到：/etc/docker/daemon.json  
[镜像源](https://1ms.run/)
```shell
{
  "registry-mirrors": [
    "docker.1ms.run"
  ]
}
```

# 2. Docker操作
```shell
# 查看所有镜像
docker images
# 构建镜像
docker build --tag draw_example .
# 强制删除镜像
docker rmi -f image_id

# 基于镜像创建并启动一个新的容器
docker run -it <image_id> /bin/bash
# 进入已有容器中运行
docker exec

# 查看正在运行的容器
docker ps -a
docker stop {container_id}
docker rm {container_id}
```

## 2.1 docker run
| 参数                         | 说明                                                                 |
|------------------------------|----------------------------------------------------------------------|
| `-d`                         | 后台运行容器（detached mode）                                        |
| `-it`                        | 交互式运行容器，并打开终端（Interactive + Terminal）                |
| `--name 容器名`               | 给容器指定一个名字                                                   |
| `-p 主机端口:容器端口`        | 端口映射，例如 `-p 8080:80`                                          |
| `-v 主机路径:容器路径`        | 卷挂载，把主机目录挂到容器里，例如 `-v /data:/app`                   |
| `--rm`                        | 容器退出时自动删除（常用于测试开发）                                  |
| `-e 环境变量=值`             | 设置环境变量，例如 `-e ENV=prod`                                     |
| `--restart 策略`              | 容器崩溃时自动重启，如 `--restart always`          