# scrr
When secrets are changed, the reloader restarts our pods.

## We need to install helm 3, then:
1. helm repo add stakater https://stakater.github.io/stakater-charts
2. helm repo update
3. helm install stakater/reloader --generate-name --set reloader.watchGlobally=true --set reloader.ignoreSecrets=false

## Execute commands in our project:
4. kubectl apply -f secret.yaml // create and apply
5. kubectl apply -f manifest.yaml // create a resource from manifest.yaml
6. kubectl expose deployment web --type=NodePort --port=80 // expose the web deployment as a Kubernetes Service
7. kubectl get service web // check whether the service
8. minikube service web --url // URL for your sample application

We will receive a static web page. After changing the secrets, the reloader will reload our pods.
![alt text](https://github.com/vitaliy-developer/scrr/blob/main/image.png)
