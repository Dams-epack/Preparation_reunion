# Point SGC du vendredi - version partagée (GitHub Pages + fichier SharePoint)

La page est hébergée sur GitHub Pages. Les données sont dans **un seul fichier JSON** placé dans un dossier SharePoint
synchronisé avec OneDrive : tous les collègues ouvrent la même page et le même fichier, et retrouvent donc les données déjà saisies.

Deux dossiers :
- `site-github/` : contient `index.html`, la page. **C'est la seule chose à mettre sur GitHub.**
- `donnees/` : contient `point-sgc-donnees.json`, les données actuelles (11 tickets, 41 MAJ, 1 question CSM,
  1 point d'attention, 2 informations). **Ne jamais le mettre sur GitHub** : il va dans SharePoint.

## 1. Publier la page sur GitHub Pages (une seule fois)

1. Sur github.com, crée un dépôt, par exemple `point-sgc` (« New repository »).
   - GitHub Pages gratuit exige un dépôt **public** : n'importe qui avec le lien peut ouvrir la page, mais elle apparaît vide
     sans le fichier de données (elle ne contient aucun nom de client).
2. « Add file » > « Upload files » : dépose `index.html` (dossier `site-github`) > « Commit changes ».
3. « Settings » > « Pages » > Source : « Deploy from a branch », branche `main`, dossier `/ (root)` > « Save ».
4. Après 1 à 2 minutes, l'adresse est `https://TON-COMPTE.github.io/point-sgc/`. C'est le lien à donner aux collègues.

Pour mettre la page à jour plus tard : remplace `index.html` dans le dépôt (même nom).

## 2. Mettre le fichier de données dans SharePoint

1. Dépose `point-sgc-donnees.json` dans le dossier SharePoint de l'équipe
   (par exemple `SGC > 04 RESSOURCES INTERNES > 00. Skills Claude AI > Point SGC`).
2. Chaque collègue synchronise ce dossier avec OneDrive (« Synchroniser »), puis clic droit sur le dossier >
   « Toujours conserver sur cet appareil ».

## 3. Se connecter au fichier (chaque collègue, une fois)

1. Ouvrir la page avec **Microsoft Edge ou Google Chrome** (Firefox et Safari ne conviennent pas).
2. Cliquer sur « Ouvrir le fichier de données » et choisir `point-sgc-donnees.json` dans le dossier synchronisé.
3. Le navigateur retient le fichier. À une prochaine visite, il peut demander de confirmer l'autorisation : cliquer sur « Reconnecter ».

## Ce qui change par rapport à la version Claude

- **Import du calendrier Outlook (.ics)** : le tri des événements se fait maintenant sans IA (reconnaissance de MAJ, migration,
  fermeture, ouverture, 2e passe, et du n° de requête). Vérifiez les lignes proposées : le client est déduit du titre.
- **Import du rapport Salesforce (.xlsx)** : inchangé (« En attente déploiement » = validée par le siège).
- **Tout le reste est identique** : tableaux, jours repliables, « Copier pour Confluence », colonne Requête Salesforce.
- **Colonne « Requête Salesforce »** : le lien cliquable sera ajouté quand l'URL d'une requête sera connue (valeur `SF_URL` dans la page).

## À savoir

- La page relit le fichier toutes les 4 secondes ; OneDrive met quelques secondes à quelques minutes à le propager entre les postes.
- Chaque champ est fusionné séparément : si deux personnes modifient des cellules différentes, tout est conservé ; sur la même cellule,
  la dernière modification gagne. En cas de copie « conflit » créée par OneDrive, garde la plus récente.
- SharePoint garde l'historique des versions du fichier (« Historique des versions ») pour revenir en arrière.
- Les mises en page repliées (semaines, jours) sont propres à chaque navigateur et ne sont pas partagées.
