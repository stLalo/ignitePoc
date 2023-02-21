# Setup Non persistent Ignite cluster

## Pre-requesites
1. install [eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)
2. install [kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)

## Apply kubenertes manifests
1. `kubectl apply -f namespace.yaml`
2. change kubectl context configuration 'kubectl config set-context --current --namespace ignite'
3. create a service `kubectl apply -f svc.yaml`
4. create service account `kubectl apply -f sa-ignite.yaml`
5. Create Cluster Role and Cluster Role Binding `kubectl apply -f ignite-clusterrole.yaml`
6. Create ConfigMap `kubectl apply -f node-config.yaml`
7. Create deployment `kubectl apply -f ignite-deploymnent.yaml`

## Test it out
`curl http://ac262471b5e2d467cab6ef05f60acab3-974160849.us-east-1.elb.amazonaws.com:8080/ignite\?cmd\=version`
