# conversao-distancia

## About The Project

This a project to containerize a Python application and run it on Kubernetes.

### Built With
* Python
* Docker
* Kubernetes

## Getting Started

## Usage with Docker alone
### Prerequisites
* You need [Docker](https://docs.docker.com/) installed

### Steps
To build the image, run the following command at the source directory:
```bash
docker build -t {your_dockerhub_username}/conversao-distancia:v1 .
```

To run the image, run the following command:
```bash
docker run -d -p 5000:5000 {your_dockerhub_username}/conversao-distancia:v1
```

Now open your browser on `localhost:5000`

## Usage with Kubernetes
### Prerequisites
* You need [Docker](https://docs.docker.com/) installed
* You need [kubectl](https://kubernetes.io/docs/tasks/tools/) installed
* A Kubernetes cluster. You can run a Kubernetes cluster locally with many tools, in this example I'll use [k3d](https://k3d.io/stable/)

### Steps
To create a cluster:
```bash
k3d cluster create mycluster --servers 1 --agents 2 -p "8080:30000@loadbalancer"
```
To apply the k8s manifesto, run on the source directory:
```bash
kubectl apply -f k8s/

```
Now open your browser on `localhost:8080`

NOTE: the k8s manifesto references my image on [Dockerhub](https://hub.docker.com/), if that is not available and/or you want to run your version:
- After building your Docker image, push it to Dockerhub
- Change the field `image` on the manifesto file to match the one you pushed 

## Acknowledgments

* [Fabricio Veronez](https://github.com/fabricioveronez)
* [DevOpsPro](https://curso.devopspro.com.br/devops-pro/)
