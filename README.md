# lab-argocd


https://github.com/badtuxx/DescomplicandoArgoCD/blob/main/pt/src/day-1/README.md#criando-a-nossa-app-exemplo


https://www.youtube.com/watch?v=TDvA2vAQCF8


argocd app create nginx-app --repo https://github.com/douglasdalves/lab-argocd.git --path lab-nginx --dest-server https://kubernetes.default.svc --dest-namespace lab-hml

kubectl port-forward svc/argocd-server -n argocd 8080:443




Commands

# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo

# you can change and delete init password

Links

Config repo: 
Docker repo: 
Install ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd
Login to ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli

ArgoCD Configuration: https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/