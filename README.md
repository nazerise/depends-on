# depends-on
equivalent for depends_on in kubernetes

Kubernetes and Helm don't have a built-in mechanism to deploy pods in a specific order. Thus, by running an init-Container which is included a python script to check multi urls we make sure that a new deployment check the pre-requeirement deployments and then start.

The check_url.py only checks OS environments which is started with readiness_url. example: readiness_url_1 , readiness_url_2 .

To use the python script in check_url.py, create docker image with python request module by using Dockerfile.

docker build . -t python-with-requests:alpine3.20 --no-cache --rm

A Deployment example is located in example directory.

