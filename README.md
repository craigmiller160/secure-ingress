# Secure Ingress

This is a Helm library for setting up a Kubernetes Ingress path and securing it with a valid TLS certificate.

## Pre-Requisites

CertManager must be installed in the cluster and setup to work with Let's Encrypt.

## Example Values For Consuming Application

```yaml
secure_ingress:
  name: apps-https-backend-ingress
  # Optional, defaults to false
  backendIsHttps: true
  # Optional, defaults to allowing everything
  ipWhitelist: 1.1.1.1/32, 2.2.2.2/16
  hosts:
    - name: apps-craigmiller160.ddns.net
      services:
        - path: /(funcoast-hi(/.*)?)
          serviceName: funcoast-hi-client
          portNumber: 443
```