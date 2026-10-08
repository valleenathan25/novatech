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
