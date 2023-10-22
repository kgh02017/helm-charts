# DynamicDNSUpdate

## Description

DynamicDNSUpdate script checks the current public IP and updates AWS Route53 record if IP address
change detected. This helm app runs DynamicDNSUpdate periodically.

## Installation
### Add helm repository to your Helm client

```
$ helm repo add kgh02017 https://kgh02017.github.io/helm-charts
```

### Get the values for configuring a chart and modify it

```
$ helm inspect values kgh02017/ddns-update > values.yaml
```

### Install the chart

```
$ helm install releaseName kgh02017/ddns-update --values values.yaml
```

### Uninstall the chart

```
$ helm uninstall releaseName
```

## Parameters
### For DynamicDNSUpdate scrypt (Mandatory)

- Unless specified, DynamicDNSUpdate scrypt doesn't work

| Name | Description | Default Value |
| --- | --- | --- |
| config.dns_zone | DNS Zone info to update | "" |
| config.timezone | Timezone info | UTC-9 |
| secret.aws_access_key_id | Access key id for Route53 user | "" |
| secret.aws_secret_access_key | Secret access key for Route53 user | "" |

### For Kubernetes

- Optional parameters

| Name | Description | Default Value |
| --- | --- | --- |
| nameOverride | resource name | "" |
| fullnameOverride | resource fullname | "" |
| image.repository | ddns-update repository | ghcr.io/kgh02017/ddns_update |
| image.tag | image tag  | "2.1.0" |
| imagePullSecrets | pullsecret for docker registry  | [] |
| cronjob.schedule | cron expression |  "@hourly" |
| cronjob.successfulJobsHistoryLimit | limit of successful jobs history| 6 |
| cronjob.failedJobsHistoryLimit | limit of failed jobs history | 10 |
| job.completions | job completion | 1 |
| job.backoffLimit | job backoff limit | 3 |
| persistence.storageClass | storage class name | "" |
| persistence.size| size of persistent volume | 100M |
| nodeSelector | node selector | {} |
| tolerations | tolerations | [] |
| affinity | affinity | {} |


