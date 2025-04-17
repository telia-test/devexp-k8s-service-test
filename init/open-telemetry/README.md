## Open-telemetry
OpenTelemetry is:

* An observability framework and toolkit designed to facilitate the
    * Generation
    * Export
    * Collection

    of telemetry data such as traces, metrics, and logs.

Ref. 
https://github.com/open-telemetry/opentelemetry-helm-charts
https://github.com/open-telemetry/opentelemetry-collector-contrib 

### Install
---
### Add otel helm repo
```
helm repo add open-telemetry "https://jfrog.teliacompany.io/artifactory/api/helm/common-open-telemetry"  --username ${{ username }} --password ${{ password }}
helm repo update        

```
### Install otel helm chart
```
helm upgrade --install otel open-telemetry/opentelemetry-collector --version 0.117.3 --wait -f ./init/open-telemetry/values.yaml --namespace ${{ namespace }} --create-namespace 
```