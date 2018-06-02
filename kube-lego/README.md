# Set up Letsencrypt auto configuration enviroment

## Create kube-lego namespace, configmap and deployment
```
kubectl create -f kube-lego-namespace.yaml -f configmap.yaml -f deployment.yaml
```

## Check state of enviroment
```
kubectl get all -n kube-lego
```

## Get logs from pod who asks for certificates to letsencypt
```
kubectl logs -l app=kube-lego -n kube-lego
```

## To clean enviroment
```
kubectl delete -f kube-lego-namespace.yaml -f configmap.yaml -f deployment.yaml && kubectl delete svc/kube-lego-gce
```