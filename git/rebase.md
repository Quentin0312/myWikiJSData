---
title: Git rebase
description: 
published: true
date: 2023-05-23T14:10:07.000Z
tags: 
editor: markdown
dateCreated: 2023-05-16T14:37:03.563Z
---

# Rebase

## Commande de départ
`git rebase <debut> <fin> --onto <cible>`
ex:
```sh
git rebase main add-thermo --onto origin/main
```
## Étapes
À répéter:
-  pour voir les fichiers liée à un conflit
    ```sh
    git status
    ```
- gérer les conflit fichier par fichiers
- "ctrl + s" le ficher
- Quand conflit géré :
    ```sh
    git add <nomFichier>
    ```
- git rebase --continue

## Pour finir
- Pour push les changements
```sh
git push -f
```
> Écrase la branche
{.is-warning}

- Pour supprimer les branches locales non existant sur le dépot
```sh
git fetch -p
```
> Attention suppréssion définitive
{.is-warning}
