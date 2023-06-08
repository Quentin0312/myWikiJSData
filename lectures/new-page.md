---
title: Programmayion fonctionellle
description: 
published: true
date: 2023-06-08T17:37:17.512Z
tags: 
editor: markdown
dateCreated: 2023-06-08T17:04:46.278Z
---

# Notes
Vidéo: https://www.youtube.com/watch?v=LEcYw9_NxhQ&ab_channel=EricNormand

# Intro
Son livre => Grokking Simplicity, Eric Normand

Ne veut pas donner de définition de ce qu'est la programmation fonctionelle mais donner les skills 
des "programmeurs fonctionelles" (ce qu'il font de mieux)

Mise en opposisition avec la programmation orienté objet (qui a lui aussi ces "sets of skills")

You can use fonctional programming skills with other paradigms skills (take the best of either)

# Discriminate between actions, calculation and data

> TODO: Mettre en comparaison avec "compute, store and 'effets de bords'" 
{.is-info}

Les 5 skills principaux:
1. Be able to discriminate between actions, calculations and data (skill 1)

Doit pouvoir en regardant le code faire la différence (ça c'est du calcul, ça effets de bords, ...)

Implique que doit pouvoir coder de cette façon (sue ce soit explicite dans le code)

COMPUTE/CALCULATIONS => Fonctions qui donne le même résultat avec les mêmes argument peu importe ou il est executé ("pure functions/calculations")
exemple => ??

ACTIONS/EFFETS DE BORDS => Peux changer selon l'endroit de l'éxécution ; ("impure functions")
exemple => ??

> En general, il est mieux d'avoir le moins de code "ACTIONS/EFFETS DE BORDS" et necessite plus d'attention que les "COMPUTE/CALCULATIONS" pcq => ?? (plus sensibles ?! vu que pas la même reponse selon lieux d'exec)
{.is-info}

DATA => stocker les infos dans des variables. (et autres => signal,... ??)

# Work effectively with immutable values
immutable values => valeurs immuable (qui ne change pas)
=> être capable de travailler avec des valeurs immuable, qui ne change pas (skill 2)
==> means ??

Bigger chalenges => with nested data, change something that is deep in nested structure

# Higherorder calculations and actions

"Using and creating Higherorder calculations and actions" (skill 3)

Calculs et actions d'ordre supérieurs





# Autres
Paradigmes
Approfondir le terme effets de bords 
Réécouter - Work effectively with immutable values -Higherorder calculations and actions
Demander explication à chatgpt