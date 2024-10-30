1. Vérifier la configuration actuelle de Git
git config --global user.name
git config --global user.email

2. Modifier votre adresse e-mail
Si vous avez mal configuré votre adresse e-mail, vous pouvez la modifier en utilisant la commande
suivante :
git config --global user.email "nouvelle_adresse@example.com"

3. Vérifier à nouveau
Après avoir fait la modification, vous pouvez exécuter à nouveau les commandes de vérification pour
vous assurer que la nouvelle adresse e-mail est bien enregistrée :
git config --global user.name
git config --global user.email

6. Ajouter un fichier README.md après coup et committer les changements
Créer le fichier README.md :
echo "# Mon Projet" > README.md
Ajouter et committer le fichier :
git add README.md
git commit -m "Ajout de README.md"
Pousser le commit vers le dépôt distant :
git push origin main
7. Définir un dépôt distant si non configuré lors de la création du projet
Ajouter l’URL du dépôt distant :
git remote add origin [URL-du-dépôt]
Pousser les commits vers le dépôt distant
git push -u origin main
3. Annuler les modifications locales d'un fichier avant de les ajouter à l'index
 Revenir aux changements du dernier commit pour un fichier spécifique :
git checkout – nom_du_fichier
. Visualiser les fichiers prêts à être commités dans Git (staging)
 Voir les fichiers en staging (prêts à être commités) :
git status

4. Suivre (track) un dépôt distant et récupérer toutes les branches de ce dépôt
 Ajouter un dépôt distant et récupérer toutes les branches : Si le dépôt distant est déjà
configuré, vous pouvez récupérer toutes les branches avec cette commande :
 git fetch –all
Cela télécharge toutes les branches sans les fusionner dans les branches locales.

 Suivre une branche spécifique : Si vous voulez suivre une branche spécifique (par exemple,
feature-branch), vous pouvez utiliser :
git checkout --track origin/feature-branch
Cela crée une branche locale qui suit origin/feature-branch.
5. Supprimer une branche locale après l'avoir fusionnée dans main
Supprimer la branche locale : Après avoir fusionné la branche dans main et vérifié que tout est
en ordre, vous pouvez la supprimer localement avec cette commande :
git branch -d nom-de-la-branche
Si la branche n’a pas encore été fusionnée et que vous souhaitez la supprimer de
force, utilisez -D (notez que cela est irréversible) :
git branch -D nom-de-la-branche
8. Comment interrompre un rebase en cours si vous avez commis une erreur ?
 Annuler un rebase en cours : Si vous avez fait une erreur pendant le rebase et que vous
souhaitez l'annuler, vous pouvez utiliser la commande suivante :
git rebase –abort
Cela annule toutes les modifications du rebase et ramène la branche à son état
initial, avant que le rebase ne commence.
9. Comment lister les commits qui vont être rebasés avant de lancer un rebase ?
 Lister les commits à rebaser : Pour voir les commits de ma-fonctionnalite qui ne sont pas dans main
 -git log master..ma-fonctionnalite
 Cette commande montre la liste des commits sur ma-fonctionnalite
qui seront rebasés sur main. Vous pouvez ainsi vérifier quels commits seront affectés avant de lancer le rebase.
 8. Comment afficher la liste des branches actives et en cours de développement dans GitFlow ?
Afficher les branches actives : Vous pouvez utiliser la commande suivante pour lister toutes les branches

git branch
 Cette commande affiche toutes les branches locales, y compris celles créées avec GitFlow.
 Lister les branches GitFlow spécifiques : Bien que GitFlow ne
 fournisse pas une commande directe pour afficher les branches

actives, vous pouvez voir les branches GitFlow spécifiques (commefeature, release, hotfix) en utilisant la commande suivante :

git branch | grep "feature/" # pour les branches de fonctionnalités
git branch | grep "release/" # pour les branches de versions
git branch | grep "hotfix/" # pour les branches de correctifs
9. Comment annuler une branche de correctif (hotfix) avant de la finaliser si vous constatez uneerreur ?
 Annuler une branche de correctif (hotfix) : Pour supprimer une branche de correctif avant safinalisation, assurez-vous d'être sur une autre branche (comme develop ou main) et utilisez git flow hotfix delete mon-correctif
Si cette commande n’est pas disponible, vous pouvez supprimer manuellement la branche
hotfix :
git branch -D hotfix/mon-correctif
