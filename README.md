
# Kubernetes
* minikube start 
* minikube status
* minikube stop

# PODS
### Api
* kubectl api-resources
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
* kubectl label pods podtest app=backend 
### Other
* kubectl port-forward podtest 1522:80
* kubectl exec -it podtest -- sh

# Manifest
* kubectl apply -f pods.yaml
* kubectl delete -f pods.yaml

# Replica set 
* kubectl get rs `or replicaset`
* kubectl describe rs rs-test
* kubectl get rs rs-test -o yaml
