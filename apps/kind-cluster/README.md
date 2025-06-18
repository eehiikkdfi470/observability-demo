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
  - role: worker

Step 2: Create the cluster using KinD

Run the following command in the directory where config.yml is saved:

kind create cluster --config config.yml

Alternatively, you can specify a cluster name:

kind create cluster --config config.yml --name my-kind-cluster

Step 3: Verify the cluster is up and running

Check the nodes with:

kubectl get nodes
Expected output should list 5 nodes

![image](https://github.com/user-attachments/assets/011345e3-6d89-4bca-88e0-3077e5705117)

![alt text](image.png)
