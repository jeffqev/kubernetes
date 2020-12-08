
# Kubernetes
* minikube start 
* minikube status
* minikube stop

# PODS
### Api
* kubectl api-resources
* kubectl run podtest --image=nginx:alpine
* kubectl run --rm -ti podtest --image=nginx:alpine -- sh
* kubectl delete pod podtest

### Pod info
* kubectl describe pod podtest
* kubectl get pod podtest -o yaml
* kubectl get pod -o wide
* kubectl get pod --watch

### Logs
* kubectl logs podtest
* kubectl logs podtest -f `logs realtime`
* kubectl logs podtest -c contenedor1 
### Labels
* kubectl get pods -l app=backend 
* kubectl label pods podtest app=backend 
* kubectl get deployment --show-labels
### Other
* kubectl port-forward podtest 1522:80
* kubectl exec -it podtest -- sh

# Manifest
containers: imagePullPolicy: IfNotPresent

* kubectl apply -f pods.yaml
* kubectl delete -f pods.yaml

# Replica set 
* kubectl get rs `or replicaset`
* kubectl describe rs rs-test
* kubectl get rs rs-test -o yaml

# Deployment
`revisionHistoryLimit: 5`
 * kubectl apply -f deployment.yaml
 * kubectl apply -f deployment.yaml --record 
 ### 
 * kubectl rollout status deployment deployment-test
 * kubectl rollout history deployment deployment-test
 * kubectl describe deployment deployment-test
 * kubectl rollout history deployment deployment-test --revision 3
 ### Rolback
* kubectl rollout undo deployment deployment-test --to-revision=3

## Annotations - chance cause
metadata:  <br /> 
&nbsp;&nbsp;annotations: <br /> 
&nbsp;&nbsp;&nbsp;&nbsp;kubernetes.io/change-cause: "Port 110"
 
# Service
 * kubectl get svc -l app=front
 * kubectl get endpoints
 * kubectl describe endpoints service-test
 * kubectl describe svc service-test

# Name space
Dns: service + namespace + svc.cluster.local <br>
deployment-test.test-ns.svc.cluster.local
 * kubectl get all -n development
 * kubectl get namespaces 
 * kubectl get namespaces --show-labels
 * kubectl get pods --namespaces default
 * kubectl create namespaces test-ns
 * kubectl run podtest --image=nginx:alpine --namespace development 
 ### Contexto
 * kubectl config current-context 
 * kubectl config view `path: .kube/config` 
 * kubectl config set-context dev --namespace=development \ --cluster=minikube \ --user=minikube
 * kubectl config use-context dev

 # Node
 * kubectl get nodes
 * kubectl describe node minikube