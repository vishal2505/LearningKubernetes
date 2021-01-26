# What is Kubernetes

Kubernetes is an open source container orchestration tool

Developed by Google

# What problems Kubernetes solve 

1. Trend from Monolith to Microservices
2. Increased usage of containers Hence need of container orchestration

# What features do orchestration tools offer 

1. High Availability or no downtime
2. SCalability or high performance
3. Disaster Recovery - Backup and Restore

# Kubernetes Basic Architecture

<img src = "images/k8s_architeture.png">

# Kubernetes Components

1. Pod

    a. Smallest unit ofg k8s

    b. Abstraction over container

    c. Usually 1 application per pod

    d. Each pod gets its own ip address

    e. New ip address on pod re-creation


2. Service

    a. Permanent ip address

    b. Lifecycle of pod and service is not connected

    c. Servie is also a load balancer

    d. App shold be accessible through browser so need External Serice

    e. For Database etc, create internal service.


3. Ingress

    a. Usually any request from client comes to Ingress and then it forwards the request to the app service.


4. ConfigMap and Secret

    a. Extrnalconfiguration of the application lik DB_URL goes to config map.

    b. Secrets contain things like database credentials which gets stored in base64 format.

    c. We use these as envoriment variables.


5. Volumes

    a. K8s doesn't manage data persistance.

    b. Volume is basically a physical storage attached to K8s cluster

    c. Volume can be local or remote like cloud.


6. Deployment
    a. Deployment is basically a bluprint for pods.

    b. We create deployments insteads of pods.

    c. We also mention replication parameter in the deployment config file which will create that many  pods.


7. StatefulSet

    a. For stateful applications like DB, it is mandatory to create StatefulSet instead of deployment.
    
    b. This is to ensure we don't suffer any  database loss and we also need to maintain the data state.





