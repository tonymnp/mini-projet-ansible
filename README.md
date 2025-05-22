🎯 Mini-projet Ansible — Déploiement d'une WebApp Conteneurisée
Objectif
Ce projet a pour but de créer un rôle Ansible permettant de déployer automatiquement une application web conteneurisée via Docker et Docker Compose, sur des serveurs Linux (Ubuntu ou CentOS). L’objectif est de proposer une solution modulaire, réutilisable et testable, conforme aux bonnes pratiques Ansible, dans un contexte d’intégration continue (CI/CD) ou de déploiement automatisé.

📁 Arborescence du projet
css
Copier
Modifier
mini-projet-ansible/
├── ansible.cfg
├── host.yml
├── playbook.yml
├── group_vars/
│   ├── all.yml
│   ├── centos.yml
│   └── ubuntu.yml
├── host_vars/
│   ├── centos-server.yml
│   └── ubuntu-server.yml
├── roles/
│   └── webapp/
│       ├── defaults/
│       │   └── main.yml
│       ├── files/
│       ├── handlers/
│       │   └── main.yml
│       ├── meta/
│       │   └── main.yml
│       ├── tasks/
│       │   ├── docker-centos.yml
│       │   ├── docker-ubuntu.yml
│       │   └── main.yml
│       ├── templates/
│       │   └── index.html.j2
│       ├── tests/
│       └── vars/
│           └── main.yml
└── README.md
✅ Déploiement
Configurer l'inventaire (host.yml) avec les IP/hosts des serveurs cibles.

Définir les variables dans group_vars/ et host_vars/.

Exécuter le playbook :

bash
Copier
Modifier
ansible-playbook -i host.yml playbook.yml
🔍 Ce que fait le rôle
Installe les paquets nécessaires (Docker, Python, utilitaires)

Ajoute les dépôts Docker pour CentOS/Ubuntu

Installe Docker CE et Docker Compose

Configure un utilisateur pour utiliser Docker sans sudo

Déploie une page web statique avec index.html.j2

Prépare l'environnement pour accueillir des conteneurs via Ansible

🧪 Tests
Un playbook de test minimal est fourni pour vérifier le bon fonctionnement du rôle sur différents systèmes :

bash
Copier
Modifier
cd tests/
ansible-playbook -i ../host.yml ../playbook.yml
🛠️ Stack technique
Ansible

Docker / Docker Compose

Linux (Ubuntu & CentOS)

Jinja2 pour les templates

Structure de rôle Ansible compatible Galaxy

🎓 Compétences développées
Création d’un rôle Ansible complet

Structuration avancée avec vars, handlers, defaults, templates

Déploiement automatisé multi-OS

Utilisation de Docker dans Ansible

Templating dynamique avec Jinja2

Gestion fine des variables d’environnement

Préparation à la publication sur Ansible Galaxy

📦 Publication
Le rôle est prêt à être versionné et partagé via un dépôt GitHub ou une Ansible Galaxy privée. 
