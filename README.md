# ctr_project_k8s
k8s manifests

# Основные команды
```
kubectl create namespace argocd

# install argocd and init password
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
argocd admin initial-password -n argocd

# forward ports and access argocd UI
kubectl port-forward svc/argocd-server -n argocd 8080:443

# run argocd app and deploy ctr_app
kubectl apply -f app.yaml 

# get external-ip address to send requests to ctr_app Service
kubectl get services -n kuber
```