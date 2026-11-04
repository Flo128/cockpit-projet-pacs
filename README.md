# Pilotage PACS

Une seule page pour piloter un déploiement de PACS côté éditeur (projet fictif : CH de Saint-Aubert) : le **cockpit** PRINCE2 et la **boîte à outils** (`#outils`), qui partagent le même classeur Excel du projet. Un classeur ouvert dans l'un est ouvert dans l'autre, et il est gardé dans le navigateur au rechargement.

- Vues : synthèse et météo du projet, planning (Gantt), risques, points et décisions, marge et facturation, gouvernance.
- Présentations plein écran : COPIL et COPROJ (sans données internes, à montrer au client) et revue interne (marge, charge, facturation, risques de l'affaire).
- Bascule « Vue interne / Vue client » pour l'affichage.
- Édition client dans `client/` : mêmes vues, mais les données internes (marge, coûts, charge, risques et points internes) sont retirées du fichier de données. C'est la seule version à transmettre à un client.
- Les données viennent du classeur Excel « Pilotage PRINCE2 PACS, version éditeur » (`data/projet.json`). Le bouton « Ouvrir le classeur du projet » charge un classeur dans le navigateur, pour le cockpit et la boîte à outils à la fois.

## Boîte à outils PACS (`#outils`)

Une vue « Cette semaine » (planning et actions du classeur, prérequis, formation, bascule, compte rendu, retards) et 13 outils pour un déploiement PACS : stockage (cache) et archivage, estimateur de migration, prérequis client, inventaire des modalités, plan d'adressage DICOM, matrice des flux, cahier de recette, chronogramme de bascule (mode jour J), suivi de migration, plan de formation, guides de démarrage, plan d'assurance qualité (export Word, PDF, Excel), générateur de compte rendu, simulateur d'avenant. Chaque outil exporte un document Excel ou PDF (client ou interne). Les saisies sont enregistrées dans le navigateur, puis dans les onglets OT du classeur avec « Enregistrer dans le classeur ». L'ancienne adresse `outils/` redirige vers `#outils`.

## Un classeur Excel par projet (`classeurs/`)

Chaque projet a son classeur de pilotage PRINCE2 (version éditeur). Ses onglets violets « OT … » sont la base de données de la boîte à outils :

- **Boîte à outils → classeur** : bouton « Classeur du projet », puis « Ouvrir le classeur du projet » ; après modification, « Enregistrer dans le classeur » télécharge le classeur mis à jour. Seuls les onglets OT sont réécrits : planning, budget, tableau de bord et documents restent intacts. « Créer un classeur à partir de ces données » part du modèle vide.
- **Pilotage → boîte à outils** : nom du projet, client, chef de projet (Accueil), chiffre d'affaires et coût prévu (Budget), dates de migration et de bascule (Planning) sont liés par formule dans « OT Paramètres » et repris en lecture seule par la boîte à outils.
- **Boîte à outils → pilotage** : le Tableau de bord du classeur a un bloc « Boîte à outils PACS » (prérequis, modalités, flux, recette, migration, formation, Go / No-Go, avenant en préparation), et le cockpit affiche la préparation technique dans la synthèse et dans le COPROJ.

Fichiers : `Pilotage-PRINCE2-PACS-Editeur-Modele.xlsx` (vide), `…-Exemple.xlsx` (CH de Saint-Aubert), deux scénarios (`Scenario-Projet-Simple-Ensoleille.xlsx`, `Scenario-Projet-Complexe-Orageux.xlsx`).

Auteur : Florian CROSES
