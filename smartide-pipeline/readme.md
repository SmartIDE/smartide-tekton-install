
## 阿里云版tekton配置

``` bash
kubectl apply -f ./aliyun/trigger.yaml
kubectl apply -f ./aliyun/trigger-template.yaml
kubectl apply -f ./aliyun/trigger-binding.yaml
kubectl apply -f ./aliyun/trigger-event-listener.yaml

# build 版本 kubectl apply -f ./aliyun/task-smartide-cli-build.yaml
# release 版本 kubectl apply -f ./aliyun/task-smartide-cli-release.yaml
kubectl apply -f ./aliyun/task-smartide-cli-dev.yaml
kubectl apply -f ./aliyun/pipeline-smartide-cli.yaml
```


## Docker Hub版tekton配置
``` bash
kubectl apply -f ./dockerhub/trigger.yaml
kubectl apply -f ./dockerhub/trigger-template.yaml
kubectl apply -f ./dockerhub/trigger-binding.yaml
kubectl apply -f ./dockerhub/trigger-event-listener.yaml

# build 版本 kubectl apply -f ./dockerhub/task-smartide-cli-build.yaml
# release 版本 kubectl apply -f ./dockerhub/task-smartide-cli-release.yaml
kubectl apply -f ./dockerhub/task-smartide-cli-dev.yaml
kubectl apply -f ./dockerhub/pipeline-smartide-cli.yaml
```

## TODO
1. trigger.yaml、trigger-template.yaml、trigger-binding.yaml、trigger-event-listener.yaml、pipeline-smartide-cli.yaml 是重复的
2. task-smartide-cli-***.yaml 文件中，除了image不同，其他都是相同的
