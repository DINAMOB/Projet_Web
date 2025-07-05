# Projet Node.js + MongoDB avec Docker

Ce projet contient une application Node.js utilisant Express et Mongoose, ainsi qu’une base de données MongoDB, le tout orchestré avec Docker et Docker Compose.

---

## Prérequis

- Installer [Docker](https://docs.docker.com/get-docker/) (Docker Desktop pour Windows/macOS ou Docker Engine pour Linux)
- Installer [Docker Compose](https://docs.docker.com/compose/install/) (souvent inclus avec Docker Desktop)

---

## Structure du projet

```plaintext
mon-projet/
├── docker-compose.yml
├── app/
│   ├── Dockerfile
│   ├── app.js
│   ├── package.json
│   └── views/
│       └── register.ejs
