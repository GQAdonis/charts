# shipwright-build

![Version: 0.6.0](https://img.shields.io/badge/Version-0.6.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.6.1](https://img.shields.io/badge/AppVersion-0.6.1-informational?style=flat-square)

A Helm chart for Shipwright Build on Kubernetes

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| wangyifei | <wangyifei@kubesphere.io> |  |

## Source Code

* <https://github.com/shipwright-io/build>


## Prerequisites

* Kubernetes cluster with RBAC (Role-Based Access Control) enabled is required
* Helm 3.4.0 or newer

## Install the Chart

Ensure Helm is initialized in your Kubernetes cluster.

For more details on initializing Helm, [read the Helm docs](https://helm.sh/docs/)

1. Add openfunction.github.io as an helm repo
    ```
    helm repo add openfunction https://openfunction.github.io/helm-charts/
    helm repo update
    ```

2. Install the shipwright-build chart on your cluster in the shipwright-build namespace:
    ```
    helm install shipwright-build openfunction/shipwright-build -n shipwright-build --create-namespace
    ```

## Verify installation

```
kubectl get pods -namespace shipwright-build
```

## Uninstall the Chart

To uninstall/delete the `shipwright-build` release:
```
helm uninstall shipwright-build -n shipwright-build
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| kubernetesClusterDomain | string | `"cluster.local"` |  |
| shipwrightBuildController.replicas | int | `1` |  |
| shipwrightBuildController.shipwrightBuild.BUNDLE_CONTAINER_IMAGE.digest | string | `"sha256:8677e34c97966921fbf34ba084bc6582c2fdb244afed19aeea51cbc5466dbd1b"` |  |
| shipwrightBuildController.shipwrightBuild.BUNDLE_CONTAINER_IMAGE.repository | string | `"quay.io/shipwright/bundle"` |  |
| shipwrightBuildController.shipwrightBuild.BUNDLE_CONTAINER_IMAGE.tag | string | `"v0.6.0"` |  |
| shipwrightBuildController.shipwrightBuild.GIT_CONTAINER_IMAGE.digest | string | `"sha256:2cff62f102e495e95081cd4b56d94c0e001cfc999228ad249d4b9b099d0c0ff2"` |  |
| shipwrightBuildController.shipwrightBuild.GIT_CONTAINER_IMAGE.repository | string | `"ghcr.io/shipwright-io/build/git"` |  |
| shipwrightBuildController.shipwrightBuild.GIT_CONTAINER_IMAGE.tag | string | `"v0.7.0"` |  |
| shipwrightBuildController.shipwrightBuild.MUTATE_IMAGE_CONTAINER_IMAGE.digest | string | `"sha256:b4af89749dfa2659b1a828b06c17b6d77cb9221abdc52a99795c13ae3cf50753"` |  |
| shipwrightBuildController.shipwrightBuild.MUTATE_IMAGE_CONTAINER_IMAGE.repository | string | `"quay.io/shipwright/mutate-image"` |  |
| shipwrightBuildController.shipwrightBuild.MUTATE_IMAGE_CONTAINER_IMAGE.tag | string | `"v0.6.0"` |  |
| shipwrightBuildController.shipwrightBuild.image.digest | string | `"sha256:7e9dce636fcedcdb4e18cc8d3ccb6bdd4e21fa0c7551efef63aa5464e1b9745b"` |  |
| shipwrightBuildController.shipwrightBuild.image.repository | string | `"quay.io/shipwright/shipwright-build-controller"` |  |
| shipwrightBuildController.shipwrightBuild.image.tag | string | `"v0.6.0"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.10.0](https://github.com/norwoodj/helm-docs/releases/v1.10.0)