# scrr
When secrets are changed, the reloader restarts our pods.

1. We need to install helm 3, then:
> helm repo add stakater https://stakater.github.io/stakater-charts
> helm repo update
> helm install stakater/reloader --generate-name --set reloader.watchGlobally=true --set reloader.ignoreSecrets=false

2. Execute commands in our project:
> kubectl apply -f secret.yaml // create and apply
> kubectl apply -f manifest.yaml // create a resource from manifest.yaml
> kubectl expose deployment web --type=NodePort --port=80 // expose the web deployment as a Kubernetes Service
> kubectl get service web // check whether the service
> minikube service web --url // URL for your sample application

# We will receive a static web page
