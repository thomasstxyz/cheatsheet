### ArgoCD app DeletionError https://github.com/argoproj/argo-cd/issues/1329

Edit the 'app' (applications.argoproj.io) and set 'finalizer' key to '[]'

### create app on cli

    argocd app create argo-rollouts-controller --repo https://github.com/thomasstxyz/gitops-certification-examples.git --path ./argo-rollouts-controller --dest-namespace argo-rollouts --dest-server https://kubernetes.default.svc --directory-recurse --sync-policy automatic --sync-option CreateNamespace=true