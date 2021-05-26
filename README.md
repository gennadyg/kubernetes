### Useful commands
az aks check-acr --acr adpdev.azurecr.io -n adp-dev-uksouth -g adp-dev-uksouth --subscription adp_dev_compute1
~~~
kubectl get no -o wide && kubectl top no
kubectl get jobs -n services-uksouth
kubectl get pods -n services-uksouth
kubectl get pods --field-selector=status.phase=Running --no-headers=true -o custom-columns=':metadata.name' -n services-uksouth

helm install --debug --dry-run aks-pod-deleter --namespace services-uksouth .\aks_del_chart\
helm install --debug aks-pod-deleter --namespace services-uksouth .\aks_del_chart\
helm uninstall --debug aks-pod-deleter --namespace services-uksouth

kubectl get events --all-namespaces  --sort-by='.metadata.creationTimestamp'
kubectl create -f .\cronjob.yaml
kubectl get pods -n services
~~~
### HELM commands
~~~
helm package volga
helm install volga .\volga-0.1.0.tgz
helm install --debug --dry-run group-multiplexer chart -f config/dev.yaml -n tenant-0
helm ls -n tenant-0
delete -n tenant-0 volga
helm uninstall volga -n tenant-0
helm list --all --all-namespaces

helm search hub kafka
helm status volga
helm show values stable/mariadb
helm list
helm delete volga -n tenant-0
helm install volga chart -f config/tenant_0.yaml -n tenant-0
or
helm upgrade volga chart -f config\tenant_0.yaml -n tenant-0
kubectl describe po -n tenant-0
kubectl logs -f volga-59978589cc-sdppr -n tenant-0

kubectl get pod -n tenant-0
 k get service --watch
~~~

### Remove images

docker system prune

### See all local images

docker image ls -a

### build & tag local image

docker build . --tag gcr.io/axonite-dev/group-multiplexer

### Push image to GCP registry

docker push gcr.io/axonite-dev/group-multiplexer

### Run intercatively
~~~
docker run -it gcr.io/axonite-dev/dnieper /bin/sh
docker run -p 127.0.0.1:8080:8080/tcp gcr.io/axonite-dev/group-multiplexer
~~~
### az 
~~~
az aks --help
az account show --output table
az acr login -n adpdev
az acr repository list -n adpdev -o table
~~~
// create appId & password 
~~~
az ad sp createfor-rbac --skip-assignment
$acrId = az acr show --name adpdev --resource-group adp-dev --query "id" -o tsv
az role assignment create --assignee "$appId" --role Reader --scope $acrId
az acr list --resource-group adp-dev --query "[].{acrLoginServerr:loginServer}" -o table
~~~
### Power Shell 
~~~
start microsoft-edge:http://www.ynet.co.il
Set-Alias -Name k -Value kubectl
function gitlog {git log --graph --oneline --decorate --all}
~~~
