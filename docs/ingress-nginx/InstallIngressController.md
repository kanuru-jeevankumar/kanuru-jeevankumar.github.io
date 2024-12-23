---
sidebar_position: 1
---
# Install Ingress controller

## Compatible helm version

#### Kubernetes Version:
```bash
kubectl version

# OP:
    Client Version: v1.30.3
    Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
    Server Version: v1.30.3+k3s1
```

#### ingress-nginx version: 

Check the version compatibility from the matrix in this repo : https://github.com/kubernetes/ingress-nginx
    
We can use any of this range to deploy ingress-nginx, according to my k8s version above I choose to deploy the following versions, always go with latest version

```bash
ingress-nginx : v1.10.1 - v1.11.2 
NGINX verison : 1.25.3 - 1.25.5
helm chart version : 	4.10.0 - 4.11.2
```

## Get the compatible helm version for the kubernetes environment:

Search for the ingress nginx helm version check the one which satisfies with the above values 

```bash
helm search repo ingress-nginx --versions
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```

## Option 1: Install helm chart with the version: 
```bash
helm install ingress-nginx ingress-nginx/ingress-nginx \
  --namespace ingress-nginx --create-namespace \
  --version 4.11.2 \
  --set controller.image.tag=v1.11.2 \
  --set controller.nginx.image.tag=1.25.5
```

## Option 2(Recommended for production):  Create the template from the helm chart 
```bash
helm template ingress-nginx ingress-nginx/ingress-nginx \
  --namespace ingress-nginx --create-namespace \
  --version 4.11.2 \
  > ./ingress-nginx-1.25.5.yml

kubectl create namespace ingress-nginx 
kubectl apply -f ingress-nginx-1.25.5.yml -n ingress-nginx
```