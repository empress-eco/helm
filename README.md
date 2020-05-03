# Frappe / ERPNext

[Frappe](https://frappe.io)/[ERPNext](https://erpnext.com) world's best 100% open source ERP.

ERPNext is a full-featured business management solution that helps SMEs to record all their business transactions in a single system. With ERPNext, SMEs can make informed, fact-based, timely decisions to remain ahead in the competition. It serves as the backbone of a business adding strength, transparency, and control to your growing enterprise.

## TL;DR;

```bash
$ helm repo add frappe https://helm.erpnext.com

$ helm install frappe-bench-0001 --namespace erpnext frappe/erpnext \
    --set mariadbHost=mariadb.mariadb.svc.cluster.local \
    --set persistence.storageClass=rook-cephfs
```

## Introduction

This chart bootstraps a [Frappe/ERPNext](https://github.com/frappe/frappe_docker) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.


## Prerequisites

- Kubernetes 1.15+
- Helm 3.0+
- PV provisioner support in the underlying infrastructure
- Mariadb host available for access

## Installing the Chart

To install the chart with the release name `frappe-bench-0001`:

```bash
$ helm install frappe-bench-0001 --namespace erpnext frappe/erpnext \
    --set mariadbHost=mariadb.mariadb.svc.cluster.local \
    --set persistence.storageClass=rook-cephfs
```

The command deploys ERPNext on the Kubernetes cluster in the default configuration. The [Parameters](#parameters) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `frappe-bench-0001` deployment:

```bash
$ helm --namespace erpnext delete frappe-bench-0001
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters

The following table lists the configurable parameters of the MariaDB chart and their default values.

| Parameter                        | Description                                         | Default                         |
|----------------------------------|-----------------------------------------------------|---------------------------------|
| `replicaCount`                   | Replica Count for App Deployments                   | `1`                             |
| `nginxImage.repository`          | Frappe/ERPNext Nginx Docker image registry          | `frappe/erpnext-nginx`          |
| `nginxImage.tag`                 | Frappe/ERPNext Nginx Docker image tag               | Latest Stable Release           |
| `nginxImage.pullPolicy`          | Frappe/ERPNext Nginx Docker image pullPolicy        | `IfNotPresent`                  |
| `pythonImage.repository`         | Frappe/ERPNext Python Docker image registry         | `frappe/erpnext-worker`         |
| `pythonImage.tag`                | Frappe/ERPNext Python Docker image tag              | Latest Stable Release           |
| `pythonImage.pullPolicy`         | Frappe/ERPNext Python Docker image pullPolicy       | `IfNotPresent`                  |
| `socketIOImage.repository`       | Frappe/ERPNext SocketIO Docker image registry       | `frappe/frappe-socketio`        |
| `socketIOImage.tag`              | Frappe/ERPNext SocketIO Docker image tag            | Latest Stable Release           |
| `socketIOImage.pullPolicy`       | Frappe/ERPNext SocketIO Docker image pullPolicy     | `IfNotPresent`                  |
| `frappePyPort`                   | Frappe/ERPNext Python Gunicorn Worker Port          | `8000`                          |
| `socketIOPort`                   | Frappe/ERPNext SocketIO Port                        | `9000`                          |
| `mariadbHost`                    | MariaDB Host to connect (Required)                  | `nil`                           |
| `redisQueueHost`                 | Queue Redis Host to connect (Optional)              | `nil`                           |
| `redisCacheHost`                 | Cache Redis Host to connect (Optional)              | `nil`                           |
| `redisSocketIOHost`              | Socket IO Redis Host to connect (Optional)          | `nil`                           |
| `migrateJob.enable`              | Run migrate sites Job after helm install / upgrade  | `false`                         |
| `migrateJob.backup`              | Backup before migrate sites Job                     | `true`                          |
| `persistence.enable`             | Creates PVC with helm release name                  | `true`                          |
| `persistence.size`               | Creates PVC with size                               | `8Gi`                           |
| `persistence.storageClass`       | StorageClass with RWX, Required if PVC is created   | `nil`                           |

The above parameters map to the env variables defined in [frappe_docker](http://github.com/frappe/frappe_docker). For more information please refer to the [frappe_docker](http://github.com/frappe/frappe_docker) images documentation.

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```bash
$ helm install frappe-bench-0001 --namespace erpnext frappe/erpnext \
    --set mariadbHost=mariadb.mariadb.svc.cluster.local \
    --set persistence.storageClass=rook-cephfs \
    --set migrateJob.enable=true
```

The above command sets the MariaDB host to `mariadb.mariadb.svc.cluster.local`. Additionally it creates a PVC named with mentioned storageClass `rook-cephfs` and creates a migration job.

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example,

```bash
$ helm install frappe-bench-0001 -f values.yaml erpnext
```
