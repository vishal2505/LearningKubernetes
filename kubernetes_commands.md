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

## Deployment and Service

```
$ kubectl get service

NAME            TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)   AGE
kubernetes      ClusterIP   10.96.0.1        <none>        443/TCP   151m
nginx-service   ClusterIP   10.106.241.228   <none>        80/TCP    18s
```

```
$ kubectl describe service nginx-service

Name:              nginx-service
Namespace:         default
Labels:            <none>
Annotations:       kubectl.kubernetes.io/last-applied-configuration:
                     {"apiVersion":"v1","kind":"Service","metadata":{"annotations":{},"name":"nginx-service","namespace":"default"},"spec":{"ports":[{"port":80...
Selector:          app=nginx
Type:              ClusterIP
IP:                10.106.241.228
Port:              <unset>  80/TCP
TargetPort:        8080/TCP
Endpoints:         172.17.0.3:8080,172.17.0.4:8080
Session Affinity:  None
Events:            <none>
```

```
$ kubectl get pod -o wide

NAME                               READY   STATUS    RESTARTS   AGE    IP           NODE       NOMINATED NODE   READINESS GATES
nginx-deployment-f4b7bbcbc-2j78t   1/1     Running   0          4m4s   172.17.0.4   minikube   <none>           <none>
nginx-deployment-f4b7bbcbc-8d2zm   1/1     Running   0          4m4s   172.17.0.3   minikube   <none>           <none>

```

## Create the yaml file from deployment

```
$ kubectl get deployment nginx-deployment -o yaml > nginx-deployment-result.yaml
```