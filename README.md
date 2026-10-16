# Kube-Agents IAM & Security Policies (`kube-agents-iam`)

This repository manages Google Cloud IAM service account bindings, Workload Identity mappings, and Kubernetes RBAC roles across the GKE fleet in project `gca-gke-test`.

---

## 1. Directory Structure

```text
kube-agents-iam/
├── policies/
│   ├── rbac/                 # Kubernetes ClusterRoles and RoleBindings
│   │   ├── cluster-viewer-role.yaml
│   │   └── platform-agent-rbac.yaml
│   └── workload-identity/    # KSA to GSA identity federation manifests
└── README.md
```

---

## 2. GitOps Integration

This repository is synchronized by the Argo CD `fleet-iam-rbac` application controller running on `kcc-management-cluster`.
