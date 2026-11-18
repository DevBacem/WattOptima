<!--
  README.md - WattOptima TN
  Utilite : presentation du depot et des versions figees du projet.
  Lie a   : .gitignore, docs\, backend\ (D2), frontend\ (D8).
-->
# WattOptima TN

Plateforme SaaS d'intelligence energetique et d'optimisation predictive de la
consommation electrique industrielle par apprentissage automatique (PFE ingenieur).

## Environnement fige (Windows 10, PowerShell)

| Outil | Version |
|---|---|
| Python | 3.12.10 |
| Node.js | 22.23.5 |
| npm | 10.9.9 |
| Angular CLI | 18.2.21 |
| PostgreSQL | 16.15 (localhost:5432) |
| Git | 2.55.0 |

Les bibliotheques Python figees sont dans `backend\requirements.txt` (cree en D0/D2).

## Structure

- `backend\`  : API Django REST + moteur IA (cree en D2)
- `frontend\` : application Angular 18 (cree en D8)
- `data\`     : jeux de donnees (non versionnes)
- `docs\`     : UML, rapport, pack startup