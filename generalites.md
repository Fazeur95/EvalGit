# s'enregistre dans .gitconfig de votre compte user
git config --global user.name
git config --global user.email

# Définir un éditeur pour écrire le texte du commit
# Normalement lors de l'installation automatique de Git
# sous Window ou Mac un éditeur est déjà défini
git config --global core.editor vim

# pour un dépôt en particulier, dans le fichier config du dossier .git/
$ git config --local user.name
$ git config --local user.email 

Pour initialiser un projet Git il faut en premier lieu tapez la ligne de commande
suivante :
git init

Pour voir si tout fonctionne bien vous vous placerez dans le dossier versionné et taperez la commande suivante :
git status

Ajouter un fichier dans la zone d'index :
git add

Désindexer le fichier :
git rm --cached

Permet de voir ce qu’il y a dans l’historique :
# Commande linux
find .git/objects -type f

Création d'un commit : 
# version courte
git commit -m ""
# équivalent, dans ce cas vous avez un éditeur qui s'ouvre
# ce dernier vous permet d'expliquer
# plus pécisémment ce que vous venez de faire
git commit

Visualiser les logs :
git log

Vérifiez que vous avez bien fait votre commit avec l’option suivante :
$ git log --oneline
# ou une autre commande équivalente
$ git shortlog

# Blame qui a fait la modif !
$ git blame -L 40,60 readme.md # rechercher qui a fait les modifs par ligne -L
$ git blame --since=3.weeks -- readme.md # depuis 3 semaines avec auteurs des modifications
$ git blame -L "/^### /" readme.md # recherche avec expression régulière

Renommer un fichier :
git mv mon_ancien_fichier mon_nouveau_fichier
git status

Une commande utile pour voir tous les fichiers suivis :
git ls-files




Remarques sur les patterns à utiliser pour exclure des fichiers :
vendor --> ignore tous les dossiers vendor
9
/vendor --> ignore le dossier vendor à la racine du dépôt
doc/foo/ --> matchera avec doc/foo mais pas a/doc/foo
foo/ --> matchera avec a/foo et foo
foo/* --> matchera avec n'importe quel fichier autre qu'un "/"
*.txt --> ignore tous les fichiers qui ont cette extension dans le dépôt : racine, dossier et sous dossier.
foo/*.txt --> ignore tous les fichiers de ce type dans les dossiers foo de l'application.
/*.txt --> ignore juste au niveau racine du dépôt.
**/foo --> ignore foo/a, bar/foo/a mais n'ignore pas foo/a/b
foo[0-9] --> ignore foo0, foo1, ... foo9
foo --> ignore a/foo, foo/a/b, a/b/foo, ...
foo/**/bar --> ignore foo/a/b/c/bar, foo/bar, ...

