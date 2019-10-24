# sans pagination pas de console bloque
git --no-pager log --oneline
# 3 commits seulement
git --no-pager log -3 --oneline
Affiche les 3 derniers commits et sort de la commande
Consulter les deux derniers commit
git log --oneline -2
Vous pouvez également consulter les commits d’un auteur en particulier :
git log --author "Antoine07"
Mais vous pouvez consulter l’historique à l’aide des commandes suivantes également :
git log --since=1.day
git log --before="2019-09-01"
Vous pouvez également consulter l’historique d’un fichier uniquement :
git log calzone.txt
Vous pouvez également visualiser les modifications au sein d’un fichier ou de
l’ensemble/d’un ensemble des fichier(s) :
git log -p calzone.txt
# Dans l'ensemble des commits
git log -p
# Ou pour les 2 derniers commits
git log -2 -p

Vous pouvez lorsque vous faite une modification dans un fichier avant de l’indexé visualiser les modifications à l’aide de la commande suivante :
git diff

La commande ci-dessous affichera les différences entre le dernier commit et l’index :
git diff --cached$

git diff HEAD~1
HEADˆ1 pour reculé d’un commit en arrière.

Visualiser les modifications entre deux commits donnés
Mais vous pouvez également voir les modifications entre deux commits :
# Récupérez les haches des deux derniers commits
git log --oneline
# Et les logs entre deux commits
git log f5541d6 b058c4f

faire des stat sur les différences opérées dans les fichiers:
git diff --stat

Annuler les modifications dans l’espace de travail:
git restore

Modifier un message de commit:
# Avant toute chose
git status
# vérifiez les deux derniers commits avant
git log -2
git commit -m "liste complète de toutes les pizzas" --amend
# vérifiez les deux derniers commits après
git log -2

Nous allons utiliser cette commande pour remettre un fichier dans son état
initial:
git checkout

Créer un commit revert d’annulation du dernier commit réalisé :
git revert 419e298