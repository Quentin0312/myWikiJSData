---
title: Déploiement de Wikijs
description: 
published: true
date: 2023-05-05T04:15:06.458Z
tags: 
editor: markdown
dateCreated: 2023-05-04T16:57:45.624Z
---

# Déploiement de wikijs avec o2switch
## Via l'utilitaire "Sous-domaine" de cpanel:
Créer un sous-domaine via cpanel avec l'utilitaire "Sous domaine"

## Via l'utilitaire "Assistant de base de données MySQL":
Créer une base de données MySQL en suivant les instructions

## Via le terminal cpanel ou en ssh:

- Supprimer le contenu du dossier qui porte le nom du sous-domaine créer
	```sh
  cd "sous_domaine"
  rm -r cgi-bin
  ```

- Télécharger la derniere version de wikijs
  ```sh
  cd ~
  wget https://github.com/Requarks/wiki/releases/latest/download/wiki-js.tar.gz
  ```

- Extraire dans le dossier du sous-domaine
  ```sh
  tar xzf wiki-js.tar.gz -C ./sous_domaine
  ```
  
- Créer le fichier config.yml depuis le template config.sample.yml
  ```sh
  cd sous_domaine/
  mv config.sample.yml config.yml
  ```
## Via l'utilitaire "Gestionnaire de fichiers":
Editer le fichier config.yml précédemment créer.
- Modifier les valeurs:
  ```text
  db:
    type: mysql
    host: localhost
    port: 3306
    user: <nomUtilisateur>
    pass: <mdp>
    db: <nomDb>
  ```
## Via l'utilitaire "Setup node.js app":
Créer une nouvelle application:
- "Application root" correspond au dossier contenant l'application, c'est donc le nom du sous-domaine
- "Application URL" correspond à l'URL du sous-domaine
![capture_d’écran_du_2023-05-04_20-09-38.png](/capture_d’écran_du_2023-05-04_20-09-38.png)

# Si erreur
## Pour vérifier la connexion entre l'application et la base de données
```sh
cd "sous_domaine"
node server
```

- Feedback attendu:
![capture_d’écran_du_2023-05-04_20-18-36.png](/capture_d’écran_du_2023-05-04_20-18-36.png)

# Ressources
https://docs.requarks.io/install/linux
https://faq.o2switch.fr/nodejs/comment-installer-wikijs-hebergement-o2switch