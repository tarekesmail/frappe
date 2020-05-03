# Matajer Kubernetes Staging
1. Helm Charts
2. Docker file for building image
3. CI/CD Process
4. Files Function

# Helm Charts
To run the helm charts to new kubernetes cluster just install helm 3 in your machine with the following steps:

`$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh`

- To install Matajer Charts 
`helm --name matajer install helm/
`
