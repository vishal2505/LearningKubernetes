# Use cases when to use Namespaces

1. Structure your components
2. Avoid conflicts between team
3. Share servicesbetrween different environments
4. Access and Resource Limits on Namespaces Level

# Characteristics of Namespaces

1. You cant access most resources from another Namespace.
2. Resources can reference service from another namespace example - databases.
3. Volumne and node doesn't reside in Namespace.

# Creating component in a Namespace

#### By default components are created in default NS unless you specify in the yaml file.

1. Provide namespace during apply

```
kubectl apply -f mysql-configmap.yaml --namespace=my-namespace
```

2. Specify in the yaml file

```
apiVersion: v1
kind: ConfigMap
metadata:
    name: mysql-configmap
    namespace: my-namespace
data:
    db_url: mysql-service.database
```

# Change Active NS

1. install kubectx
    brew install kubectx

2. Check namespace with the below command -
    ```
    kubens
    ```

    active namespace will be highlighed.

3. Change the namespace
    ```
    kubens my-namespace
    Contexxt "minikube" modified.
    Active namespace is "my-namespace".
    ```
