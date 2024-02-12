# To install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# To access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# Login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o yaml
echo <argocd-initial-admin-secret> | base64 --decode

# you can change and delete init password


