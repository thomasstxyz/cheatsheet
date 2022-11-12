# cheatsheet for kubectl

### Checking kubernetes pod CPU and memory

    kubectl top pod <pod> -n <namespace> --containers
    
### Mark storageclass as default

    kubectl patch storageclass <storageclass> -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}'
