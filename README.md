<h1 align="center">
  <span>Getting Started with Docker by Nigel Poulton</span>
</h1>

<p align="center">
  <a href="#-project">Project</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-scenarios">Scenarios</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-license">License</a>
</p>

<br>

<p align="center">
  <img alt="layout" src="./images/layout.jpg" width="80%">
</p>

<br>

## 💻 Project

This project was studied concepts of docker and its commands. Through the pluralsight platform by the following course:
https://app.pluralsight.com/library/courses/getting-started-docker/table-of-contents.

## 🚀 Scenarios

### 1. first-container

This folder contains the files to build a single-container web app (express, handlebars...)
- Docker hub image: [brunocs90/gsd:first-ctr].

```bash
docker image build -t brunocs90/gsd:first-ctr .
docker image push brunocs90/gsd:first-ctr
docker image rm brunocs90/gsd:first-ctr -f
docker container run -d --name web -p 8000:8080 brunocs90/gsd:first-ctr

docker container stop web
docker container start web
docker container rm web
```

### 2.  multi-container

NEEDS UPDATING
This folder contains the files to build a multi-container web app with Compose.
- Python flask app with redis cache.

```bash
docker-compose up -d
docker image ls
docker container ls
docker-compose down
```

### 3. swarm-stack

This folder contains the files to build a multi-container web app with Swarm Stacks.
- Python flask app with redis cache that also returns hostname of container service request.

```bash
docker image build -t brunocs90/gsd:swarm-stack .
docker image push brunocs90/gsd:swarm-stack
docker swarm init
docker stack deploy -c .\docker-compose.yml counter
docker stack ls
docker stack services counter
docker stack ps counter
http://localhost:5000/
Change replicas: 5
docker stack deploy -c .\docker-compose.yml counter
docker stack rm counter
```
## 📝 License

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

---
**Desenvolvido por [Bruno César](https://github.com/brunocs90).**
