# TimescaleDB (TigerData) Helm Chart

This Helm chart deploys [TimescaleDB (TigerData)](https://www.tigerdata.com/) on Kubernetes. TimescaleDB is an open-source time-series database powered by PostgreSQL.
Note that the current helm manifests do not include production-grade configuration capabilities (e.g., backups, snapshots). Rather, it is meant for a **development/staging environment**. 

## Prerequisites

- Kubernetes 1.16+
- Helm 3.x
- Persistent storage provisioner

## Installation

```sh
helm repo add timescaledb https://akvnn.github.io/helm-timescaledb
helm repo update
helm install timescaledb timescaledb/timescaledb
```

## Configuration

You can customize the deployment by overriding values in `values.yaml`:

```sh
helm install timescaledb timescaledb/timescaledb \
    --set persistentVolumeClaim.resources.requests.storage=100Gi \
    --set env[2].value="mysecretpassword"
```

See `values.yaml` for all options.

## Support

For issues and contributions, please open an issue or pull request on this repository.