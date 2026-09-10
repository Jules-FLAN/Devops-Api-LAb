# DevOps Docker API Lab

J’ai fait ce projet pour m’entraîner avec Flask, Docker et GitHub Actions.

L’API est écrite en Python avec Flask. Je l’ai mise dans un conteneur Docker pour pouvoir la lancer facilement, sans installer les dépendances directement sur la machine.

## Endpoints

- `GET /` : affiche un message simple.
- `GET /health` : permet de vérifier que l’API répond correctement.
- `GET /version` : affiche la version de l’application et son environnement.

## Outils utilisés

- Python 3
- Flask
- Docker
- Docker Compose
- GitHub Actions

## Lancer le projet

Cloner le dépôt :

```bash
git clone [https://github.com/Blym-JF/Devops-Api-LAb.git](https://github.com/Blym-JF/Devops-Api-LAb.git)
cd Devops-Api-LAb
```

Lancer avec Docker Compose :

```bash
docker compose up --build
```

Une fois le conteneur lancé, l’API est disponible sur le port `8080`.

```bash
curl http://localhost:8080/
curl http://localhost:8080/health
curl http://localhost:8080/version
```

Pour arrêter le projet :

```bash
docker compose down
```

## CI

J’ai ajouté un workflow GitHub Actions dans `.github/workflows/ci.yml`.

À chaque push, il build l’image Docker, démarre le conteneur et vérifie que l’endpoint `/health` répond bien.

## Arborescence

```text
.
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
└── .github
    └── workflows
        └── ci.yml
