# Préparation de la réunion du lundi - page autonome (GitHub Pages + fichier SharePoint)

Cette page prépare la réunion du lundi avec les CSM des groupes : tickets en cours (avec le technicien en charge),
MAJ à venir, points à demander aux CSM et notes. Elle est hébergée sur GitHub Pages et les données partagées sont
dans **un seul fichier JSON** placé dans un dossier SharePoint synchronisé avec OneDrive. Elle fonctionne comme le
suivi des MAJ (`suivi-maj`) et n'a pas besoin de Claude.

Contenu du projet :
- `index.html` : la page (à la racine du dépôt). **C'est la seule chose à mettre sur GitHub**, avec ce LISEZ-MOI, le README et le `.gitignore`.
- `donnees/preparation-reunion-donnees.json` : le fichier de données de départ (vide). **Ne jamais le mettre sur GitHub** :
  il va dans SharePoint (le `.gitignore` l'exclut).

## 1. Publier la page sur GitHub Pages (une seule fois)

1. Dépôt : `Dams-epack/Preparation_reunion`. GitHub Pages gratuit exige un dépôt **public** : la page ne contient
   aucune donnée client, mais n'importe qui avec le lien peut l'ouvrir (elle apparaît vide sans le fichier de données).
2. « Settings » > « Pages » > Source : « Deploy from a branch », branche `main`, dossier `/ (root)` > « Save ».
3. Après 1 à 2 minutes, l'adresse est : `https://dams-epack.github.io/Preparation_reunion/`. C'est le lien à donner aux collègues.

Pour mettre à jour la page plus tard : remplacer `index.html` dans le dépôt.

## 2. Mettre le fichier de données dans SharePoint

1. Déposer `preparation-reunion-donnees.json` dans un dossier SharePoint de l'équipe
   (`SGC > 04 RESSOURCES INTERNES > 00. Skills Claude AI > Préparation réunion lundi`).
2. Chaque collègue synchronise ce dossier avec OneDrive (bouton « Synchroniser » dans SharePoint), puis clic droit
   sur le dossier > « Toujours conserver sur cet appareil » (le fichier doit être réellement présent sur le poste).

## 3. Se connecter au fichier (chaque collègue, une fois)

1. Ouvrir la page **avec Microsoft Edge ou Google Chrome** (Firefox et Safari ne conviennent pas).
2. « Ouvrir le fichier de données » > choisir `preparation-reunion-donnees.json` dans le dossier synchronisé.
3. Saisir son prénom (il apparaît dans « modifié par »).

Le navigateur retient le fichier. À une prochaine visite, cliquer sur « Reconnecter » si la page le demande.

## Utilisation

- « Créer la première préparation » crée la réunion du prochain lundi. Ensuite, « Nouvelle préparation » crée le lundi
  suivant en **reprenant ce qui n'est pas terminé** (tickets non résolus, MAJ non faites, points non traités) : un collègue
  peut préparer le point à la place de Damien en repartant des données déjà saisies.
- Le filtre « Technicien » (Damien, Matthieu, Tristan, extensible) montre les lignes d'une personne.
- « Copier la trame » produit un texte prêt à coller dans Confluence ou un mail.

## À savoir

- **Synchronisation** : la page relit le fichier toutes les 4 secondes, mais OneDrive met quelques secondes à quelques
  minutes à propager le fichier entre les postes : ce n'est pas du temps réel.
- **Écritures simultanées** : chaque enregistrement relit le fichier et fusionne ligne par ligne (la dernière modification
  d'une ligne gagne). Si OneDrive crée une copie « conflit » du fichier, garder la plus récente et supprimer l'autre.
- **Sauvegarde** : SharePoint garde l'historique des versions du fichier (« Historique des versions »).
- **Données** : le fichier JSON contient les tickets et les noms de clients. Il reste dans SharePoint, jamais sur GitHub.
