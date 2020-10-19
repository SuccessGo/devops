### 在 K8s 中运行一个 php-fpm 应用

#### 前置条件

我们需要一个运行中的 k8s 集群。

```shell script
$ docker version
$ kubectl version
$ minikube version
```

#### 应用架构设计

使用 k8s 中的 service 来暴露集群内的服务。请求经过 nginx 容器转发至 fpm 容器，两个窗口共用一个存储卷来存代码。

#### 关键命令帮助

k8s 对象的配置文件加载命令 `kubectl apply -f FILE_NAME`

获取服务的访问地址 `minikube service SERVICE_NAME`

打包一个镜像 `docker build -t REPO:TAG CONTEXT`

上传镜像 `docker push REPO:TAG`

登录镜像中心 `docker login [optional registry]`

#### 致谢

https://matthewpalmer.net/kubernetes-app-developer/articles/php-fpm-nginx-kubernetes.html