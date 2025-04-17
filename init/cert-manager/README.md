## Cert-Manager
cert-manager adds certificates and certificate issuers as resource types in Kubernetes clusters, and simplifies the process of obtaining, renewing and using those certificates.

It supports issuing certificates from a variety of sources, including Let's Encrypt (ACME), HashiCorp Vault, and Venafi TPP / TLS Protect Cloud, as well as local in-cluster issuance.

cert-manager also ensures certificates remain valid and up to date, attempting to renew certificates at an appropriate time before expiry to reduce the risk of outages and remove toil.

Ref. https://github.com/bitnami/charts/tree/main/bitnami/cert-manager

### Install
---
### Loging to helm repo
```
helm registry login devexp-common-helm-oci.jfrog.teliacompany.io -u ${{ username}} -p ${{ password }}
```
### Install helm chart
```
helm upgrade --install cert-manager oci://devexp-common-helm-oci.jfrog.teliacompany.io/bitnamicharts/cert-manager --wait -f ./init/cert-manager/values.yaml --namespace ${{ namespace }}  --create-namespace
```
### Create telia-acme-key secret
```
kubectl create secret generic telia-acme-key \
            --from-literal=acme_hmac=${{ TELIA_ACME_KEY }} \
            --namespace {{ namespace }} \
            --dry-run=true -o yaml | kubectl apply -f - 
```
###  Install cert-manager-issuer 
```
kubectl apply -f ./init/certmanager/cert-manager-issuer.yaml -n ${{ namespace }}  