---
title: Hug
description: 
published: true
date: 2023-06-01T16:08:27.036Z
tags: 
editor: markdown
dateCreated: 2023-06-01T16:08:27.036Z
---

# Script d'éxecution
```sh
#!/bin/bash
echo ""
echo "************Hug python launching script**************"
script_directory=$(dirname $(readlink -f $0))
cd $script_directory

hug -f server.py
```
`server.py` étant le fichier principal

# Ressource
https://github.com/alexsavio/hug