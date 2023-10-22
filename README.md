# kgh02017 Helm charts Repository

## Description

This site is kgh02017 Helm Repository.

## Usage
### Add this repository to your Helm client

```
helm repo add kgh02017 https://kgh02017.github.io/helm-charts
```

### Search the chart in this repository

```
helm search repo kgh02017
```

### Get the values for configuring the chart

```
helm inspect values kgh02017/ChartName > values.yaml
```

### Install the chart

```
helm install releaseName kgh02017/ChartName --values values.yaml
```

### Uninstall the chart

```
helm uninstall releaseName
```

## Source

- [kgh02017:helm-charts](https://github.com/kgh02017/helm-charts)
