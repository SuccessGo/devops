### 使用 nginx 官方镜像

nginx 官方镜像站地址 https://hub.docker.com/_/nginx

首先请选择一个版本，如稳定版 v1.19。

如果希望镜像体积小，可以选择 v1.19-alpine。

#### 执行拉取镜像命令

```shell
$ docker pull nginx:1.19
$ docker pull nginx:1.19-alpine
$ docker image ls nginx
```

#### 启动 nginx 容器并访问

```shell
$ docker run --rm --name nginx --publish 8080:80 nginx:1.19
```

> 说明：
> `docker run` 命令来启动一个容器。
> `--rm` 容器停止后删除容器。
> `--name nginx` 代表给容器命名为 `name`。
> `--publish 8080:80` 代表将容器内的端口 80 映射为外部宿主机的 8080 端口。
> `nginx:1.19` 代表要启动容器要采用的镜像名称。

成功运行上述命令后，即可打开浏览器访问 `http://localhost:8080`
