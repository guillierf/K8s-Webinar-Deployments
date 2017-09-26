# K8s-Webinar-Deployments

Deploy the K8s deployments:
```
cd Deploy-Kubernetes
kubectl create -f j-hello.yml 
```

Deploy the K8s service:
```
kubectl create -f j-hello-svc.yml 
```

Result:
```
curl NodeIP:<NodePort>
```

Check:
```
kubectl get deploy
kubectl describe deploy j-hello
kubectl get pod --show-labels
kubectl get rs --show-labels
kubectl get svc
kubectl describe svc j-hello-svc
```

Scale out the K8s deployments:
```
kubectl scale deployment j-hello --replicas 10
```


Upgrade K8s deployments image:
```
kubectl set image deployment j-hello j-hello=janakiramm/j-hello:2
```

Check:
```
kubectl rollout history deployment j-hello
```

Rollbacl K8s deployments image:
```
kubectl rollout undo deployment j-hello
```

Check:
```
kubectl rollout history deployment j-hello
```



## Annex:

Useful commands:

Deployments upgrade/rollback images:

```
kubectl set image deployment j-hello j-hello=janakiramm/j-hello:2

kubectl rollout undo deployment j-hello

kubectl rollout status deployment j-hello

kubectl rollout pause deployment j-hello (this is useful for CANARY type of upgrade)

kubectl rollout resume deployment j-hello (this is useful for CANARY type of upgrade)
```
