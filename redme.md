
kind create cluster --name=first-cluster-eric
kubectl cluster-info --context kind-first-cluster-eric

list all pods:
 kubectl get pods -n kube-system

kind delete cluster --name=first-cluster-eric

create cluster with declarative file: 
kind create cluster --config kind.yaml --name=second-cluster-eric
kubectl get nodes


imperative, create nginx pod:
kubectl run nginx --image=nginx:alpine3.20-slim
kubectl get pods
kubectl logs nginx

kubectl delete pod nginx


creating a namespace(logical division within the application for better governance) 
project, api or context

 kubectl create namespace fist-app

 (creating a declarative pod with pod.yaml on fist-app namespace)
kubectl apply -f pod.yaml -n fist-app

details: kubectl get pods -n fist-app

forward nginx in external port:
kubectl port-forward pod/nginx -n fist-app 8081:80