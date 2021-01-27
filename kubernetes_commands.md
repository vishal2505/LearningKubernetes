$ minikube start --vm-driver=hyperkit

$ kubectl create deployment nginx-depl --image=nginx

deployment.apps/nginx-depl created

```
$ kubectl get deployment
NAME         READY   UP-TO-DATE   AVAILABLE   AGE
nginx-depl   0/1     1            0           7s
```


```
$ kubectl get pod
NAME                          READY   STATUS              RESTARTS   AGE
nginx-depl-5c8bf76b5b-nbjpp   0/1     ContainerCreating   0          15s
```


```
$ kubectl get pod
NAME                          READY   STATUS    RESTARTS   AGE
nginx-depl-5c8bf76b5b-nbjpp   1/1     Running   0          25s
```


```
$ kubectl get replicaset
NAME                    DESIRED   CURRENT   READY   AGE
nginx-depl-5c8bf76b5b   1         1         1       72s
```


## debugging
```
kubectl logs {pod-name}
kubectl exec -it {pod-name} -- bin/bash
```

## create mongo deployment
```
kubectl create deployment mongo-depl --image=mongo
kubectl logs mongo-depl                -{pod-name}
kubectl describe pod mongo-depl        -{pod-name}
```

## delete deplyoment
```
kubectl delete deployment mongo-depl
kubectl delete deployment nginx-depl
```

## create or edit config file
```
vim nginx-deployment.yaml
kubectl apply -f nginx-deployment.yaml
kubectl get pod
kubectl get deployment
```

## delete with config
```
kubectl delete -f nginx-deployment.yaml
```

## Metrics
```
kubectl top 
The kubectl top command returns current CPU and memory usage for a cluster’s pods or nodes, or for a particular pod or node if specified.
```