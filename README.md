# Matajer Kubernetes Staging
1. Helm Charts
2. Docker file for building image
3. CI/CD Process

# 1- Helm Charts
To run the helm charts to new kubernetes cluster just install helm 3 in your machine with the following steps:

`$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh`

- To install Matajer Charts 
`helm --name matajer install helm/
`

The helm charts containing the following:
* majater_backend - matajer deployment 
* matajer_assets - this is API Gateway as nginx reversed proxy
* matajer_socketio - socketIO service deployment
* matajer_worker_d - matajer worker default
* matajer_worker_l - matajer worker long
* matajer_worker_s - matajer worker short
* matajer_redis_cache - redis deployment for caching
* matajer_redis_qeueu - redis for worker job queue 
* matajer_redis_socketio - redis for socketIO service

# 2- Docker file
The Dockerfile containing the build steps to build the matajer_backend service

# 3- CI/CD Processes
The CI/CD processes as the following:
1. Push new code to github develop branch for matajer repo 
2. The github will trigger jenkins job to start build matajer backend docker image
3. At the end of the job the pipeline will build the image and push it to dockerhub then set image for matajer services in kubernetes namespace staging for staging environment

