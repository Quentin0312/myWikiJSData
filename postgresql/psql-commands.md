---
title: PSQL commands
description: 
published: true
date: 2023-05-23T14:25:00.217Z
tags: 
editor: markdown
dateCreated: 2023-05-23T14:24:57.873Z
---

# Commands
Se connecter:
```sh
psql -U postgres -h localhost -p 5432
```
Afficher la liste des BDD: `\l`
Se connecter à une BDD: `\c <nomBDD>`
Afficher la liste des tables: `\dt`