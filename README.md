# Kube-Agents IAM & Security Policies (`kube-agents-iam`)

This repository manages Google Cloud IAM Workload Identity mappings and Kubernetes RBAC roles partitioned across the GKE fleet in projects `gca-gke-test` and `gca-gke-2025`.

---

## 1. Directory Structure

Policies are partitioned between universal fleet-wide RBAC and cluster-specific Workload Identity identities:

```text
kube-agents-iam/
├── policies/
│   ├── fleet-wide/                       # ClusterRoles applied across all fleet clusters
│   │   ├── README.md
│   │   ├── cluster-viewer-role.yaml      # Auditor / viewer role
│   │   └── platform-operator-role.yaml   # Operator runtime role
│   └── environments/
│       ├── gca-gke-test/                 # Cluster-scoped Workload Identity KSAs
│       │   ├── README.md
│       │   ├── ka-webconsole-pr2321/     # Web console & platform agent WI
│       │   ├── gke-a2-ultra/             # OpenRL worker manager & SA
│       │   ├── gke-tpuv6-dws/            # TPU v6e training SA
│       │   ├── simple-app-cluster/       # Cost dashboard Cloud SQL proxy SA
│       │   └── kcc-management-cluster/   # Config Connector SA
│       └── gca-gke-2025/
│           ├── README.md
│           └── openrl-gpu-hub/           # OpenRL L4 GPU worker SA
└── README.md
```

---

## 2. GitOps Integration

This repository is synchronized by Argo CD running on `kcc-management-cluster`. Fleet-wide policies can be reconciled to all clusters, while environment-specific policies target only their respective cluster boundaries.
