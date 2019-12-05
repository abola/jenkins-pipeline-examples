# Healthy

這個範例是基於 basic 下，再增加 Liveness probe 及 Readiness probe 的示範

參考此配置，您只需要調整檔案 `Jenkinsfile` 中，最上方的參數，如下

```pipeline
def name = "my-app"
def namespace = "my-app-project"
def imageName = "localhost:32000/my-app"
def imageTag = "1.0" // image's tag
def podReplicaCount = "3"
def serviceType = "ClusterIP" // None, NodePort, ClusterIP, LoadBalancer
def ports = "3000"
def nodePort = "" // if serviceType is NodePort
def targetPort = ""
```

存檔後，將此目錄，含子錄目的所有內容，拷貝一份至其它的 git repository ，並交由Jenkins 透過 SCM 拉取執行即可
