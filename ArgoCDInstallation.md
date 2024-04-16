#  Installing ArgoCD in K8s cluster with creating namespace
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

# Expsose argocd service for ArgoCD UI 
```bash
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd
```

# Use below command for password with decode with base64
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```

# Important Links : 

- Config repo: https://gitlab.com/nanuchi/argocd-app-config


- Docker repo: https://hub.docker.com/repository/docker/nanajanashia/argocd-app


- Install ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd


- Login to ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli


- ArgoCD Configuration: https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/