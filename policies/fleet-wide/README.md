# Fleet-Wide IAM & RBAC Policies

Manifests in this directory define cluster-level roles and role bindings that apply identically across every cluster in the fleet.

- `cluster-viewer-role.yaml`: Grants read-only audit access across standard Kubernetes resources.
- `platform-operator-role.yaml`: Grants administrative controller access for the `kube-agents` runtime.
