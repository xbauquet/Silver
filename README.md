# Silver k8s

## Command line log
```bash
minikube start

kubectl apply -f auth-deployment.yaml
kubectl apply -f api-deployment.yaml
kubectl get pods

kubectl apply -f auth-service.yaml
kubectl apply -f api-service.yaml
kubectl get svc

kubectl apply -f postgres-service.yaml

minikube addons enable ingress

kubectl apply -f ingress.yaml
kubectl get ingress

# Minikube tests
curl -k -L --user user:password http://`minikube ip`/auth/token/get
curl -k -L http://`minikube ip`/main/api/hello -H "Authorization: Bearer 222lsfhdsqlkfhidp4xfhm<kdsfhjm5464wfjs54dlf5dvg9kbbdhvhfdogfdjohkgjfgb543575xfvjhfwlgf2"

curl -k -L http://`minikube ip`/main/api/all -H "Authorization: Bearer 222lsfhdsqlkfhidp4xfhm<kdsfhjm5464wfjs54dlf5dvg9kbbdhvhfdogfdjohkgjfgb543575xfvjhfwlgf2"


# Local tests
curl -k -L --user user:password localhost:4567/token/get
curl -k -L localhost:4567/api/hello -H "Authorization: Bearer 222lsfhdsqlkfhidp4xfhm<kdsfhjm5464wfjs54dlf5dvg9kbbdhvhfdogfdjohkgjfgb543575xfvjhfwlgf2"

```