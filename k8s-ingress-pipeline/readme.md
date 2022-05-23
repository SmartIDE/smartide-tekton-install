<!--
 * @Date: 2022-05-20 16:12:37
 * @LastEditors: vincent wei
 * @LastEditTime: 2022-05-20 16:12:37
 * @FilePath: /smartide-tekton-install/smartide-pipeline/k8s-ingress/readme.md
-->

## 阿里云版tekton配置

``` bash
cd k8s-ingress-pipeline

kubectl apply -f ./aliyun/trigger.yaml
kubectl apply -f ./aliyun/trigger-template.yaml
kubectl apply -f ./aliyun/trigger-binding.yaml
kubectl apply -f ./aliyun/trigger-event-listener.yaml
kubectl apply -f ./aliyun/task-k8s-ingress.yaml
kubectl apply -f ./aliyun/pipeline-k8s-ingress.yaml
```


## Docker Hub版tekton配置
``` bash
cd k8s-ingress-pipeline

kubectl apply -f ./dockerhub/trigger.yaml
kubectl apply -f ./dockerhub/trigger-template.yaml
kubectl apply -f ./dockerhub/trigger-binding.yaml
kubectl apply -f ./dockerhub/trigger-event-listener.yaml
kubectl apply -f ./dockerhub/task-k8s-ingress.yaml
kubectl apply -f ./dockerhub/pipeline-k8s-ingress.yaml
```