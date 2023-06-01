---
title: SQLAlchemy
description: 
published: true
date: 2023-06-01T17:05:41.910Z
tags: 
editor: markdown
dateCreated: 2023-06-01T16:56:39.624Z
---

# Utiliser les credentials présent dans le venv
```python
# utils.py
import configparser


# Permet de garder les identifiants de connexion de la BDD dans l'environnement
def getConfig(name):
    config = configparser.ConfigParser()
    config.read(".venv/pyvenv.cfg")

    return config.get("venv", name)
```

# Créer engine et session
```python
# database.py
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

from utils import getConfig

""" Create engine and session communicate with database """
engine = create_engine(
    "postgresql://"
    + getConfig("user")
    + ":"
    + getConfig("password")
    + "@localhost/"
    + getConfig("database")
    + "",
    echo=True,
)
session = sessionmaker(bind=engine)
session = session()
```

# Créer les models
## Exemples:
```python
from sqlalchemy.orm import DeclarativeBase
from sqlalchemy import Integer, Column, String


class Base(DeclarativeBase):
    pass


class Employee(Base):
    __tablename__ = "employee"

    id = Column(Integer, primary_key=True)
    simple_text = Column(String, nullable=True)
    fkey= Column(Integer, ForeignKey('models.id'))
    unicity_constraint = Column(String, unique=True)
```

# Syntaxe ORM
# TODO:
code copié peut être mis dans un repo sample
le + important =>
creation des classes (elts spécifiques ex:lien identifiant)
syntaxe de l'orm