# Udagram Casson ![Travis build status](https://travis-ci.com/cassonchris/udagram-casson.svg?branch=master "Travis build status")
___

## Build Locally
___
`docker-compose -f docker/docker-compose-build.yaml build --parallel`

## Run Locally
___
`docker-compose up`

## Deploy to Kubernetes
___
1. Apply aws-secret `kubectl apply -f k8s/aws-secret.yaml`
2. Apply secrets-dev `kubectl apply -f k8s/secrets-dev.yaml`
3. Apply configmap-dev `kubectl apply -f k8s/configmap-dev.yaml`
4. Apply deployments
    1. `kubectl apply -f k8s/deployment-api-feed.yaml`
    2. `kubectl apply -f k8s/deployment-api-user.yaml`
    3. `kubectl apply -f k8s/deployment-frontend.yaml`
    4. `kubectl apply -f k8s/deployment-reverse-proxy.yaml`
5. Apply services
    1. `kubectl apply -f k8s/service-api-feed.yaml`
    2. `kubectl apply -f k8s/service-api-user.yaml`
    3. `kubectl apply -f k8s/service-frontend.yaml`
    4. `kubectl apply -f k8s/service-reverse-proxy.yaml`
