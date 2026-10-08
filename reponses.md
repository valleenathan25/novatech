Compte rendu du TP final Git NovaTech


Mission 5

Pour voir l'historique avec les branches et les fusions j'ai tapé git log --oneline --graph --all

1. Le premier commit est 2c6a94a. C'est la création de la page d'accueil.

2. Le commit qui ajoute la page Contact est c93cf0e. C'est la création de la page Contact.

3. Il y a 8 commits en tout. Ça compte aussi le commit de fusion de la branche contact.

4. Pour voir l'historique en graphique j'ai tapé git log --oneline --graph --all

Pour regarder un commit de la page Contact en détail j'ai tapé git show c93cf0e

On voit qui a fait le commit et quand. On voit aussi les lignes ajoutées dans contact.html avec le menu le titre et les cases Nom et E-mail.


Mission 6

J'ai ajouté © 2026 NovaTech en bas de la page d'accueil et j'ai fait un commit avec le message modif. Ce commit avait le numéro abf9b8d.

Ce message ne dit pas ce qui a changé. Alors j'ai changé le message du dernier commit avec git commit --amend -m "Ajout du copyright dans le pied de page"

Le commit est devenu 5d84505. Il n'y a qu'un seul commit pour ce changement parce que amend remplace le dernier commit au lieu d'en faire un nouveau.

J'ai envoyé sur GitHub seulement après avoir corrigé le message.


Mission 7

J'ai enlevé le menu le grand titre et le texte de la page index.html sans faire de commit.

git status montrait que index.html était modifié.

Je ne voulais pas garder ces changements. Alors j'ai tapé git restore index.html pour remettre le fichier comme au dernier commit.

Ensuite git status ne montrait plus rien à enregistrer. Le fichier était revenu comme avant.


Mission 8

J'ai ajouté body { display: none; } dans style.css et j'ai fait le commit Test affichage. Ce commit avait le numéro a5322f4.

Ce commit n'était pas bon et je ne l'avais envoyé à personne. Alors je l'ai annulé avec git reset HEAD~1

HEAD~1 veut dire le commit juste avant. git reset ramène la branche sur ce commit. Le commit Test affichage n'est plus dans l'historique.

Sans option git reset ne touche pas aux fichiers. Il enlève juste le commit et le fichier n'est plus dans le staging. C'est pour ça que la règle display none était encore dans style.css.

Avec git reset --hard HEAD~1 la règle aurait aussi été effacée du fichier.

Ensuite j'ai enlevé la mauvaise règle avec git restore style.css


Mission 9

J'ai ajouté la promotion à -90 % sur la page d'accueil et j'ai fait le commit Ajout promotion. Il a le numéro 487399a.

Je l'ai envoyé sur GitHub. Donc les autres de l'équipe peuvent déjà l'avoir.

La promotion était une erreur. Je l'ai annulée avec git revert 487399a

Git a fait un nouveau commit c246c6e qui enlève la promotion. Dans l'historique on voit encore Ajout promotion et juste après le commit qui l'annule.

Ce n'est pas comme à la mission 8. Là le commit était partagé. Si je l'enlève avec reset mon historique ne sera plus le même que celui des autres et ça va poser des problèmes. Revert n'efface rien. Il ajoute un commit qui fait l'inverse. Comme ça tout le monde garde le même historique.


Mission 10

J'ai commencé la page equipe.html sur une branche equipe. Le travail n'était pas fini donc je ne voulais pas faire de commit.

C'était un nouveau fichier. Alors je l'ai d'abord ajouté avec git add equipe.html sinon git stash ne le prend pas.

Ensuite j'ai tapé git stash pour mettre mon travail de côté. Avec git stash list j'ai vu qu'il était bien gardé.

Je suis allé sur main avec git switch main. J'ai corrigé le titre de la page d'accueil qui était écrit Acceuil au lieu de Accueil. J'ai fait le commit 648e4c0 et je l'ai envoyé.

Après je suis revenu sur la branche equipe avec git switch equipe. J'ai récupéré mon travail avec git stash pop.

J'ai fini la page avec les trois personnes de l'équipe. J'ai fait le commit d2db9bf puis j'ai fusionné la branche dans main et je l'ai supprimée.


Mission 11

J'ai créé une branche test avec git switch -c test et j'ai fait trois commits.

f4faf1f change la couleur du menu pour tester.

221f859 corrige la faute dans le grand titre. Bienvenu devient Bienvenue.

2173a39 ajoute un texte de test en bas de la page.

Je voulais garder seulement la correction de la faute. Alors je suis revenu sur main et j'ai tapé git cherry-pick 221f859

Git a copié ce commit sur main avec un nouveau numéro 234fa82. Les couleurs et le texte de test ne sont pas sur main.

Une fusion normale n'était pas bonne ici. Elle aurait pris les trois commits de la branche test. Les couleurs de test et le texte de test seraient arrivés sur le vrai site.


Mission 12

Le site marche bien. Avec git log --oneline j'ai vu que le dernier commit était a6244a2.

J'ai créé la version avec git tag -a v1.0.0 -m "Première version stable de NovaTech"

J'ai vérifié avec git tag puis j'ai vu les infos de la version avec git show v1.0.0

On voit le nom de la version qui l'a créée la date le message et le commit a6244a2.

Le premier chiffre 1 est la version majeure. On le change quand on refait beaucoup de choses et que l'ancien ne marche plus pareil.

Le deuxième chiffre 0 est la version mineure. On le change quand on ajoute une chose nouvelle sans rien casser.

Le troisième chiffre 0 est le correctif. On le change quand on répare un petit bug.

Pour une petite correction de bug la version suivante est v1.0.1

Pour une nouvelle fonction qui ne casse rien la version suivante est v1.1.0

Pour une grosse refonte qui change tout la version suivante est v2.0.0
