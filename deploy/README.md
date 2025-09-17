# Kustomize Configuration for Warm Pool

This directory contains the Kubernetes manifests and Kustomize configuration for deploying the warm pool components.

## Directory Structure

- `base/`: Contains the base Kubernetes manifests. These should not be modified directly for configuration changes.
- `overlays/`: Contains different environments or configurations for the deployment.
  - `default/`: A default overlay that provides configurable values for the base manifests.

## Usage

To apply the manifests with the default configuration, stand in the project root directory and run:

```bash
kubectl apply -k deploy/overlays/default
```

## Configuration

To change the configuration, modify the `deployment-patch.yaml` file in `deploy/overlays/default/`. This file allows you to change values such as:

- Replica count
- Container image
- Resource requests and limits
- Application labels for anti-affinity

For example, to change the number of replicas, edit `deploy/overlays/default/deployment-patch.yaml` and modify the value for `/spec/replicas`.
