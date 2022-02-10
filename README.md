# Tekton 本地化部署

本代码库提供了Tekton本地部署优化的脚本，所有镜像已经导入阿里云镜像仓库，不再依赖墙外资源。
已经测试了MacOS上的本地Minikube上部署并运行hello-world成功。

## 安装脚本

1. Tekton API Server

```shell
kubectl apply --filename pipeline/smartide-tekton-release.yaml
```

CLI

原生安装方式，可能被墙，参考 https://tekton.dev/docs/cli/

```shell
## MacOS
brew install tektoncd-cli
## Linux
sudo apt update;sudo apt install -y gnupg
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3EFE0E0A2F2F60AA
echo "deb http://ppa.launchpad.net/tektoncd/cli/ubuntu eoan main"|sudo tee /etc/apt/sources.list.d/tektoncd-ubuntu-cli.list
sudo apt update && sudo apt install -y tektoncd-cli
```

cli安装包已经复制到dlsmartide存储账号

- Mac https://smartidedl.blob.core.chinacloudapi.cn/tekton/cli/v0.21.0/tkn_0.21.0_Darwin_x86_64.tar.gz
- Windows https://smartidedl.blob.core.chinacloudapi.cn/tekton/cli/v0.21.0/tkn_0.21.0_Windows_x86_64.zip
- Linux https://smartidedl.blob.core.chinacloudapi.cn/tekton/cli/v0.21.0/tkn_0.21.0_Linux_x86_64.tar.gz 


2. Tekton Dashboard

```shell
## 安装
kubectl apply -f dashboard/smartide-tekton-dashboard-release.yaml
## 端口转发
kubectl --namespace tekton-pipelines port-forward svc/tekton-dashboard 9097:9097
## 打开 http://localhost:9097
```

3. Trigger

```shell
## 安装
kubectl apply -f trigger/smartide-release.yaml
kubectl apply -f trigger/smartide-interceptor.yaml

## 端口转发
kubectl --namespace tekton-pipelines port-forward svc/tekton-dashboard 9097:9097
## 打开 http://localhost:9097
```

## 测试Tekton可以正常工作

```shell
## 创建 hello-world 任务
kubectl apply -f task-hello.yaml

## 使用tkn运行
tkn task start hello --dry-run
tkn task start hello

## 使用kubectl运行
# use tkn's --dry-run option to save the TaskRun to a file
tkn task start hello --dry-run > taskRun-hello.yaml
# create the TaskRun
kubectl create -f taskRun-hello.yaml

## 查看运行日志
tkn taskrun logs --last -f 
```

