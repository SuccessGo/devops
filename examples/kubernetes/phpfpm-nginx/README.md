### 在 K8s 中运行 phpfpm 和 nginx

需要提前安装好 docker, minikube。

创建一个 configmap 存储 nginx 配置文件

创建一个 pod，包含 2 个容器：nginx 和 phpfpm。两者连接同一个存储卷实现代码共享

创建一个 service

创建一个 deployment

所有文件使用如下命令生效 `kubectl apply -f FILE_NAME`

获取服务的访问地址 `minikube service SERVICE_NAME`