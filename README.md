# k8s-docker-ci-cd

## Install cluster K0s
> https://www.youtube.com/watch?v=netJ0Nuj_tw

### Run K0s controller
```k0s default-config > k0s.yaml```

```k0s server -c k0s.yaml```

### Create token for worker
```k0s token create --role=worker > token-worker```

### Run K0s worker
```k0s worker [TOKEN-WORKER]```

### Create K0s cluster
- Create a cluster user: ```clusterUser=obehotel```
- Create kube config: ```k0s kubeconfig create --groups "system:masters" $clusterUser > ~/.kube/config```
- Start cluster role: ```kubectl create clusterrolebinding $clusterUser-admin-binding --clusterrole=admin --user=$clusterUser```

## Configure CI/CD
> https://www.youtube.com/watch?v=MNBf-ylhtK0

