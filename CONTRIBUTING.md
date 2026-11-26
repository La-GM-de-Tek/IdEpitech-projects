# Contribuer

Merci de vouloir ajouter ou améliorer un projet ! Tout passe par une pull request sur `main`.

## Mettre en place

Les projets se testent dans IdEpitech, où ce repo est monté comme sous-module :

```bash
git clone --recurse-submodules https://github.com/La-GM-de-Tek/IdEpitech.git
cd IdEpitech/frontend
npm install
npm run dev
```

Travaillez ensuite dans `frontend/src/projects/`, qui est un clone de ce repo :

```bash
cd src/projects
git checkout -b feat/mon-projet
```

Pour proposer vos changements, forkez ce repo et ajoutez votre fork comme remote dans `frontend/src/projects/` (`git remote add fork <url de votre fork>`).

## Ajouter un projet

1. Créez `monProjet/` en suivant la structure de [filDariane/](filDariane/) ou [feuTricolore/](feuTricolore/) (voir le [README](README.md#structure-dun-projet)).
2. Écrivez l'énoncé dans `monProjet.md`, puis exportez-le en `monProjet.pdf`. Gardez les deux à jour : le `.md` est la source, le `.pdf` est ce que voit l'élève.
3. Mettez l'explication et les indices dans `values.js`. Le dernier indice peut renvoyer vers un humain (« Va demander à un Manta… »).
4. Si le projet a besoin d'un visualiseur, ajoutez `monProjet.jsx` et chargez la scène 3D avec un `import()` dynamique pour ne pas alourdir le bundle. Utilisez [scenePalette.js](scenePalette.js) pour que les couleurs suivent le thème.
5. Déclarez le projet dans IdEpitech (`frontend/src/datas/guidedProjets.jsx`). Ce changement est une PR séparée sur [La-GM-de-Tek/IdEpitech](https://github.com/La-GM-de-Tek/IdEpitech), qui met aussi à jour le commit du sous-module.

## Avant d'ouvrir la PR

- [ ] Une solution correcte passe le projet, une solution fausse échoue.
- [ ] Le niveau « gold » (s'il existe) n'est accordé que pour la bonne raison.
- [ ] `npm run lint` et `npm run build` passent dans `IdEpitech/frontend`.
- [ ] L'énoncé `.md` et le `.pdf` disent la même chose.
- [ ] Le visualiseur reste lisible en thème clair et en thème sombre.

## Commits

Les messages suivent [Conventional Commits](https://www.conventionalcommits.org/fr/) :

```text
feat: add feu-tricolore project
fix: wrong expected output in hyrule-attack
docs: clarify level 3 of fil-dariane
```

## Licence

En contribuant, vous acceptez que votre contribution soit publiée sous [licence MIT](LICENSE.md).
