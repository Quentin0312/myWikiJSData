---
title: Déployer hug python
description: 
published: true
date: 2023-06-15T19:42:50.975Z
tags: 
editor: markdown
dateCreated: 2023-06-15T19:38:25.332Z
---

# 0
Setup la BDD
# 1
![capture_d’écran_du_2023-06-15_23-35-43.png](/capture_d’écran_du_2023-06-15_23-35-43.png)

Remplacer "backend" par le nom du dossier dans lequel se situera le projet hug python.
Doit être de préférence à la racine.

# 2
Ajouter `passenger_wsgi.py` à la racine du projet Hug.
```python
import imp
import os
import sys
from server import __hug_wsgi__

sys.path.insert(0, os.path.dirname(__file__))

application = __hug_wsgi__

```
# 3
git clone le projet hug dans le dossier choisi plus tôt

# 4
![capture_d’écran_du_2023-06-15_23-39-37.png](/capture_d’écran_du_2023-06-15_23-39-37.png)
Utiliser dans le terminal depuis CPANEL ou ssh pour 
- `pip install -r requirements.txt`
- `python ./database/migration.py`
- `python ./database/import.py`
