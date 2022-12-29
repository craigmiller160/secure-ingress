# Secure Ingress

This is a Helm library for setting up a Kubernetes Ingress path and securing it with a valid TLS certificate.

## Pre-Requisites

CertManager must be installed in the cluster and setup to work with Let's Encrypt.

## Example Values For Consuming Application

```yaml
secure_ingress:
  name: apps-https-backend-ingress
  backendIsHttps: true
  hosts:
    - name: apps-craigmiller160.ddns.net
      services:
        - path: /(funcoast-hi(/.*)?)
          serviceName: funcoast-hi-client
          portNumber: 443
```