# sidecar-proxy-example

Run:
\*\* For minikube

- minikube start
- minikube dashboard
- kubectl apply -f kubernetes-deployment.yaml
- kubectl expose deployment nginx-deployment --type=LoadBalancer --name=my-service-nginx-deployment
- kubectl get services my-service-nginx-deployment
- minikube service my-service-nginx-deployment

Input : admin:admin

- nginx-proxy >> proxy to redirect to hello world app

- helloworld-http >> application

////////////////////////////////////////

cd nginx-proxy

docker build -t anacondong/sidecar-proxy-example-sidecar-proxy .

cd helloworld-http

docker build -t anacondong/sidecar-proxy-example .

kubectl apply -f kubernetes-deployment-local-build.yaml

//////////////////////////////

ref: Example application for article at https://medium.com/@lukas.eichler/securing-pods-with-sidecar-proxies-d84f8d34be3e about Kubernetes Sidecar proxies
