---
title: Programmayion fonctionellle
description: 
published: true
date: 2023-06-08T17:53:30.158Z
tags: 
editor: markdown
dateCreated: 2023-06-08T17:04:46.278Z
---

# Notes
Vidéo: https://www.youtube.com/watch?v=LEcYw9_NxhQ&ab_channel=EricNormand

# Intro

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

En réalité correspond à 4 skills Using / creating calculations / actions

Calculs et actions d'ordre supérieurs

Higherorder calculations and actions
Means => calculations and actions that can be traited like any other value
	=> can be passed to functions as arguments
  => you can return them from functions ??
  => can be store in variable
  => ...
  => "pass behavior to another function"
  => take an action and make it indempotant
  if operating at higher order level
 
math(), filter() and reduce exemple of higherorder functions



# Autres
Paradigmes
Approfondir le terme effets de bords 
Réécouter - Work effectively with immutable values -Higherorder calculations and actions
Demander explication à chatgpt (exemple concret à concept abstrait)

# Autres ressources
Son livre => Grokking Simplicity, Eric Normand

Structure and Interpretation of Computer Programs, JavaScript Edition (2022)