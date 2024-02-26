# elea

## the whole gbf.wiki stack

## deploy steps

deploy dashboard

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
```

deploy service account 

```
kubectl apply -f serviceaccount/admin-user.yaml
```

deploy argocd

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```


# useful stuff


### get dashboard token

```
kubectl -n kubernetes-dashboard create token admin-user
```

### port-forward argocd

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```