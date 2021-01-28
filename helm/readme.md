# Helm

Package Manager for Kubernetes

1. To package YAML files
2. Distribute them in public and private repositories

Example - Elastic stack for Logging is pretty much same for all. So, we can direclty deploy 
Helm Charts (Bundle of YAML files).


## Use cases for Helm

1. Templating Engine (Create 1 template yaml file and pass the values)
2. Same applications acress different environments
3. Release management

## Helm Chart Structure

```
mychart/                    --> Top level mychart folder which is the name of chart
    Chart.yaml              --> meta infor about chart
    values.yaml             --> values for the template files
    charts/                 --> chart dependencies
    templates/              --> the actual template files
```

Templates files will be filled with the values from values.yaml

## To install Helm chart

```
help install <chartname>

helm install --values=my-value.yaml <chartname>
```

## Useful links

- Helm hub: https://artifacthub.io/
- Helm charts GitHub Project: https://github.com/helm/charts
- Install Helm: https://helm.sh/docs/intro/install/