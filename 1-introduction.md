# Chapitre 1: Introduction

## Objectifs

- Caracteristique de la base de donnée **(Modèle Relationnel, Entité-Association)**
- Pouvoir creer un schema de base de donnée et la creer en SQL
- Etudier la conception de base de donnée: Créer une base de donnée sécurisée, performante et évolutive
- TP (SQL)

## Pourquoi étudier les bases de données?

- Gestion efficace des données
- Accès rapide et sécurisé aux données
- Analyse et prise de décision
- Automatisation des tâches (ex: facturation, paie, etc)
- Interopérabilité des applications (ex: application web, mobile, etc)
- Compétence très recherchée sur le marché du travail
- Evolution technologies (Big Data, Machine Learning, etc)

## Définitions partie 1

- ### Base de donnée

Collection de données cohérentes et structurées

- ### Système de Gestion de Base de Donnée (SGBD)

Ensemble de logiciels coordonné permettant de <b>décrire, mémoriser, manipuler, traiter et interroger</b> efficacement des données spécifiques avec une grande masse d'informations partagées par plusieurs utilisateurs.

---

### Système de Gestion de Base de Donnée (SGBD)

Logiciel(s) assurant structuration, stockage, maintenance, mise à jour et consultation des données d'une base de donnée

## Exercice 1 (Modècle conceptuel de données)

Voir le dossier Exercice 1.

## Chapitre 1: Introduction à la conception de base de donnée

### Concepts de base de donnée

- Les fichiers ne suffisent pas (pour des application complexes) car

  - il faut gérer en écrivant du code spécifique:
    - La cohérence des données
    - La structure des données
    - Les algo de recherche et de mise à jour des données
  - ils n'assurent pas toujours la sécurité des données

- Nées au début des années 70
- On a vu l'apparition de'un grand nombre de SGBD qui ont permis de gérer des données de plus en plus volumineuses et complexes

- Haut degré d'indépendance entre les données et les applications (indépendance logique/physique)

### Rôle essentiel des BD

- Assurer le stockage des données
  - garantie de pérénnité des données
  - garantie de la cohérence des données

- Prendre en compte la structure des données

- Permettre des utilisations simultannées et autorisées:
  - contrôle d'accès et gestion de la concurrence

- Trouver rapidement une information (trier par...croissant/décroissant, etc)

### Présentation des SGBD (Système de Gestion de Base de Donnée) (1)

#### Définition

##### SGBD

Ensemble de logiciels coordonné permettant de **décrire, mémoriser, manipuler, traiter et interroger** efficacement des données spécifiques avec une grande masse d'informations partagées par plusieurs utilisateurs.

#### Que proposent les SGBD

- La **définition** de la structure des données
- La **mise à jour** des données
- La **recherche** des données
- Le **controle** des données (sécurité, intégrité, concurrence)

nb : Languages textuels ou interfaces graphiques

### Relation BD et SGBD

Les données de la base de données vont être **interrogées et mises à jour** par des utilisateurs via des **programmes d'application** ou des **programmes utilitaires** fournis par le SGBD.

### Défis des SGBD aujourd'hui

- **Multiplication** des types de données
- Informations **incrorrectres** ou **incomplètes**
- **Volumes** et **performances** (une bdd peut être réparties dans de nombreux serveurs)
- Accès aisé par des **non-informaticiens**.
- Données distribuées et nomades (ex: cloud) pour **partager** et **synchroniser** les données
- BD et Web : unification
- Données décisionnelles (BD Traditionnelles / BD d'aide à la décision -> Big Data)
- Emergence des BD Objet
