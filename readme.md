# GIT
GIT a été créé en 2005 par Linus Torvalds, créateur de LINUX. 
C'est un Logiciel libre, gratuit, permettant de travailler en collabaration et de sauvegarder son travail. Tout en protégeant le code source, il permet de suivre chaque changements apportés, de garder une trace et revenir en arrière si on fait une erreur entre autre.


## Installation
#### linux : 
```
sudo dnf install git-all
```
#### Mac : 
  Homebrew:
 ```
  brew install git
 ```
#### Windows: 
[Téléchargez-le](https://git-scm.com/download/win)

### Principale commande de base :

| Commande | Description |
| ---- | ---- |
| git init | Initialise GIT dans un dossier|
| git config| Configurer git avec son nom et son mail |
| git status | Affiche l'état des statuts des fichiers|
| git add | Ajoute un ou plusieurs fichier(s) en staging : vous pouvez choisir de prendre un ou plusieurs fichiers avant de commit|
| git commit | Enregistre les changements effectués sur le(s) fichier(s) tout en ajoutant un message détaillant le changement|
| git remote | Lie votre dépôt local à votre dépôt distant, permettant d'envoyer ton fichier sur le dépôt distant|
| git push | Envoi ton fichier sur ton dépôt distant et mets à jour ton projet sur la branche main |
| git pull |  Récupère un fichier sur un dépôt distant et lors d'une collaboration met à jour le contenu|
| git fetch | Télécharge un projet à partir d'un dépôt distant |
| git clone | clone un dépôt à partir d'une URL existante(github) |
| git branch | créer une branche |
| git checkout | change de branche |
| git merge | fusionne l'historique d'une branche dans la branche actuelle|


### Fonctionnement de GIT:


#### Créer un projet à partir d'un dépôt vide
 créer un nouveau repository dans Github
```
git init 
git add nom_du_fichier
git commit -m nom_du_commit 
git remote add origin [ssh.... ou HTTPS...] 
git push -u origin 
```
Si vous voulez add plusieurs dossiers en même-temps :
```
git add .
```

## Les branches 
Une branche dans git permet de se déplacer vers l'un de ces commits avec un pointeur. En avançant dans le projet, les commits augmentent sur la branche main.

Il existe plusieurs branches que l'on peut renommer comme l'on souhaite :  
- La branche par défaut est "master" que l'on doit la renommer en "main". 
- La branche "develop" créer à partir de "main".
- Les branches "feature" à partir de "develop" pour travailler dessus et garder la meilleure version. 
Travailler sur la branche secondaire permet de ne pas détruire le travail de la branche principale et de garder la meilleure version.


 

```
git branch develop 
git checkout develop 
git branch feature1 
git chekckout feature1 
git checkout develop 
git merge feature1 
git branch -d feature1 
```

## Pull request
Récupère un projet upstream permettant de travailler en collaboration.
### Fonctionnement:
1) Fork un projet upstream vers origin
2) Clone le nouveau projet dans le local
3) Créer une new branche
4) Push ton travail sur origin
5) Proposer son projet à upstream

