# kubefed2 Docker image

Use this image when walking through the [federation-v2 userguide](https://github.com/kubernetes-sigs/federation-v2/blob/master/docs/userguide.md).

Example usage assuming $HOME/.kube/config has two contexts that are to be part of the federated cluster, cluster1 and cluster2:
```
docker run -v $HOME/.kube:/root/.kube erstaples/kubefed2:latest join cluster1 \
    --cluster-context cluster1 \
    --host-cluster-context cluster1 \
    --add-to-registry \
    --v=2

docker run -v $HOME/.kube:/root/.kube erstaples/kubefed2:latest join cluster2 \
    --cluster-context cluster2 \
    --host-cluster-context cluster1 \
    --add-to-registry \
    --v=2
```

See https://github.com/kubernetes-sigs/federation-v2/blob/master/docs/userguide.md for more information. Happy federating!
