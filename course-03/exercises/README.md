# Docker Hub Images 
https://hub.docker.com/u/noura22

# Travis CI Screenshots
Travis CI screenshots is on this directory

# Build and Push Docker Images
Apply the following for each service:
1. Install dependencies `npm i`
2. build docker image. e.g. `docker build -t noura22/feed .`
4. push the created image to docker hub. e.g. `docker push noura22/feed`

# Deploy The Services
The following steps explain how to deploy the services:
1. Deploy config files as follows
`kubectl apply -f env-secret.yaml`
`kubectl apply -f env-configmap.yaml`
`kubectl apply -f aws-secret.yaml`
2. Deploy the services. For example
`kubectl apply -f backend-feed-deployment.yaml`
`kubectl apply -f backend-feed-service.yaml`
3. Check running running `kubectl get pods`
4. Forward ports
`kubectl port-forward service/frontend 8100:8100`
`kubectl port-forward service/reverseproxy 8080:8080`
