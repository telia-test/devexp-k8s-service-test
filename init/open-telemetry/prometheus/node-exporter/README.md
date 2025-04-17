## Prometheus node-exporter
Prometheus exporter for hardware and OS metrics exposed by *NIX kernels, written in Go with pluggable metric collectors.

### Install
---
### Add prometheus-community helm repo
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts    

```
### Install node-exporter helm chart
```
helm upgrade --install node-exporter prometheus-community/prometheus-node-exporter --wait -f ./init/open-telemetry/prometheus/node-exporter/values.yaml --namespace ${{ namespace }} --create-namespace

```

```
helm upgrade --install node-exporter oci://devexp-common-helm-oci.jfrog.teliacompany.io/bitnamicharts/node-exporter --wait -f ./init/open-telemetry/prometheus/node-exporter/values.yaml --namespace ${{ namespace }} --create-namespace
```