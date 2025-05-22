# 🎯 Mini-projet Ansible — Déploiement d'une WebApp Conteneurisée

## 🧭 Objectif

Ce projet a pour but de créer un **rôle Ansible** permettant de **déployer automatiquement une application web conteneurisée** via **Docker** et **Docker Compose**, sur des serveurs Linux (Ubuntu ou CentOS).  
L’objectif est de proposer une solution **modulaire**, **réutilisable** et **testable**, conforme aux **bonnes pratiques Ansible**, dans un contexte **CI/CD** ou de **déploiement automatisé**.

---

## 📁 Arborescence du projet

mini-projet-ansible/
├── ansible.cfg
├── host.yml
├── playbook.yml
├── group_vars/
│ ├── all.yml
│ ├── centos.yml
│ └── ubuntu.yml
├── host_vars/
│ ├── centos-server.yml
│ └── ubuntu-server.yml
├── roles/
│ └── webapp/
│ ├── defaults/
│ │ └── main.yml
│ ├── files/
│ ├── handlers/
│ │ └── main.yml
│ ├── meta/
│ │ └── main.yml
│ ├── tasks/
│ │ ├── docker-centos.yml
│ │ ├── docker-ubuntu.yml
│ │ └── main.yml
│ ├── templates/
│ │ └── index.html.j2
│ ├── tests/
│ └── vars/
│ └── main.yml
└── README.md

yaml
Copier
Modifier

---

## ✅ Déploiement

1. Configurer l'inventaire dans `host.yml` avec les IP/hosts des serveurs cibles.
2. Définir les variables dans `group_vars/` et `host_vars/`.
3. Exécuter le playbook principal :

```bash
ansible-playbook -i host.yml playbook.yml
🔍 Ce que fait le rôle
Installe les paquets nécessaires (Docker, Python, utilitaires)

Ajoute les dépôts Docker pour CentOS et Ubuntu

Installe Docker CE et Docker Compose

Configure un utilisateur pour exécuter Docker sans sudo

Déploie une page web statique via index.html.j2

Prépare l’environnement pour l’orchestration de conteneurs

🧪 Tests
Un playbook de test est fourni pour valider le bon fonctionnement du rôle sur différents OS :

bash
Copier
Modifier
cd tests/
ansible-playbook -i ../host.yml ../playbook.yml
🛠️ Stack technique
Ansible

Docker / Docker Compose

Linux (Ubuntu & CentOS)

Jinja2 (templating)

Structure de rôle compatible Ansible Galaxy

🎓 Compétences développées
Création d’un rôle Ansible complet et modulaire

Structuration avancée avec vars, handlers, defaults, templates

Déploiement automatisé sur plusieurs distributions

Utilisation de Docker et Docker Compose avec Ansible

Templating dynamique avec Jinja2

Bonne gestion des variables et environnement cible

Préparation à la publication Galaxy ou usage entreprise

📦 Publication
Le rôle est prêt à être versionné et partagé via un dépôt GitHub ou une Ansible Galaxy privée (conforme aux standards de l'entreprise).
