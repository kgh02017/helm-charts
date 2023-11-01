# source-efcore

## Description

SourceBrowser website for efcore

## Installation
### Add helm repository to your Helm client

```
$ helm repo add kgh02017 https://kgh02017.github.io/helm-charts
```

### Get the values for configuring a chart and modify it

```
$ helm inspect values kgh02017/source-efcore > values.yaml
```

### Install the chart

```
$ helm install releaseName kgh02017/source-efcore --values values.yaml
```

### Uninstall the chart

```
$ helm uninstall releaseName
```

## Parameters

- Optional parameters

| Name | Description | Default Value |
| --- | --- | --- |
| nameOverride | resource name | "" |
| fullnameOverride | resource fullname | "" |
| image.repository | ddns-update repository | ghcr.io/kgh02017/source-efcore |
| image.tag | image tag  | "7.0.13" |
| imagePullSecrets | pullsecret for docker registry  | [] |
| replicaCount | # of replica pod | 1 |
| service.type | type of service | ClusterIP |
| service.port | port of service | 80 |
| ingress.enabled | enable ingress or not | false |
| ingress.className | ingress class name | "" |
| ingress.annotations | annotations for ingress | {} |
| ingress.hosts.host | hostname for ingress | source-efcore.your-cluster.local |
| ingress.hosts.paths.path | path | / |
| ingress.hosts.paths.pathType | type of path | ImplementationSpecific |
| ingress.tls | TLS for ingress | [] |
| route.enabled | enable OpenShift route or not | false |
| route.annotations | annotations for route | {} |
| route.host | hostname for route | source-efcore.your-cluster.local |
| nodeSelector | node selector | {} |
| tolerations | tolerations | [] |
| affinity | affinity | {} |