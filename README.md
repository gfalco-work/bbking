# GitOps - ArgoCD

- Install Docker & Kind
- Install Kubectl 
- Run: **kind create cluster --name local-dev** 
- Switch to default: **kubectl config use-context kind-local-dev** 
- Install ArgoCD: **kubectl create namespace argocd** and run this after: **kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml**
- Access ArgoCD UI (using port forwarding): **kubectl port-forward svc/argocd-server -n argocd 8080:443** 
- Retrieve password: **kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d**
  - After logging in , go to the UI and User Info and change it to something like: **asdfghjkl** 
- Access to ArgoCD ui: https://localhost:8080
- Can also install ArgoCD CLI commands: **brew install argocd**
- Can be used like this: **argocd app list** 

TODO - Create multi-node config - understand what it means!