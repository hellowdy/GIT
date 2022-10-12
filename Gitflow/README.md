# Gitflow

## Description

Gitflow est une extension Git développée par Vincent Driessen.
Cette extension permet de gérer le versioning d'un projet et pose un cadre de travail.
Les développeurs qui travaillent sur un projet géré par Gitflow doivent suivre un Workflow établi et éprouvé.

## Installation

- Une installation fonctionnelle de git est requise
- Gitflow fonctionne sur macOS, Linux et Windows

### Commande d'installation

#### Mac OS

_Homebrew_

```
brew install git-flow-avh
```

##### Linux

```
apt-get install git-flow
```

##### Windows

Sous Windows, vous devrez télécharger et installer git-flow.
[Installation GitFlow](https://git-scm.com/download/win)

### Fonctionnement de Gitflow

Gitflow est un ensemble de règles simples qui se basent sur le fonctionnement par branche de Git.
Gitflow génére de manière automatique de multiple chose dont les branches ==Main== et ==Develop==.
La branche ==Main== est la branche dite principale souvent utilisé lors de la production.
La branche ==Develop== rassemble toutes les fonctionnalitées mais il est recommandé de ne pas faire de modification directement dans cette branche
Il permet de réalisé plusieurs commande git en une seule ligne.

</br>

### Initiation de gitflow

Pour Démarrer l'iniatialisation, lancez la commande :

```
git flow init
```

L'extension propose de préfixer les branches de Gitflow. Il est conseillé de laisser les valeurs par défaut.(appuyer sur entrée à chaque proposition)

</br>

### Démarrer une fonctionnalité

Pour gitflow démarrer une fonctionnalité correspond à la création d'une nouvelle branche de type ==feature==.Cela permet de développer plusieurs fonctionnalités en parallèle, souvent utilisé pour le travail en équipe.

Pour démarrer une fonctionnalité, lancer la commande :

```
git flow feature start Myfeature
```

Cette commande créer une branche et ce positionne sur celle-ci.

**Commande correspondante sur Git :**

```
git checkout develop
git checkout -b feature/Myfeature
```

</br>

### Finaliser une fonctionnalité

Lorsque votre fonctionnalité est finie, vous devez lancer la commande :

```
git flow feature finish Myfeature
```

Gitflow retourne sur la branche ==Develop== et merge la branche ==feature==/Myfeature, une fois le merge réussi la branche est supprimée.

**Commande correspondante sur Git :**

```
git checkout develop
git merge feature/Myfeature
git branch -D feature/Myfeature
```

</br>

### Création de version

Gitflow permet aussi de gérer les versions avec la création de branche ==release==, pouvant être utilisé lors de la production.

Pour crée une version lancer la commande :

```
git flow release start 1.0.0
```

L'extension crée une branche ==release== en ce plaçant sur la branche ==Develop==.

</br>

###

Après avoir effectué les actions voulues, vous devez lancer la commande :

```
git flow release finish 1.0.0
```

Cette commande merge la branche ==release== à la branche ==main==.

**Commande correspondante sur Git :**

```
git checkout main
git merge release/1.0.0
```

En cas d'erreur lors de la production, la création d'une branche ==hotfix== peut être crée.
Pour cela lancer la commande :

```
git flow hotfix start (nom de la branche)
```

Cette commande crée une branche à partir de la branche ==main==.

**Commande correspondante sur Git :**

```
git checkout main
git checkout -b hotfix/(nom de la branche)
```

Lorsque votre ==hotfix== est terminé lancer la commande :

```
git flow hotfix finish (nom de la branche)
```

Cette commande envoie les changements à la fois sur la branche ==main== et la branche ==Develop==.

**Commande correspondante sur Git :**

```
git checkout master
git merge hotfix/(nom de la branche)
git checkout develop
git merge hotfix/(nom de la branche)
git branch -D hotfix/(nom de la branche)
```

**Mot clé Publish**

Le mot clé ==Publish== permet le partage de branche local, très pratique pour travailler avec d'autres développeurs.

```
git flow release publish 1.0.0
```

Si un autre développeur souhaite travailler dessus, il faudra qu'il lance cette commande :

```
git flow release pull origin 1.0.0
```
