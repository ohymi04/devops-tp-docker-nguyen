Parfait 👍
Voici un **README.md complet, professionnel et prêt à être rendu**, adapté **exactement à ton TP**, ton repo **`devops-tp-docker-nguyen`** et **GHCR**.
Tu peux **copier-coller tel quel**.

---

# 🚀 TP DevOps – Déploiement Automatisé avec Docker & GitHub Actions

## 📌 Description du projet

Ce projet a pour objectif de mettre en œuvre une **chaîne CI/CD complète** permettant de :

* Conteneuriser une application web statique avec **Docker**
* Déployer automatiquement une image Docker via **GitHub Actions**
* Publier l’image sur **GitHub Container Registry (GHCR)**
* Gérer le **versioning automatique** des images Docker

L’application web est servie par **Nginx** et affiche des informations simulées sur le conteneur et son état.

---

## 🧱 Architecture du projet

```
devops-tp-docker-nguyen/
├── .github/
│   └── workflows/
│       └── docker-deploy.yml
├── src/
│   ├── index.html
│   ├── style.css
│   └── app.js
├── nginx/
│   └── nginx.conf
├── Dockerfile
├── .dockerignore
└── README.md
```

---

## 🎯 Objectifs pédagogiques

* Comprendre la **conteneurisation** d’une application web
* Utiliser **Docker** et **Nginx**
* Mettre en place un **pipeline CI/CD**
* Publier des images sur **GHCR**
* Utiliser les **tags Git pour le versioning**
* Appliquer les **bonnes pratiques DevOps**

---

## ⚙️ Prérequis

* Compte GitHub
* Docker Desktop installé
* Git installé
* Éditeur de code (VS Code recommandé)

### Vérification de Docker

```bash
docker --version
docker run hello-world
```

---

## 🌐 Application Web

L’application est une page HTML/CSS/JavaScript qui :

* Affiche l’état du container
* Simule un test de fonctionnement
* Montre les informations Docker et CI/CD
* Est servie via **Nginx**

---

## 🐳 Conteneurisation avec Docker

### 📄 Dockerfile

* Image de base : `nginx:alpine`
* Configuration Nginx personnalisée
* Copie des fichiers statiques
* Healthcheck HTTP
* Port exposé : `80`

### Build local

```bash
docker build -t devops-tp-docker .
```

### Exécution locale

```bash
docker run -d -p 8080:80 --name devops-tp devops-tp-docker
```

➡️ Accès : [http://localhost:8080](http://localhost:8080)

---

## 🔁 Pipeline CI/CD – GitHub Actions

Le pipeline se déclenche automatiquement :

* À chaque **push sur la branche main**
* Lors de la création d’un **tag Git (vX.Y.Z)**

### Fonctionnalités du pipeline :

* Build de l’image Docker
* Tag automatique
* Push vers **GitHub Container Registry**
* Cache Docker activé

### Image publiée sur GHCR :

```
ghcr.io/ohymi04/devops-tp-docker-nguyen
```

---

## 📦 Utilisation de l’image depuis GHCR

### Pull de l’image

```bash
docker pull ghcr.io/ohymi04/devops-tp-docker-nguyen:latest
```

### Lancer le container

```bash
docker run -d -p 8090:80 ghcr.io/ohymi04/devops-tp-docker-nguyen:latest
```

➡️ Accès : [http://localhost:8090](http://localhost:8090)

---

## 🏷️ Versioning avec Git Tags

Création d’un tag :

```bash
git tag -a v1.0.0 -m "Version 1.0.0"
git push origin v1.0.0
```

Images générées automatiquement :

* `v1.0.0`
* `1.0`
* `latest`

---

## 🧪 Commandes Docker utiles

```bash
# Lister les images
docker images

# Lister les containers
docker ps -a

# Logs d’un container
docker logs <container_id>

# Exécuter une commande dans un container
docker exec -it <container_id> sh

# Arrêter et supprimer un container
docker stop <container_id>
docker rm <container_id>

# Nettoyage Docker
docker image prune -a
docker system df
```

---

## ✅ Résultats obtenus

* ✔ Application web fonctionnelle
* ✔ Image Docker optimisée
* ✔ Pipeline CI/CD opérationnel
* ✔ Publication sur GHCR
* ✔ Versioning automatique
* ✔ Bonnes pratiques DevOps respectées

---

## 👨‍🎓 Auteur

**Ohymi04**
TP DevOps – Docker & GitHub Actions
GitHub : [https://github.com/ohymi04](https://github.com/ohymi04)

---

