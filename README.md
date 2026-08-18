# Collection numismatique — site

## Structure
```
index.html              -> la page du site
data/index.json         -> liste légère de tous les pays (pour la page d'accueil, l'index A-Z, la carte)
data/countries/*.json   -> le détail complet d'un pays (chargé seulement quand tu cliques dessus)
images/<pays>/*.jpg     -> les photos des pièces, un dossier par pays
```

## Important : ça ne marche PAS en double-cliquant sur le fichier
Le site charge maintenant les données à la demande (plus léger, plus rapide), ce qui veut dire
qu'il doit être servi par un serveur web — les navigateurs bloquent ce type de chargement
quand on ouvre un fichier directement (`file://`).

## Tester en local (optionnel)
Si tu as Python installé sur ton ordinateur, ouvre un terminal dans ce dossier et lance :
```
python3 -m http.server 8000
```
Puis ouvre http://localhost:8000 dans ton navigateur.

## Mettre en ligne avec GitHub Pages (gratuit)
1. Crée un compte GitHub si tu n'en as pas (github.com)
2. Crée un nouveau dépôt (repository), par exemple `ma-collection`
3. Mets tous les fichiers de ce dossier dedans (glisser-déposer sur github.com fonctionne,
   ou `git add . && git commit -m "site" && git push` si tu utilises git)
4. Dans les paramètres du dépôt (Settings) → Pages → Source : choisis la branche `main` et le dossier `/ (root)`
5. Après une minute ou deux, ton site sera visible à `https://tonpseudo.github.io/ma-collection/`

## Ajouter un pays / une série plus tard
- Ajoute une entrée dans `data/index.json` (copie le format d'une entrée existante)
- Crée le fichier `data/countries/<slug-du-pays>.json` correspondant
- Mets les photos dans `images/<slug-du-pays>/`

Si tu veux, je peux t'aider à écrire un petit script pour ajouter un pays proprement
plutôt que de modifier les fichiers à la main.
