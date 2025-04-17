## Ingress-nginx
Ingress-nginx is an Ingress controller for Kubernetes using NGINX as a reverse proxy and load balancer.

Ref. https://github.com/bitnami/charts/tree/main/bitnami/nginx-ingress-controller

### Install
---
### Loging to helm repo
```
helm registry login devexp-common-helm-oci.jfrog.teliacompany.io -u ${{ username}} -p ${{ password }}
```
### Install helm chart
```
helm upgrade --install nginx-ingress oci://devexp-common-helm-oci.jfrog.teliacompany.io/bitnamicharts/nginx-ingress-controller --wait -f /init/ingress-nginx/values.yaml --namespace ${{ namespace }} --create-namespace
```