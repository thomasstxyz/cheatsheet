# cheatsheet for kubectl

### Checking kubernetes pod CPU and memory

    kubectl top pod <pod> -n <namespace> --containers
    
### Mark storageclass as default

    kubectl patch storageclass <storageclass> -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}'
    
### Changing the reclaim policy of a PersistentVolume

    kubectl patch pv <your-pv-name> -p '{"spec":{"persistentVolumeReclaimPolicy":"Retain"}}'
    
### Restart all pods of deployment

    kubectl rollout restart deployment <deploymentname>

### Get all events in cluster sorted by newest first

    kubectl get events -A --sort-by='{.metadata.creationTimestamp}'

### Print all base64-encoded values of secret

    kubectl get secret name-of-secret -o go-template='{{range $k,$v := .data}}{{printf "%s: " $k}}{{if not $v}}{{$v}}{{else}}{{$v | base64decode}}{{end}}{{"\n"}}{{end}}'

