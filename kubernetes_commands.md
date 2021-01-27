$ minikube start --vm-driver=hyperkit

$ kubectl create deployment nginx-depl --image=nginx

deployment.apps/nginx-depl created

```
$ kubectl get deployment
NAME         READY   UP-TO-DATE   AVAILABLE   AGE
nginx-depl   0/1     1            0           7s
```


```$ kubectl get pod
NAME                          READY   STATUS              RESTARTS   AGE
nginx-depl-5c8bf76b5b-nbjpp   0/1     ContainerCreating   0          15s```


```$ kubectl get pod
NAME                          READY   STATUS    RESTARTS   AGE
nginx-depl-5c8bf76b5b-nbjpp   1/1     Running   0          25s```

```$ kubectl get replicaset
NAME                    DESIRED   CURRENT   READY   AGE
nginx-depl-5c8bf76b5b   1         1         1       72s```