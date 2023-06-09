---
title: Programmation fonctionnelle
description: 
published: true
date: 2023-06-09T07:00:17.612Z
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

# Data modeling (skill 4)

Data modeling is all about, how do you effectively structure the data that you have so that you can use it effectively

Tw0 kind	
- Public facing data that exit the server (ex: API) (different constrains because for ex needs to be human readable for dev to use your api)

- Internal data modeling (constraint ex: efficient, available, ...)

5. Architecture skills (skills 5)
design and architectural principles needed (functional programing have some (diff de celles des autres paradigms))
ex of architectural patterns is the reactive data , reactive architecture
(Redux, Elm Architecture, re-frame in ClojureScript, ...)
=> the idea is :
- events generated
- events consumed
That generates a view that is projected out into like a GUI

modified state generates a projection onto the GUI
reaction based on changes to the data

Another architecure pattern => Onion architecture
3 main layers (comme des couches d'un oignon)
1. Interaction layer (outer layer)
talks to the "outside worlds"; where to put the ACTIONS
2. Business rule layer (calculation layer) CALCULATIONS
3. Domain layer (domain model) DATA ? => NON

Exemple donnée:
2. Business rule layer
contains changing requirements of business
like how payroll is calculated ; vacation policy
3. Domain layer, domain model
Timeless domain layer that the business rule call into
like the fact that employee get salary, vacation (no matter how much) 


# Fast changing layer
1. Interaction layer (fastest to be change) ex: version change of external API used imply modification

2. Business rule layer can also change but least rapidly (ex: vacation policy, salary)

3. Domain model change least than the others (voir pas du tout, ou change que dans cas exceptionel)

exemple de ce que contient chaque couche:

1. Com avec l'ext => fetch ; aussi ce qui est display ?
2. Calculs (salaires, etc...)
3. ??

Récap 5 skills:
1. Be able to discriminate between actions, calculations and data
2. Work effectively with immutable values
3. Higherorder calculations and actions
4. Data modelling
5. Functional architecture

# Réstitution
Programmation fonctionnelle => PF
## Intro
Donne pas de définition de la programmation fonctionnelle 
mais plutôt 5 skills que doit posséder un dev faisant de la programmation fonctionnelle

PF décrit comme étant un paradigme de programmation
et mise en comparaison avec la programmation orienté objet

Ces 5 skills peuvent être utilisé avec d'autres paradigms

# Skill 1 (le plus important selon lui)
"Discrimate between actions, calculations and data"
> Faire la distinction entre les calculs, les effets de bords et la data.
{.is-success}

- Calculs
Fonctions idempotentes
=> Retourne le même résultat avec les même arguments, indépendamment de l'endroit de l'execution ou du "contexte" ou du nombre d'éxecution.

Appelées "pure fonctions".

- Effets de bord (actions)
Fonctions (ou autres ? (elt) ) non idempotent
cad ??

Appelées "impure fonctions, functions with side-effects => fonctions avec des effets de bords"

- Data
Enregistrer des informations dans des variables par exemples

> Il précise qu'en général il faut avoir le moins de code possible qui correspond à des effets de bords pcq ça créer de la complexité
{.is-info}

# Skill 2
"Work effectively with immutable values"
> Être capable de travailler efficacement avec des valeurs immuable (qui ne change pas)
{.is-success}

C'est compliqué d'apporter des modifications sur des éléments qui sont "deep in nested structures" (répercussions en chaînes)

# Skill 3
"Using and creating Higherorder calculations and actions"
> Créer et utilisé des calculs et actions (effets de bords) d'ordre supérieurs
{.is-success}

Calculs et actions d'ordres supérieurs signifie
fonctions qui peuvent êtres traités comme n'importe qu'elle autre valeurs
=> peut être passé comme argument d'une fonction
=> peut être retourné par une fonction
=> peut être stocké dans une variable

Exemples données de fonctions d'ordre supérieur => map(), filter(), reduce()

# Skill 4
"Data modeling"
> Modélisatoin des données
{.is-success}

Structurer efficacement les données pour les utiliser de façon optimale

2 Types de données:
- "Public facing data"
ex: API
Contraintes spécifique: "human readable", utilisable par d'autres dév

- Internal data
Contraintes: efficace, disponible, ...

# Skill 5
"Architecture skills"
> Architecture skills
{.is-success}

Corrrespond à l'abilité à comprendre et mettre en place des principes architecturaux, les patterns et les bests practices

Principes d'architecture necessaire.

Ex de pattern d'architecure reactive architecture (Redux, Elm architecture, re-frame)

Dont l'idée principal est => des events sont générés puis consommées.

Générant ainsi des view.

# Pour la réstitution
À appronfondir:
Comment définir effets de bords ou calculs
(skill 2)

# Autres
Paradigmes
Autres paradigms que programmation fonctionnelle et orienté objet ?
(Redux, Elm Architecture, re-frame in ClojureScript)
Approfondir le terme effets de bords; Architecture skills
Réécouter - Work effectively with immutable values - Higherorder calculations and actions - Data modeling
Demander explication à chatgpt (exemple concret à concept abstrait)

# Autres ressources cités
Son livre => Grokking Simplicity, Eric Normand

Structure and Interpretation of Computer Programs, JavaScript Edition (2022) 