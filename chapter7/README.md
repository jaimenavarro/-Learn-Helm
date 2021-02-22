```
k create clusterrolebinding add-on-cluster-admin --clusterrole=cluster-admin --serviceaccount=default:default
```

```
helm_v3.3.4 install jenkins bitnami/jenkins --version 7.3.5 --values values.yaml --wait --timeout 5m
```

```
k edit svc jenkins
...
...
  - name: agent
    nodePort: 32341
    port: 50000
    protocol: TCP
    targetPort: 50000
```