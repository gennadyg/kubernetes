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
az aks --help
az account show --output table
az acr repository list -n adpdev -o table

### Power Shell 

start microsoft-edge:http://www.ynet.co.il
Set-Alias -Name k -Value kubectl

