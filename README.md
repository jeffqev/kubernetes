
# Kubernetes
* minikube start 
* minikube status
* minikube stop

# PODS
### Api
* kubectl run podtest --image=nginx:alpine
* kubectl delete pod podtest

### Pod info
* kubectl describe pod podtest
* kubectl get pod podtest -o yaml
### Logs
* kubectl logs podtest
* kubectl logs podtest -f `logs realtime`
* kubectl logs podtest -c contenedor1 
### Labels
* kubectl get pods -l app=backend 
### Other
* kubectl port-forward podtest 1522:80
* kubectl exec -it podtest -- sh

# Manifest
* kubectl apply -f pods.yaml
* kubectl delete -f pods.yaml

