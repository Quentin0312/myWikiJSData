---
title: PSQL commands
description: 
published: true
date: 2023-06-01T15:18:06.974Z
tags: 
editor: markdown
dateCreated: 2023-05-23T14:24:57.873Z
---

# Commands
Se connecter:
```sh
psql -U postgres -h localhost -p 5432
```
Afficher la liste des database: `\l`
Se connecter à une database: `\c <nomBDD>`
Afficher la liste des tables: `\dt`