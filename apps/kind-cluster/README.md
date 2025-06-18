# KinD Cluster Setup with 1 Master and 4 Worker Nodes

This guide explains how to create a Kubernetes cluster locally using [KinD (Kubernetes in Docker)](https://kind.sigs.k8s.io/), with 1 master node and 4 worker nodes.

---

## Prerequisites

- Docker installed and running
- KinD installed ([installation guide](https://kind.sigs.k8s.io/docs/user/quick-start/#installation))
- kubectl installed ([installation guide](https://kubernetes.io/docs/tasks/tools/))

---

## Step 1: Create the KinD config file

Create a file named `kind-config.yaml` with the following content:

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
  - role: control-plane
  - role: worker
  - role: worker
  - role: worker
  - role: worker
