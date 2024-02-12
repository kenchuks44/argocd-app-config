# To install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# To access ArgoCD UI
kubectl get svc -n argocd
kubectl patch svc argo-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

# Login with admin user and below token (as in documentation):
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d

# you can change and delete init password


