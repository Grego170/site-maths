# Site de mathématiques MP2I : mode d'emploi

Tout se fait **depuis le navigateur, sans rien installer** : vous déposez un PDF dans le bon dossier, et il apparaît sur le site environ une minute plus tard.

- [1. Chaque semaine : publier le programme de colle](#1-chaque-semaine--publier-le-programme-de-colle)
- [2. Ajouter un cours, un TD, un devoir](#2-ajouter-un-cours-un-td-un-devoir)
- [3. Bien nommer les fichiers](#3-bien-nommer-les-fichiers)
- [4. Remplacer ou supprimer un fichier](#4-remplacer-ou-supprimer-un-fichier)
- [5. Écrire une annonce, modifier un texte](#5-écrire-une-annonce-modifier-un-texte)
- [6. Personnaliser le site](#6-personnaliser-le-site)
- [7. Mise en ligne (une seule fois)](#7-mise-en-ligne-une-seule-fois)
- [8. Bon à savoir](#8-bon-à-savoir)

---

## 1. Chaque semaine : publier le programme de colle

1. Ouvrez votre dépôt sur **github.com** et cliquez sur le dossier **`colles`**.
2. Cliquez sur **Add file → Upload files**.
3. Glissez votre PDF, par exemple `Semaine 04 - Intégration.pdf`.
4. Cliquez sur le bouton vert **Commit changes**.

Environ une minute plus tard :
- le programme apparaît **en tête de la page Colles**, avec l'étiquette « Cette semaine » ;
- il s'affiche aussi **dans l'encadré de la page d'accueil**.

> Le « dernier » programme est le dernier fichier **par ordre alphabétique**. Numérotez donc toujours avec deux chiffres : `Semaine 04`, pas `Semaine 4` (voir §3).

## 2. Ajouter un cours, un TD, un devoir

La manipulation est la même, dans le dossier qui correspond :

| Dossier    | Page du site | Contenu                                         |
|------------|--------------|-------------------------------------------------|
| `colles/`  | Colles       | programmes de colle (le plus récent en premier) |
| `cours/`   | Cours        | polycopiés de cours                             |
| `td/`      | TD           | feuilles d'exercices et corrigés                |
| `devoirs/` | Devoirs      | DS et DM, énoncés et corrigés                   |
| `infos/`   | Infos        | colloscope, emploi du temps, programme officiel |

Tous les formats sont acceptés (PDF, `.tex`, `.py`, images…). Vous pouvez déposer plusieurs fichiers d'un coup.

## 3. Bien nommer les fichiers

**Le nom du fichier devient le titre affiché** sur le site (sans l'extension). Les `_` sont remplacés par des espaces. Les accents sont acceptés.

Exemples :

```
Semaine 01 - Logique et ensembles.pdf
Chapitre 03 - Nombres complexes.pdf
TD 03 - Nombres complexes.pdf
TD 03 - Nombres complexes - corrigé.pdf     → étiquette « Corrigé » ajoutée automatiquement
DS 01 - Énoncé.pdf
DS 01 - Corrigé.pdf
```

⚠️ Deux chiffres pour les numéros (`01`, `02`… `10`) : sinon « Semaine 10 » serait classée avant « Semaine 2 ».

## 4. Remplacer ou supprimer un fichier

- **Remplacer** (une coquille à corriger) : déposez un fichier portant **exactement le même nom** ; il remplace l'ancien.
- **Supprimer** : cliquez sur le fichier, puis sur le menu **`···`** en haut à droite → **Delete file** → **Commit changes**.
- **Renommer** : supprimez-le puis déposez-le à nouveau sous le bon nom.

Rien n'est jamais vraiment perdu : l'onglet **History** de chaque dossier garde toutes les versions.

## 5. Écrire une annonce, modifier un texte

Les annonces sont dans le fichier **`index.md`**.

1. Cliquez sur `index.md`, puis sur le crayon ✏️ (**Edit this file**).
2. Ajoutez une ligne en haut de la liste :
   ```
   - **Lun. 22/09** — Pas de TD jeudi : sortie scolaire.
   ```
3. Cliquez sur **Commit changes**.

Les textes des autres pages se modifient de la même façon (`colles.md`, `infos.md`…) : ce qui est écrit **sous le deuxième `---`** s'affiche au-dessus de la liste des documents. Ne touchez pas aux lignes entre les deux `---`, sauf `title:` et `resume:`.

Mise en forme utile :

| Vous écrivez                 | Résultat                    |
|------------------------------|-----------------------------|
| `**gras**`                   | **gras**                    |
| `*italique*`                 | *italique*                  |
| `[Infos](infos/)`            | un lien                     |
| `> Attention : …`            | un encadré                  |
| `$$\int_0^1 f(t)\,dt$$`      | une formule mathématique    |

Les formules s'écrivent en LaTeX entre `$$ … $$` (évitez simplement d'écrire `{{` : mettez un espace, `{ {`).

## 6. Personnaliser le site

- **Titre, nom, lycée, année** : fichier `_config.yml` (crayon ✏️).
- **Couleurs** : en haut du fichier `assets/style.css`.
- **Ajouter une rubrique** (par ex. « Python ») :
  1. ouvrez `td.md`, copiez son contenu, puis **Add file → Create new file** nommé `python.md` ;
  2. collez, puis changez `title`, `menu`, `rang: 6`, `dossier: python` et `resume` ;
  3. sur votre ordinateur, créez un dossier `python` contenant votre premier fichier, et glissez **le dossier** dans **Add file → Upload files** à la racine du dépôt.

  La rubrique apparaît automatiquement dans le menu et sur la page d'accueil.

## 7. Mise en ligne (une seule fois)

### a. Créer le dépôt

1. Créez un compte gratuit sur [github.com](https://github.com).
2. En haut à droite, **+ → New repository** : nom `site-maths` (par exemple), cochez **Public**, puis **Create repository**.
3. Cliquez sur le lien **uploading an existing file**, glissez **tout le contenu** de ce dossier (fichiers et sous-dossiers), puis **Commit changes**.

### b. Activer l'hébergement (GitHub Pages)

1. Dans le dépôt : **Settings → Pages**.
2. *Source* : **Deploy from a branch** ; *Branch* : **main** et **/(root)** → **Save**.
3. Après 1 à 2 minutes, le site est en ligne à l'adresse `https://VOTRE-PSEUDO.github.io/site-maths/`.

### c. Brancher votre nom de domaine

1. **Settings → Pages → Custom domain** : saisissez `votre-domaine.fr` → **Save**.
2. Chez votre registrar (OVH, Gandi, IONOS…), dans la **zone DNS** du domaine, supprimez les anciens enregistrements `A` de `@` puis ajoutez :

   | Type    | Sous-domaine | Cible                  |
   |---------|--------------|------------------------|
   | `A`     | *(vide)*     | `185.199.108.153`      |
   | `A`     | *(vide)*     | `185.199.109.153`      |
   | `A`     | *(vide)*     | `185.199.110.153`      |
   | `A`     | *(vide)*     | `185.199.111.153`      |
   | `CNAME` | `www`        | `VOTRE-PSEUDO.github.io.` |

3. Attendez la propagation (de quelques minutes à quelques heures), puis revenez dans **Settings → Pages** et cochez **Enforce HTTPS**.

## 8. Bon à savoir

- **Le site est public** (c'est le cas de tout dépôt GitHub gratuit). N'y mettez pas de données personnelles d'élèves (notes, noms complets) : pour le colloscope, préférez des numéros de groupe.
- **Délai** : chaque modification apparaît en ligne après 1 à 2 minutes. Pensez à rafraîchir la page.
- **Taille** : 25 Mo maximum par fichier déposé via le navigateur.
- **En cas de problème**, GitHub envoie un e-mail et l'onglet **Actions** du dépôt indique l'erreur.
- **Mode sombre** : le site passe automatiquement en thème « tableau noir » sur les appareils réglés en sombre.
- Pour déposer depuis un dossier de votre ordinateur plutôt que depuis le navigateur, l'application gratuite **GitHub Desktop** synchronise un dossier local avec le site.

### Organisation des fichiers

```
_config.yml          ← réglages : titre, nom, lycée, année
index.md             ← page d'accueil et annonces
colles.md  cours.md  td.md  devoirs.md  infos.md   ← textes des rubriques

colles/  cours/  td/  devoirs/  infos/             ← VOS DOCUMENTS (déposer ici)

_layouts/  _includes/  assets/                     ← mise en page (inutile d'y toucher)
```
