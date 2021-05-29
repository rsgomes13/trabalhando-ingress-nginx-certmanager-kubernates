# trabalhando-ingress-nginx-certmanager-kubernates

## aplicação
kubectl apply -f app1.yaml
kubectl apply -f app2.yaml
kubectl apply -f app3.yaml

## ingress-nginx
kubectl create namespace ingress-nginx
helm install ingress-nginx ingress-nginx/ingress-nginx
kubectl apply -f ingress-wildcard-host.yaml


## cert-manager
helm install \
  cert-manager jetstack/cert-manager \
  --namespace cert-manager \
  --create-namespace \
  --version v1.3.1 \
  --set installCRDs=true

kubectl apply -f issuer.yaml
