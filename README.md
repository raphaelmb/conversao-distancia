# conversao-distancia

## About The Project

This a project to containerize a Python application

### Built With

* Python
* Docker

## Getting Started

### Prerequisites

* You need [Docker](https://docs.docker.com/) installed

## Usage

To build the image, run the following command at the source directory:
```bash
docker build -t {your_dockerhub_username}/conversao-distancia:v1 .
```

To run the image, run the following command:
```bash
docker run -d -p 5000:5000 {your_dockerhub_username}/conversao-distancia:v1
```

Now open your browser on `localhost:5000`

## Acknowledgments

* [Fabricio Veronez](https://github.com/fabricioveronez)
* [DevOpsPro](https://curso.devopspro.com.br/devops-pro/)
