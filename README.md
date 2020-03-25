## HELM Chart Repository Guide 

[官方stable repo](https://github.com/helm/charts)

```
$ helm repo add stable https://kubernetes-charts.storage.googleapis.com
```

使用方法: `helm install stable/<chart>`


### 利用github自定义一个repo

```
git checkout -b gh-pages

helm package ../mychart

mkdir mychart

mv mychart-0.1.1.tgz mychart/

helm repo index . --merge index.yaml --url https://zyanru.github.io/wahaha

git commit -a -m "change index.yaml"
git push origin

helm repo add helm-example https://zyanru.github.io/wahaha
helm search repo mychart
helm install nginx-demo helm-example/mychart --set service.type=NodePort --set service.port=80
```
