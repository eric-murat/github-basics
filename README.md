Commandes de bases pour Github

# Installation d'un client Git

# Création d'un compte github.com

# Création d'un repo sur github.com

# SSH
Sources : 
- https://syntaxbytetutorials.com/add-a-github-ssh-key-on-windows/
- https://www.youtube.com/watch?v=WgZIv5HI44o

Méthode à suivre pour ajouter une clé SSH à github :
1. Se placer dans D:\dev puis clic droit/Git Bash Here
2. Générer la clé SSH publique : dans Git Bash, saisir :
```
ssh-keygen -t rsa -b 4096 -C "emurat@free.fr"
```
Taper Entrée
- Saisir une PassPhrase
- Valider en resaisissant la PassPhrase  
La clé publique C:\Users\33619\.ssh\id_rsa.pub a été générée.
3. Ajouter la clé SSH au référentiel :
- Lancer l'agent SSH :
```
eval $(ssh-agent -s)
```
- Puis ajouter la clé :
```
ssh-add ~/.ssh/id_rsa
```
- Saisir la PassPhrase saisie précedemment
4. Ajouter la clé SSH de l'ordinateur à Github :
- Copier la clé dans le presse-papier :
```
clip < ~/.ssh/id_rsa.pub
```
- Ouvrir https://github.com/eric-murat
- Profile / Settings / SSH and GPG keys
- Cliquer sur "New SSH key"
- Saisir :  
  Title : Portable ASUS VivoBook 17  
  Key : CTRL-V
- Valider en cliquant sur "Add SSH key"

# Sauvegarder son travail local sur repo distant sur github.com
PREALABLE: un repo doit avoir été créé sur github.com
* Depuis github.com sur son repo (par exemple eric-murat/github basics) :
- Bouton "Code" / Clone / SSH copier l'adresse SSH du repo dans le presse-papier
* Se placer sur son répertoire de Dev, par exemple D:\dev
* Faire un clic droit / Git Bash Here
* Cloner le repo distant :
```
git clone git@github.com:eric-murat/github-basics.git
```
- Valider l'authenticity en saisissant : yes
* Copier ses fichiers locaux dans le répertoire D:\dev\github-basics qui vient d'être créé
* Au niveau de Git Bash, se placer dans le nouveau répertoire :
```
cd github-basics
```
* Ajouter les fichiers à l'index :
```
git add .
```
* Commiter dans le repo local :
```
git commit -m "Ajout de Github Cheat Sheet"
```
* Pousser les Commits sur le repo distant :
```
git push -u origin main
```







