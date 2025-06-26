
# 🛠️ Setup MongoDB + Express (Node.js)

Ce projet contient :

- Un script de configuration automatique de **MongoDB** pour Ubuntu 24.04+ (`setup_mongodb`)
- Un petit serveur **Node.js + Express + Mongoose** (`test_1.js`) avec enregistrement d'utilisateurs

---

## 📦 Prérequis

- Ubuntu 22.04 ou **Ubuntu 24.04 (Noble)**
- `node` et `npm` installés (v16 ou + recommandé)
- `curl` et `apt` disponibles
- Un terminal avec privilèges `sudo`

---

## 🧪 Étape 1 : Installation de MongoDB

### 🔧 Lancer le script

```bash
chmod +x setup_mongodb
./setup_mongodb
```

OU
```bash
chmod +x mongodb_docker.sh
./mongodb_docker.sh
```

### ✅ Ce que fait ce script :

- Ajoute manuellement le dépôt MongoDB 6.0 compatible Ubuntu 24.04
- Installe MongoDB (`mongodb-org`)
- Active et démarre le service `mongod`

### 🧪 Vérifier que MongoDB fonctionne :

```bash
mongosh
```

Tu devrais voir :
```
Connecting to: mongodb://127.0.0.1:27017/
```

---

## 🧪 Étape 2 : Lancer le serveur Node.js

### 📁 Installer les dépendances

Assure-toi que tu es dans le dossier contenant `test_1.js` :

```bash
npm init -y
npm install express mongoose body-parser bcrypt ejs
```

### 🚀 Lancer le serveur

```bash
node test_1.js
```

Tu devrais voir :

```
Connecté à MongoDB
http://localhost:4444
```

---

## 📌 Routes disponibles

### `GET /register`

- Affiche une page HTML

### `POST /register`

- Crée un utilisateur
- Exemple avec curl:

```bash
curl -X POST http://localhost:4444/register \
  -H "Content-Type: application/json" \
  -d '{"username": "test", "password": "1234", "email": "test@example.com"}'
```

### `GET /users`

- Renvoie tous les utilisateurs en JSON.

---

## 🛠️ À faire / Améliorations

- Ajouter une vraie page HTML pour `register.ejs`
- Ajouter une vérification d'existence d'utilisateur
- Ajouter un système d'authentification / sessions
- Ajouter `.env` pour les infos sensibles

---

## 🧹 Nettoyage

Pour désinstaller MongoDB :

```bash
sudo systemctl stop mongod
sudo apt purge mongodb-org*
sudo rm -r /var/log/mongodb /var/lib/mongodb
```

---

## 📄 Auteurs

- Script et backend par Antonie morel
