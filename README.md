#### Experiments with Minio in k3s

https://docs.min.io/docs/minio-docker-quickstart-guide.html

Assuming you already installed the Token in your local config:

    $ export KUBECONFIG=~/.kube/config
    $ kubectl get nodes
    $ source <(kubectl completion bash)

Deploy to Kubernetes

    $ kubectl create namespace hello-minio
    $ kubectl config set-context --current --namespace=hello-minio
    $ kubectl apply -k k3s/

Then visit the [URL](https://minio.localhost).
