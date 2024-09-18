# Chapitre 3: Modèle Entité-Association / Entité-Relation

## Introduction

- **Le modèle Entité** - Relation repose sur une perception du monde réel sous forme d'un ensemble d'objets appelés **entités**, associés au moyen d'un ensemble de relations.
- Cette modélisation a été développée de façon à faciliter la conception des architectures de base de données.

## Entité - Propriété - Identifiant

### Entité

- C'est un type d'objet ou de concept (concret ou abstrait) manipulé par l'organisation étudiée. On peut la définir sans faire référence à d'autres entités (Exemple: entités Client, Produit, Commande, etc).
- Représentation de l'entité Etudiant:

| **Etudiant** |
|--------------|
| **Matricule: 123456** |
| Nom: Dupont |
| Prénom: Jean |

### Propriété (ou Attribut) d'une entité

- Une entité est caractérisée par un ensemble de propriétés (ou attributs).
- Exemple : Des propriétés possibles de l'entité Etudiant sont le CodeEtudiant, le nom, le prénom, l'adresse, le numéro de téléphone, etc.
- Représentation de l'entité Etudiant avec ses propriétés :

| **Etudiant** |
|--------------|
| **Matricule: 123456** |
| **Nom: Dupont** |
| **Prénom: Jean** |

### Contrainte d'intégrité

- Elles permettent de limiter les valeurs possibles d'une propriété.
- Exemple :
  - La propriété CodeEtudiant doit être unique pour chaque étudiant.
  - L'âge doit être compris entre 0 et 120 ans.

### Occurrence d'une entité

- C'est un élément individualisé et unique appartenant à cette entité (un tuple).

### Identifiant / Clé d'une entité

- C'est une propriété (ou un ensemble de propriétés) qui permet d'identifier de manière **unique** une occurrence d'une entité.
- Toute entité a un identifiant qui est constitué d'une ou plusieurs de ses propriétés et qui permet d'identifier sans ambiguïté chaque occurrence de l'entité.
- Dans un schéma de base de données, l'identifiant d'une entité est en première position et **souligné**.
- Représentation de l'entité Etudiant avec son identifiant :

| **Etudiant** |
|--------------|
| **Matricule: 123456** |
| Nom: Dupont |
| Prénom: Jean |

## Relations (ou associations) entre entités

### Définition

- Une relation permet de relier plusieurs entités. Elle est généralement caractérisée par un verbe.
- Exemple: L'entité Etudiant est en relation avec l'entité Cours par l'association "Suivre".

| **Etudiant** | --(Suivre)-- | **Cours** |

- La dimension d'une relation est le nombre d'entités qui y participent.
- La collection d'une relation est le nombre d'occurrences d'une entité qui peuvent être reliées à une occurrence d'une autre entité.

### Occurrence d'une relation

- C'est une relation individualisée constituée d'une et une seule occurrence des entités qu'elle relie.
- Exemple:

| **Etudiant** | --(Suivre)-- | **Cours** |

Une occurrence de la relation "Suivre" est constituée d'un étudiant et d'un cours.

### Propriété d'une relation

- Une relation peut avoir des propriétés qui lui sont propres.
- Exemple : La relation "Suivre" peut avoir comme propriété la note obtenue par l'étudiant au cours.

| **Etudiant** | --(Suivre: Note = 15)-- | **Cours** |

Les propriétés d'une relation sont souvent des propriétés qui ne sont pas des propriétés des entités reliées !

### A Retenir / Récap

- A une occurrence d'une relation, il ne peut y avoir qu'une seule valeur pour chacune des propriétés rattachées à cette relation.
- A une combinaison d'occurrence d'entités reliées par une relation, il ne peut y avoir au plus qu'une occurrence de la relation.
- Plus simplemement : Un attribut peut être placé dans une relation uniquement lorsqu'il dépend de toutes les entités liées par la relation.

## Cardinalité des relations

- C'est le nombre minimum et maximum d'occurrence d'une relatio pour une occurrence d'une entité.
- Exemple:
  - | **Enfant** | 1,1 --(Avoir)-- 0,N | **Père** |
  - | **Client** | 0,N --(Acheter)-- 1,N | **Produit** |

- Cardinalité **minimum** d'une relation (gauche)
  - C'est le nombre minimum de fois ou chaque occurrence d'une entité participe à une relation
- Cardinalité **maximum** d'une relation (droite)
  - C'est le nombre maximum de fois ou chaque occurrence d'une entité participe à une relation

### Types de cardinalité

- <u>Obligatoire</u>
  - **1,1** : L'entité doit participer une fois à la relation
  - **1,N** : L'entité doit participer au moins une fois à la relation
- <u>Facultatif</u>
  - **0,1** : L'entité peut ne pas participer à la relation
  - **0,N** : L'entité peut participer plusieurs fois à la relation
  
### Comment le lire ?

- | Enfant | **1,1** --(<u>Avoir</u>)-- **0,N** | Père |
  - Un enfant <u>*a*</u> **un et un seul père**, mais un père peut <u>*avoir*</u> **0 à N enfants**.
  - NB : C'est l'inverse de l'UML où on met le cardinalité de l'autre côté. :angry:

## Règles de normalisation - Entité

- Première forme normale (1FN)
  - Chaque entité doit posséder un identifiant unique
- Deuxième forme normale (2FN)
  - Chaque attribut doit dépendre de la clé primaire
- /!\ Troisième forme normale (3FN)
  - Chaque attribut doit dépendre de la clé primaire et de **rien d'autre**.<br> *Par exemple, un attribut 3 ne doit pas dépendre de l'attribut 4 ou 5 ou 6 ou....*

## Règles de normalisation - Relation

- /!\ Normalisation des relations
  - Les attributs des associations doivent **dépendre** des identifiants de **toutes les entités en association**.
    - Par exemple, la quantité commandée dépend à la fois du n° de client et du n° de produit.
    - Par contre la date de commande non. Il faut donc créer une entité commandes à part.

## Construction du MCD

- Pour la construction du MCD, on a à notre disposition:
  - Un **dictionnaire des données** (liste des attributs + différentes caractéristiques)
  - Des règles de gestion (Ensemble de règles qui vont permettre notamment de fixer les cardinalités)
  - Une liste des résultats attendus

- ### Phase A: Epuration du Dictionnaire des données

  - Suppression des synonymes (exemple : N° Salarié et CodeSalarié ; RefProduit et CodeProduit)
  - Suppression des polysèmes (on ne doit pas avoir la même propritété Nom pour NomClient et NomSalarié)

- ### Phase B: Identification des entités

  - Repérer les **Entités** du domaine étudié qui apparaissent le plus **naturellement** (ex: Client, Produit, Commande, etc)
  - Et leur attribuer leurs **propriétés**

- ### Phase C: Etablir les relations entre entités et lister leur propriétés qui leurs sont attribués, si necessaire

- ### Phase D: Fixer les cardinalités

- ### Phase E

  - Vérifier la troisième forme normale (3FN) (Chaque attribut doit dépendre de la clé primaire et de rien d'autre) et la normalisation des relations (Les attributs des associations doivent dépendre des identifiants de toutes les entités en association)
  - Effectuer les corrections nécessaires
  - Une propriété ne peut apparaître qu'une seule fois dans un même MCD.
  - Les propriétés qui sont résultats d'un calcul ne doivent pas apparaître dans le MCD.

#### NB: 

- On peut avoir des relations plurielles:

      | Personne | 0,N -- (Etre l'auteur) -- 1,N | Livre |
      
      | Personne | 0,N -- (Avoir critiqué) -- 0,N | Livre |

- Ou des relations reflexives:

      | Personne | 0,N -- (est le Frère) -- 0,N | Personne |
