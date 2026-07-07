# ctr_project_k8s

Kubernetes manifests.

# Main Commands

```bash
kubectl create namespace argocd

# Install Argo CD and retrieve the initial admin password
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
argocd admin initial-password -n argocd

# Forward ports and access the Argo CD UI
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Create the Argo CD application and deploy ctr_app
kubectl apply -f app.yaml

# Get the external IP address for sending requests to the ctr_app Service
kubectl get services -n kuber
```
