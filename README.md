# Octo Gitea

Thème Gitea épuré, palette neutre, disponible en variante claire et sombre.

## Variantes

| Thème | Style |
|-------|-------|
| **Octo Dark** | Fond noir profond (`#020202` / `#000000`), texte clair, accent bleu |
| **Octo Light** | Fond blanc, texte sombre, accent bleu |
| **Octo Auto** | Bascule automatique selon `prefers-color-scheme` du système |

## Installation

1. Copie les trois fichiers de [`themes/`](themes/) dans `data/gitea/public/assets/css/` :

   ```sh
   cp themes/theme-octo-*.css /chemin/vers/gitea/data/public/assets/css/
   ```

   Le dossier `assets/css` peut ne pas exister par défaut, crée-le si besoin.

2. Édite `data/gitea/conf/app.ini` et ajoute les variantes à la ligne `THEMES` de la section `[ui]` :

   ```ini
   [ui]
   THEMES = gitea-auto, gitea-light, gitea-dark, octo-auto, octo-light, octo-dark
   ```

   Les noms à ajouter sont **sans** le préfixe `theme-` ni le suffixe `.css`.

3. Redémarre Gitea.

4. Choisis le thème dans **Paramètres → Apparence**.

> [!IMPORTANT]
> Le thème `octo-auto` nécessite la présence de `theme-octo-light.css` **et** `theme-octo-dark.css` dans le même dossier — il les `@import` selon le `prefers-color-scheme` du navigateur.

Doc Gitea de référence : [Customizing Gitea](https://docs.gitea.com/administration/customizing-gitea#customizing-the-look-of-gitea).

## Personnalisation

Les couleurs sont définies via les variables CSS standard de Gitea (`--color-primary`, `--color-body`, `--color-syntax-*`, etc.). Pour ajuster un thème, édite directement le fichier CSS correspondant — aucun build n'est nécessaire.
