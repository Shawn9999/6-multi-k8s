## This is the 2nd kebernetes project
* Multiple set of pods
* Multiple services 
* Multiple Deployments
* ClusterIp
* Ingress-nginx
* PVC
* Environment variable
* Secret
* Redis
* Postgres

### Workflow
* ingress: 80/443 -> ClusterIp port: 3000/5000 -> targetPort/containerPort: 3000/5000

### Rebuild multi-client image
* See README.md in 3-docker-react
* multi-client image in docker hub is loaded by 4-multi-docker project which got extra 

### Deploy locally
* login session must be `root#`. 
* Do not use `/home/sha$` because `kind` does not expose app port to the outside unless you use loadBalancer.
* Deploy 
```sh
    kubectl apply -f ./k8s
```
* Test on `localhost` or `https://localhost`
    * Uncaught syntax error: unexpected token '<'
* Cleanup 
```sh
    kubectl delete -f ./k8s
```

