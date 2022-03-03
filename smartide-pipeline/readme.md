
## 阿里云版tekton配置
```
kubectl apply -f ./aliyun/trigger.yaml
kubectl apply -f ./aliyun/trigger-template.yaml
kubectl apply -f ./aliyun/trigger-binding.yaml
kubectl apply -f ./aliyun/trigger-event-listener.yaml

kubectl apply -f ./aliyun/task-smartide-cli.yaml
kubectl apply -f ./aliyun/pipeline-smartide-cli.yaml
```


## Docker Hub版tekton配置
```
kubectl apply -f ./dockerhub/trigger.yaml
kubectl apply -f ./dockerhub/trigger-template.yaml
kubectl apply -f ./dockerhub/trigger-binding.yaml
kubectl apply -f ./dockerhub/trigger-event-listener.yaml

kubectl apply -f ./dockerhub/task-smartide-cli.yaml
kubectl apply -f ./dockerhub/pipeline-smartide-cli.yaml
```