# Paperless-ngx

An Helm chart to deploy [Paperless-ngx](https://www.paperless-ngx.com)

## Goal

This repo contains an helm chart to help deploying Paperless-ngx on Kubernetes cluster.

## Installation

### Namespace

Create a namespace for the app :

```shell
$ kubectl create ns paperless-ngx
```

### Dependencies

Paperless-ngx need 3 other charts to work :

- Apache tika
  
  ```shell
  $ helm repo add tika https://apache.jfrog.io/artifactory/tika
  $ helm upgrade --install -n paperless-ngx tika/tika
  ```

- Gotenberg

  ```shell
  $ helm repo add maikumori https://maikumori.github.io/helm-charts
  $ helm upgrade --install -n paperless-ngx maikumori/gotenberg -f values.yaml
  ```

- Redis

  ```shell
  $ helm repo add bitnami https://charts.bitnami.com/bitnami
  $ helm upgrade --install -n paperless-ngx bitnami/redis
  ```

### App

Currently that helm-chart is not (yet) deployed to a helm-registry. So you have to install it by checking out this repo

```shell
$ git checkout https://github.com/nicolas2bonfils/helm-paperless-ngx.git
$ cd helm-paperless-ngx
$ helm install -n paperless-ngx paperless-ngx . -f values.yaml
```
