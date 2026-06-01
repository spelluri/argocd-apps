# argocd-apps 🎯

GitOps configuration repository for ArgoCD deployments
on a 3-node Raspberry Pi Kubernetes cluster.

## 📁 Repository Structure

\```
argocd-apps/
├── apps/                    # ArgoCD Application definitions
│   ├── root-app.yaml        # App of Apps parent
│   ├── guestbook.yaml       # Example app (plain YAML)
│   ├── nginx-*.yaml         # Nginx environments
│   ├── myapp-*.yaml         # Custom Helm chart apps
│   ├── kustomize-*.yaml     # Kustomize overlay apps
│   └── nodeapp-*.yaml       # Node.js microservice
├── charts/                  # Custom Helm charts
│   └── myapp/               # Multi-environment Helm chart
├── environments/            # Helm values per environment
│   ├── dev/
│   └── prod/
└── manifests/               # Plain K8s manifests
    ├── guestbook/
    ├── nginx/
    └── nodeapp-kustomize/   # Kustomize overlays
        ├── base/
        └── overlays/
            ├── dev/
            ├── staging/
            └── prod/
\```

## 🏗️ Apps Managed

| App | Type | Environments |
|-----|------|--------------|
| guestbook | Plain YAML | default |
| myapp | Helm | dev, prod |
| kustomize-app | Kustomize | dev, prod |
| nodeapp | Kustomize | dev, staging, prod |

## 🔗 Related Repositories

- [gitops-nodeapp](https://github.com/spelluri/gitops-nodeapp)
  — Node.js microservice source code

## 🏠 Infrastructure

3-node Raspberry Pi cluster running k3s v1.34.5
