#### Experiments with Minio in k3s

See Quick-Start
[guide](https://docs.min.io/docs/minio-docker-quickstart-guide.html).

Assuming you already installed the Token in your local config:

    $ export KUBECONFIG=~/.kube/config
    $ kubectl get nodes
    $ source <(kubectl completion bash)

Deploy to Kubernetes

    $ kubectl create namespace hello-minio
    $ kubectl config set-context --current --namespace=hello-minio
    $ kubectl apply -k k3s/

Then visit the [URL](https://minio.localhost). See access & secret
keys below or in deployment Yaml.

#### MinIO Client

See
[Intro](https://docs.min.io/docs/minio-client-quickstart-guide.html):

    $ curl -L https://dl.min.io/client/mc/release/linux-amd64/mc > ~/bin/mc && chmod +x ~/bin/mc
    $ MINIO_ACCESS_KEY=AKIAIOSFODNN7EXAMPLE
    $ MINIO_SECRET_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
    $ mc alias set minio http://minio.localhost $MINIO_ACCESS_KEY $MINIO_SECRET_KEY
    $ mc ls minio
