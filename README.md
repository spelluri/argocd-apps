# argocd-apps 🎯

GitOps configuration repository for ArgoCD deployments
on a 3-node Raspberry Pi Kubernetes cluster.

## 📁 Repository Structure

```
argocd-apps/
├── apps/                         # ArgoCD Application definitions
│   ├── root-app.yaml             # App of Apps parent
│   ├── guestbook.yaml            # Example app (plain YAML)
│   ├── nginx-dev.yaml            # Nginx dev environment
│   ├── nginx-staging.yaml        # Nginx staging environment
│   ├── nginx-prod.yaml           # Nginx prod environment
│   ├── myapp-dev.yaml            # Custom Helm chart (dev)
│   ├── myapp-prod.yaml           # Custom Helm chart (prod)
│   ├── kustomize-dev.yaml        # Kustomize overlay (dev)
│   ├── kustomize-prod.yaml       # Kustomize overlay (prod)
│   ├── nodeapp-dev.yaml          # Node.js app (dev)
│   ├── nodeapp-staging.yaml      # Node.js app (staging)
│   └── nodeapp-prod.yaml         # Node.js app (prod)
├── charts/                       # Custom Helm charts
│   └── myapp/                    # Multi-environment Helm chart
│       ├── Chart.yaml
│       ├── values.yaml
│       └── templates/
├── environments/                 # Helm values per environment
│   ├── dev/
│   │   └── values.yaml
│   └── prod/
│       └── values.yaml
└── manifests/                    # Kubernetes manifests
    ├── guestbook/                # Plain YAML example
    ├── nginx/                    # Plain YAML nginx
    └── nodeapp-kustomize/        # Kustomize overlays
        ├── base/                 # Shared base manifests
        └── overlays/
            ├── dev/              # Dev patches
            ├── staging/          # Staging patches
            └── prod/             # Prod patches
```

## 🏗️ Apps Managed

| App | Type | Environments |
|-----|------|--------------|
| guestbook | Plain YAML | default |
| nginx | Kustomize | dev, staging, prod |
| myapp | Helm | dev, prod |
| kustomize-app | Kustomize | dev, prod |
| nodeapp | Kustomize | dev, staging, prod |

## 🔗 Related Repositories

- [gitops-nodeapp](https://github.com/spelluri/gitops-nodeapp) — Node.js microservice source code

## 🏠 Infrastructure

```
3-node Raspberry Pi cluster running k3s v1.34.5

pelluri-berrypi1  →  control-plane  (8GB RAM)
pelluri-berrypi2  →  worker         (4GB RAM)
pelluri-berrypi3  →  worker         (4GB RAM)
```

## 📚 Topics Covered

- [x] GitOps concepts & principles
- [x] ArgoCD installation & setup
- [x] First app deployment
- [x] App of Apps pattern
- [x] Sync policies & automation
- [x] Helm & Kustomize integration
- [ ] RBAC & Multi-tenancy
- [ ] ApplicationSets
- [ ] Secrets management
- [ ] CI/CD pipeline integration
- [ ] Notifications & monitoring
- [ ] Disaster recovery & HA
