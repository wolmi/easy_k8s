# NGINX Ingress Controller Installation

This contains the NGINX controller built around the Kubernetes Ingress resource that uses ConfigMap to store the NGINX configuration.

Official Documentation: [NGINX Ingress Controller](https://github.com/kubernetes/ingress-nginx)


## Installation

The following resources are required for a generic deployment.

Information and commands extracted from [NGINX Ingress Controller Deployment](https://github.com/kubernetes/ingress-nginx/tree/master/deploy)

### Mandatory commands

```console
kubectl apply -f ./namespace.yaml


kubectl apply -f ./default-backend.yaml


kubectl apply -f ../nginx-controller-config.yaml

kubectl apply -f ./tcp-services-config.yaml

kubectl apply -f ./udp-services-config.yaml

kubectl apply -f ./without-rbac.yaml

kubectl apply -f ./service.yaml

kubectl apply -f ./patch-service-without-rbac.yaml


```



## Verify installation
```
kubectl get all --namespace=ingress-nginx
kubectl get pods --all-namespaces -l app=ingress-nginx --watch
```
## See Ingres controller logs
```
kubectl logs -n=ingress-nginx -l app=ingress-nginx
```