# Volumes

## Need of persistance storage

1. Storage that doesnt depend on the pod lifecycle.
2. Storage must be available on all nodes.
3. Storage needs to survive even if cluster crashes.


## Persistent Volume

1. A Cluster resoruce
2. Created via YAML files 
3. Needs actual physical storage (external plugin to the cluster like nfs server or cloud)
4. PV outside of namespaces and accessible to the whole cluster


K8s admin sets up and maintains the cluster and also configures the actual storage.
Storage needs to be avialble before the cluster setup.


## Persistant Volume Claim

1. Application has to claim the Persistent Volume
2. Storage and accessModes need to be defined
3. Pod requests the volume through the PV claim
4. Claim tries to find a volume in Cluster
5. Claims must be in the same namespace


## ConfigMap and Secret Volumes
1. Local Volumes
2. Not created via PV or PVC

## Storage Class
1. SC provisions PV dynamically when PVC claims it.
2. kind: StorageClass

