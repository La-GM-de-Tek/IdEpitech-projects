# IdEpitech Projects

Les projets guidés de [IdEpitech](https://github.com/La-GM-de-Tek/IdEpitech), l'IDE d'apprentissage qui tourne entièrement dans le navigateur : <https://idepitech.vercel.app>.

Chaque projet est un sujet complet (énoncé Markdown et PDF, code fourni, indices) et parfois un visualiseur qui anime le résultat du code de l'élève.

## Les projets

| Projet | Dossier | Langage | Ce que l'élève code | Visualiseur |
| --- | --- | --- | --- | --- |
| Fil d'Ariane | [filDariane/](filDariane/) | Python | Un algorithme qui sort Thésée du labyrinthe | Labyrinthe 2D / 3D |
| Appleton Calculator | [appletonCalculator/](appletonCalculator/) | HTML / CSS / JS | Une calculatrice inspirée de celle de l'iPhone | Aperçu HTML |
| Assaut d'Hyrule | [hyruleAttack/](hyruleAttack/) | Python | Un vérificateur de sudoku résolu | Console + correcteur |
| Défense d'Hyrule | [hyruleDefense/](hyruleDefense/) | Python | Un résolveur de sudoku | Sceau 2D / 3D |
| Feu Tricolore | [feuTricolore/](feuTricolore/) | Python | Les feux d'un carrefour, en 5 niveaux | Carrefour 3D |

[createSubject/](createSubject/) contient l'outil de création de sujet de l'IDE, et [scenePalette.js](scenePalette.js) les helpers de couleur partagés par les scènes 3D (ils lisent les couleurs du thème actif).

## Structure d'un projet

```text
monProjet/
├── monProjet.md     # énoncé (source du PDF)
├── monProjet.pdf    # énoncé affiché dans l'IDE
├── assets/          # images de l'énoncé
├── values.js        # explication, indices, sorties attendues
├── helpers.py       # code injecté avant celui de l'élève (importé avec ?raw)
├── grader.py        # code injecté après, pour corriger (optionnel)
└── monProjet.jsx    # visualiseur React (optionnel)
```

Les visualiseurs reçoivent `{ lines, status, onClear, project }` de l'IDE et appellent `saveCompletion(project.id, gold)` quand l'élève réussit.

## Utilisation dans IdEpitech

Ce repo est un sous-module de IdEpitech, monté dans `frontend/src/projects/`. Il n'est pas autonome : les composants importent des modules du frontend (`../../completion`, `../../components/Icon`, `../../usePyodide`…), et les projets sont déclarés dans `frontend/src/datas/guidedProjets.jsx` côté IdEpitech.

```bash
git clone --recurse-submodules https://github.com/La-GM-de-Tek/IdEpitech.git
cd IdEpitech/frontend
npm install
npm run dev      # http://localhost:5173
```

Sur un clone existant : `git submodule update --init`.

## Contribuer

Les nouveaux sujets et les corrections sont les bienvenus. Voir [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

[MIT](LICENSE.md) © La GM de Tek
