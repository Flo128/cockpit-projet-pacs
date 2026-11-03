# Cockpit projet PACS

Cockpit de pilotage PRINCE2 d'un déploiement de PACS, vu du côté de l'éditeur (projet fictif : CH de Saint-Aubert).

- Vues : synthèse et météo du projet, planning (Gantt), risques, points et décisions, marge et facturation, gouvernance.
- Présentations plein écran : COPIL et COPROJ (sans données internes, à montrer au client) et revue interne (marge, charge, facturation, risques de l'affaire).
- Bascule « Vue interne / Vue client » pour l'affichage.
- Édition client dans `client/` : mêmes vues, mais les données internes (marge, coûts, charge, risques et points internes) sont retirées du fichier de données. C'est la seule version à transmettre à un client.
- Les données viennent du classeur Excel « Pilotage PRINCE2 PACS, version éditeur » (`data/projet.json`). Le bouton « Mettre à jour depuis Excel » charge un classeur à jour dans le navigateur.

## Boîte à outils PACS (`outils/`)

13 outils pour un déploiement PACS : dimensionnement du stockage, estimateur de migration, prérequis client, inventaire des modalités, plan d'adressage DICOM, matrice des flux, cahier de recette, chronogramme de bascule (mode jour J), suivi de migration, plan de formation, guides de démarrage, générateur de compte rendu, simulateur d'avenant. Chaque outil exporte un document Excel ou PDF (client ou interne). Les saisies sont enregistrées dans le navigateur.

Auteur : Florian CROSES
