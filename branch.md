La commande pour créer une branche :
git branch dev
Affichez maintenant l’ensemble des branches se trouvant sur votre dépôt :
git branch

Pour se déplacer sur l’autre branche, on utilise la commande checkout comme
suit :
# on déplace le HEAD sur la branche dev
$ git checkout dev

Si on souhaite revenir sur la branche master on exécutera la commande suivante :
# On déplace le HEAD sur la branche master
$ git checkout master
Vous pouvez également créer une branche et vous déplacez dessus en une seule commande :
# on déplace le HEAD sur la branche master
$ git checkout -b feature_header

Vous pouvez facilement supprimer une branche en utilisant l’une des commandes
suivantes :
git branch -d [nom de votre branche]
Forcer la suppression d’une branche :
git branch -D [nom de votre branche]

Voici les commandes à exécuter pour faire le merge :
# On suppose que l'on est sur dev
git checkout master
# On merge dev dans master
git merge dev

Voici les commandes à exécuter pour faire le merge :
# On suppose que l'on est sur dev
git checkout master
# On merge dev dans master
git merge dev

Lister toutes les branches non mergées :
git branch --no-merged

Visualisez le graph des commit à partir de la branche master maintenant :
git log --oneline --graph

# Listez sur la branche les stash
git stash list
# On recupère ce qui était dans la stash
# Et on l'applique => récupération de son code modifié
git stash apply
#On supprime ce qui se trouve dans la remise
git stash drop
# Essaye de remettre ce qui était dans l'index
git stash apply --index


Voici quelques commandes utiles pour la création des tags :
# Tag annoté
$ git tag -a v1.0 -m "version 1 de l'application"
# Tag léger peu utilisé
$ git tag v1
# Etiquetter après coup sur un commit donné
$ git tag -a v1.0.1 -m "version 1.0.1" 9fceb2
list & show tags
# liste les tags
git tag
# Rechercher des tags particuliers
git tag -l 'v8.*'
# Voir un tag annoté
git show v8.2



Créez un serveur Git sur votre machine locale :
# Sur votre bureau
$ cd GitServer
$ mkdir fichier.git
$ cd fichier.git
# Création du server Git
$ git --bare init
Dossiers du serveur Git :
# Contenu du dossier my_lessons_server.git
branches config description HEAD hooks info objects refs
Sur le bureau également ou dans votre dossier de cours créez maintenant un
dossier puis récupérez la branche distante du serveur Git :
# Sur le même poste
$ cd my_lessons
$ git init
$ echo "# Lessons" > README.md
$ git add .
$ git commit -m 'first commit'
# Spécifiez un chemin absolu sur votre machine
# pour indiquer où se trouve votre serveur
# origin est arbitraire mais par convention on l'utilise
# pour nommer son dépôt distant
$ git remote add origin C:\Labs\my_lessons_server.git
# Sous Linux ou Mac dans un media
# $ git remote add origin /media/antoine/3065-6232/my_lessons_server.git
# Publier sur la branche distante (serveur)
# git push [nom-distant] [nom-de-branche]
# push la branche master dans votre dépôt dans
# le serveur origin
$ git push origin master

