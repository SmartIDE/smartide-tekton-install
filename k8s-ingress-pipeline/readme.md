<!--
 * @Date: 2022-05-20 16:12:37
 * @LastEditors: vincent wei
 * @LastEditTime: 2022-05-20 16:12:37
 * @FilePath: /smartide-tekton-install/smartide-pipeline/k8s-ingress/readme.md
-->

## 阿里云版tekton配置

``` bash
cd k8s-ingress-pipeline

kubectl apply -f ./aliyun/1.trigger.yaml
kubectl apply -f ./aliyun/2.trigger-binding.yaml
kubectl apply -f ./aliyun/3.task-k8s-ingress.yaml
kubectl apply -f ./aliyun/4.pipeline-k8s-ingress.yaml
kubectl apply -f ./aliyun/5.trigger-template.yaml
kubectl apply -f ./aliyun/6.trigger-event-listener.yaml
```


## Docker Hub版tekton配置
``` bash
cd k8s-ingress-pipeline

kubectl apply -f ./dockerhub/1.trigger.yaml
kubectl apply -f ./dockerhub/2.trigger-binding.yaml
kubectl apply -f ./dockerhub/3.task-k8s-ingress.yaml
kubectl apply -f ./dockerhub/4.pipeline-k8s-ingress.yaml
kubectl apply -f ./dockerhub/5.trigger-template.yaml
kubectl apply -f ./dockerhub/6.trigger-event-listener.yaml
```