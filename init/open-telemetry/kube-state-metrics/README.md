## kube-state-metrics
kube-state-metrics (KSM) is a simple service that listens to the Kubernetes API server and generates metrics about the state of the objects. It is not focused on the health of the individual Kubernetes components, but rather on the health of the various objects inside, such as deployments, nodes and pods.

Ref.
https://github.com/kubernetes/kube-state-metrics
https://github.com/bitnami/charts/tree/main/bitnami/kube-state-metrics

### Install
---

### Install kube-state-metrics
```
helm upgrade --install kube-state-metrics oci://devexp-common-helm-oci.jfrog.teliacompany.io/bitnamicharts/kube-state-metrics --wait -f ./init/open-telemetry/kube-state-metrics/values.yaml --namespace {{ namespace }} --create-namespace
```
