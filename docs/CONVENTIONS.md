<!--
  Fichier : docs/CONVENTIONS.md
  Utilité : règles de nommage, de commentaires, de Git et de structure applicables à tout le projet.
  Liens   : README.md (versions figées), .gitignore, backend/.env.example.
-->
# Conventions WattOptima TN

## 1. Langues
- **Identifiants de code en anglais** : modèles, champs, fonctions, variables, endpoints (`Company`, `EnergyRecord`, `power_factor`).
- **Commentaires, docstrings, messages d'erreur et textes d'interface en français.**

## 2. En-tête obligatoire de chaque fichier
Python :
```python
"""
Fichier        : backend/apps/xxx/fichier.py
Utilité        : à quoi sert ce fichier.
Fonctionnement : comment il marche, en bref.
Liens          : imports, appelants, endpoints, modèles associés.
"""
```
TypeScript / Angular : même contenu dans un bloc `/** ... */` en tête de fichier.

## 3. Python / Django
- PEP 8, formatage automatique avec Black (88 colonnes).
- `snake_case` (fonctions, variables, champs), `PascalCase` (classes), `UPPER_SNAKE_CASE` (constantes).
- Chaque modèle appartenant à un client porte une clé étrangère `company` ; **toute requête est filtrée par `company` côté serveur**.
- Dates stockées en UTC avec fuseau (`USE_TZ = True`) ; l'affichage se règle sur le fuseau de la Tunisie (à confirmer en D2).
- Valeurs métier susceptibles de changer (tarifs, facteur d'émission CO₂, seuils) : **jamais en dur**, toujours en base ou en configuration.

## 4. API REST
- Préfixe `/api/`, ressources au pluriel, mots en anglais séparés par des tirets (`/api/energy-records/`).
- Pagination sur toutes les listes ; erreurs renvoyées avec un message clair en français.

## 5. Angular
- Composants autonomes (standalone), chargement paresseux des routes.
- Fichiers en `kebab-case` : `login.component.ts`, `auth.service.ts` ; classes en `PascalCase`.
- Formatage avec Prettier.

## 6. Git
- Branche unique `main` (projet individuel).
- Messages de commit : `type(Dn): message`, avec `type` ∈ `feat`, `fix`, `test`, `docs`, `chore`, `refactor`.
- Un commit à chaque étape validée.
- **Fin de chaque discussion Dn** : commit final, `git push`, puis tag annoté `Dn` poussé vers le dépôt GitHub **privé**.

## 7. Secrets
- Aucun secret dans Git : `backend/.env` est ignoré, seul `backend/.env.example` est versionné.