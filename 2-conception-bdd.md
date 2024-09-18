# Chapitre 2: Conception de base de donnée

## Introduction

- On appelle **conception de base de donnée** la phase d'analyse qui aboutit à déterminer le futur contenu de la base de donnée.
- Elle représente un processus complexe.
- Elle peut être facilitée par une décomposition en niveau de description:
  - **Modèle conceptuel de données** *<- on est là*
  - **Modèle logique de données**
  - **Modèle physique de données**

Lorsqu'une entreprise décide, pour son informatisation, d'adopter une approche de BDD, le premier **problème** à résoudre, peut-être le plus difficile, est de déterminer **les informations** qu'il conviendra de traiter dans la bdd 
(Entretiens et validation avec l'ensemble des utilisateurs auquel et futurs de cette bdd)

- Il faut ensuite **implanter la base de données**, c'est-à-dire déterminer comment les informations seront stockées et comment elles seront manipulées.
- Une fois l'implantation terminée, peut commencer **l'utilisation de la bdd**
- Suit ensuite la phase qui concerne la **maintenance** de la bdd

### Cycle de vie d'une BDD:

1. **Conception** de la base de donnée

*Moèle conceptuel de données*

2. **Implantation** de la base de donnée

*Modèle logique de données*

3. **Utilisation** de la base de donnée

*Interrogation mise à jour des données*

4. **Maintenance** de la base de donnée

*Correction des erreurs, évolution, etc...*

## Généralités

- Une bonne représentation du **monde réel** (**Fidelité**)
- Une **non-redondance** des données
- Une **indépendance** des données (indépendance logique/physique car les données peuvent être stockées de différentes manières)
- La **sécurité** et la **confidentialité** des données
- La **performance** des applications (les temps de réponse doivent être courts)

## Conception d'une base de donnée

- ### Bien réfléchir à la **structure** de la base de donnée avant de la créer :thumbsup:

**Etape 1**. Analyse

**Etape 2**. Réalisation informatique (programmation, tests, validation)

**Etape 3**. Mise en service - Utilisation

- ### La phase d'Analyse se décompose elle-même en plusieurs étapes:

#### Etape 1 Evaluation des besoins actuels

    Lister en vrac :

     - Les documents à éditer
     - Les statistiques à obtenir
     - Les éléments à calculer
     - Les info à stocker (rubriques)

#### Etape 2 Evaluation des besoins futurs

    Anticipier:
    
     - Quelles seront les évolutions possibles de la base de données
     - La taille des rubriques prévue est-elle suffiante ?

#### Etape 3 Structuration des informations

    Une fois les besoins définis et les informations à stocker énumérées, il faut classer les informations par thèmes/domaines.

### Architecture à trois niveaux

On a besoin de **vues externes** pour les utilisateurs, d'une vue conceptuelle pour les concepteurs et d'une vue interne pour les informaticiens.

### Modélisation des données

- **Principe**: Séparer la description des données et manipulation par des programmes
- **Description**: Spécification des structures des données et de leurs types.
- **Manipulation**: Opération d'interrogation, d'insertion, mise à jour, suppression.
- **Réalisation**: Norme ANSI-SPARC (permet de séparer les données et les programmes)

Univers réel -> Schéma conceptuel -> Schéma logique -> Schéma physique

- **Niveau conceptuel**: 
  - Déscription des besoins => Modèle conceptuel de données
- **Niveau logique**: 
  - Traduction du modèle conceptuel en modèle logique => Modèle logique de données
- **Niveau physique**: 
  - Choix des structures de stockage des données par les admin-systèmes
  - Shéma interne: description des choix d'enregistrement des données dans les fichiers
  - Fait appel à un nouveau modèle, le modèle interne, o`les concepts sont ceux de fichier, organisation de fichier, index, chemin d'accès, clé, ...

### Spécificités d'un SGBD

- Très grande quantité de données à gérer
- Besoin d'interroger, mettre à jour souvent, rapidement et efficacement ces données
- Contrôler la redondance d'info
- Partage des données
- Gérer les autorisations d'acès / Sécurité des données
- Offrir des interfaces d'accès multiples
- Verif les contraintes d'intégrité
- Assurer la reprise après incident

### /!\ Fonctions des SGBD /!\

- Définition de la structure des données -> Langage de Définition de Données (LDD)
- **Recherche des données** --
- **Mise à jour des données** -- Langage de Manipulation de Donnée (LMD)
- **Transformation des données** --
- Contrôle de l'intégrité des données
- Gestion de transactions et sécurité
