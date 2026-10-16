# Cluster IAM Policies: `gca-gke-test`

This directory manages cluster-specific Kubernetes ServiceAccounts, Workload Identity mappings, and localized RBAC bindings for GCP project `gca-gke-test`.

## Directory Index

| Cluster Directory | Role / Service Account | Associated Workload |
| :--- | :--- | :--- |
| `ka-webconsole-pr2321/` | `kube-agents-web-console` / `kubeagents-platform-agent` | Web Console & Platform Agent |
| `gke-a2-ultra/` | `open-rl-sa` + `open-rl-worker-manager` Role | OpenRL training & scheduling system |
| `gke-tpuv6-dws/` | `tpu-training-sa` | Cloud TPU v6e training with GCS FUSE |
| `simple-app-cluster/` | `cost-dashboard-sa` | GKE Cost Dashboard Cloud SQL proxy |
| `kcc-management-cluster/` | `cnrm-controller-manager` | Config Connector management plane |
