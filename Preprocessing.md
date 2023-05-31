---
title: Preprocessing
description: 
published: true
date: 2023-05-06T10:39:16.270Z
tags: 
editor: markdown
dateCreated: 2023-05-05T09:20:53.286Z
---

# Infos générales
> On **encode** les valeurs qualitatives et on **normalise** les valeurs quantitatives
{.is-info}

# Encodage
Comment choisir => ...

## Ordinal
Remplacer des noms de classes par des int auto-incrémenté
ajouter photo

> Chien < chat < oiseau n'a pas de sens 
et influence la plupart des modèles sauf arbres de décision (ex: `random forest`)
{.is-warning}
### LabelEncoder()
`sklearn.preprocessing.LabelEncoder()`
Pour une classe seulement, utilisé pour `y`
```python
y = np.array(['chat','chien','chat','oiseau'])

encoder = LabelEncoder()
encoded_y = encoder.fit_transform(y)

print(encoded_y)
# => array([0,1,0,2], dtype=int64)
```
### OrdinalEncoder()
`sklearn.preprocessing.OrdinalEncoder()`
Utilisé pour `X`
```python
X = np.array([['chat','poils'],
			  ['chien','poils'],
			  ['chat','poils'],
			  ['oiseau','plumes']])

encoder = OrdinalEncoder()
encoded_y = encoder.fit_transform(y)

print(encoded_y)
#=> array([0., 1.],
#		 [1., 1.],
#		 [0., 1.],
#		 [2., 0.]])
```
## One Hot
> Crée une nouvelle colonne par classes et donc augmente le nombre de dimensions
{.is-info}
### LabelBinarizer()
`sklearn.preprocessing.LabelBinarizer()`
Utilisé pour `y`
```python
y = np.array(['chat','chien','chat','oiseau'])

encoder = LabelBinarizer()
encoded_y = encoder.fit_transform(y)

print(encoded_y)
#=>[[1 0 0]
#   [0 1 0]
#   [1 0 0]
#   [0 0 1]]
```
> Pour stocker les informations dans une matrice creuse (sparse matrix) utiliser `sparse_output=True`
{.is-warning}
### OneHotEncoder()
`sklearn.preprocessing.OneHotEncoder()`
Utilisé pour `X`
```python
X = np.array([['chat','poils'],
			  ['chien','poils'],
			  ['chat','poils'],
			  ['oiseau','plumes']])

encoder = OneHotEncoder()
encoded_y = encoder.fit_transform(X)

print(encoded_y)
#  (0, 0)	1.0
#  (0, 4)	1.0
#  (1, 1)	1.0
#  (1, 4)	1.0
#  (2, 0)	1.0
#  (2, 4)	1.0
#  (3, 2)	1.0
#  (3, 3)	1.0

#<4x5 sparse matrix of type '<class 'numpy.float64'>'
#	  with 8 stored elements in Compressed Sparse Row format>
```
> Ici `sparse_output=True` par default
{.is-warning}
### MultiLabelBinarizer()
`sklearn.preprocessing.MultiLabelBinarizer()`
??



# Normalisation
Comment choisir => ...
si potentiel valeurs abérantes => robustscaler()
si définir un min et max fixe n'a pas de sens selon l'information => standardscaler()
sinon => minMaxScaler()
> Normaliser les valeurs correspond à les mettre sur une même échelle
{.is-info}

> Lors de l'utilisation de nouvelles données, la normalisation doit être refaite pour garder les proportions
{.is-warning}

> StandardScaler() et MinMax() sont très sensibles aux outliers (valeurs abérantes)
> {.is-danger}
## MinMax()
`sklearn.preprocessing.MinMaxScaler()`
> Transforme les valeurs pour qu'elles soient comprises entre 0 et 1
> Modification des données mais conservation des rapports de distance donc valeurs 'équivalentes'
{.is-info}

```python
X = np.array([[70],
             [80],
             [120]])
             
scaler = MinMaxScaler()
normalized_X = scaler.fit_transform(X)

print(normalized_X)
# [[0. ]
#  [0.2]
#  [1. ]]
```
feature_range peut être précisez !!!!!!!!!!!!!!!!!!!!!!!!!
## StandardScaler()
`sklearn.preprocessing.StandardScaler()`
> Consiste à standardiser les valeurs => La feature à une **moyenne de 0** et les **écarts types sont de tous de 1**
> Bien pour les modèle statistque comme svm decomposition principale component analysis ??
{.is-info}

```python
X = np.array([[70],
             [80],
             [120]])

scaler = StandardScaler()
normalized = scaler.fit_transform(X)

print(normalized)
# [[-0.9258201 ]
#  [-0.46291005]
#  [ 1.38873015]]
# Moy = 0 => 1.38873015 + (-0.9258201) + (-0.46291005) /3 =0
```
## RobustScaler()
`sklearn.preprocessing.RobustScaler()`
> Peu sensible aux outliers contrairement aux 2 normaliseurs précedents
{.is-info}

```python
X = np.array([[70],
             [80],
             [120]])

scaler = RobustScaler()
normalized = scaler.fit_transform(X)

print(normalized)
# [[-0.4]
#  [ 0. ]
#  [ 1.6]]
```
STOPED AT:
https://youtu.be/OGWwzm304Xs?t=1426


# Imputation
Remplacer les valeurs manquantes
# Sélection
Feature selection
# Extraction
# Méthodes et propriétés des transformers de preprocessing
# Ressources
https://scikit-learn.org/stable/modules/classes.html#module-sklearn.preprocessing
https://www.youtube.com/watch?v=OGWwzm304Xs&t=1174s&ab_channel=MachineLearnia


et/ou ajouter les infos ex: propriété de transformers => ex: encoded.classes_
Pour chaque procédé précisez compatibilité avec les types de modèles
et les cas d'utilisation
demander à GPT
différence standardisation et minmax dans l'utilisation ?
inconv ? (robust scaler par ex)
pro cons pour chaque transformers
obj => aider au choix !
lien pour plus de précision sur chaque transformers => calcul math ? necessaire ?
à revoir polynomial features !
		ex: permet de créer une regression poly même si une seule feature disponible
Faire un TODO:
Discrétisation ; polynamialFeatures ; 