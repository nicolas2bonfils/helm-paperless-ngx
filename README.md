# Paperless-ngx

An Helm chart to deploy [Paperless-ngx](https://www.paperless-ngx.com)

## Goal

This repo contains an helm chart to help deploying Paperless-ngx on Kubernetes cluster.

## Installation

Currently that helm-chart is not (yet) deployed to a helm-registry. So you have to install it by checking out this repo

```
$ git checkout https://github.com/nicolas2bonfils/helm-paperless-ngx.git
$ cd helm-paperless-ngx
$ helm install -n paperless-ngx paperless-ngx . -f values.yaml
```
