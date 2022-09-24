# argocd-demo

### Install

Non-HA:

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.4.12/manifests/install.yaml
```

HA:

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.4.12/manifests/ha/install.yaml
```

Password login:

`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo`

Nếu bạn muốn update lại password thì ta làm như sau, trước tiên chạy câu lệnh:

`argocd login <ARGOCD_SERVER>`

`argocd account update-password`

`https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli`