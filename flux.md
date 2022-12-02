### Diagnosis

Basic Troubleshooting on flux-system kustomization and gitrepository

    kubectl -n flux-system describe kustomizations.kustomize.toolkit.fluxcd.io flux-system


    kubectl -n flux-system describe gitrepositories.source.toolkit.fluxcd.io flux-system

Reconcile flux-system

    flux reconcile kustomization flux-system

Get all flux resources

    flux get all
