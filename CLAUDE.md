# CLAUDE.md — shiyamii-brand

Pack d'identité visuelle du pseudo **Shiyamii** (logos, fonds, favicons). Il est publié via GitHub (dépôt public `Shiyamii/shiyamii-brand`) et servi par **jsDelivr**. Ce n'est pas du code : il n'y a ni build ni tests, seulement des fichiers SVG/PNG/ICO.

## Source de référence : Outline

Tout le contexte (charte, décisions, règles) est dans la collection Outline **« Identité Shiyamii »**, accessible via le MCP `outline`. À lire avant toute modification :

1. « 00 — Vue d'ensemble »
2. « Règles »
3. « Décisions »
4. « Charte graphique » et ses sous-pages, en particulier « Fichiers et nommage »
5. « Publier les logos sur GitHub + jsDelivr (contexte de reprise pour Claude Code) » : la checklist en cours

**Ne refais aucun choix de design.** Tout est tranché dans « Décisions ».

## Arborescence

```text
logos/     logo-<forme>-sur-<clair|sombre>-<couleur|mono>.{svg,png}   12 logos, fond transparent
fonds/     fond-<fond>-<format>.{svg,png}                              16 gabarits
favicons/  favicon-<tuile>-<taille>.{svg,png}, favicon-<tuile>.ico     5 tuiles
```

- `<forme>` : `complet`, `monogramme`, `symbole`
- `<fond>` : `dark-point`, `light-point`, `plain-color`, `dark-aurore`
- `<format>` : `banniere-readme`, `banniere-social`, `avatar-symbole`, `avatar-monogramme`
- `<tuile>` : `transparent-sur-clair`, `transparent-sur-sombre`, `sombre`, `clair`, `plain-color`
- `<taille>` : `16`, `24`, `32`, `48`, `64` (SVG + PNG), plus `512` en PNG uniquement

## Règles

- **Les SVG font foi.** Aucun script de génération n'existe. Pour modifier un dessin, édite le SVG et régénère le PNG correspondant, ou demande à Tamas.
- **Le logo n'a jamais de fond.** Les fichiers de `fonds/` sont des gabarits, pas des logos.
- Ne mélange pas les versions : sur fond clair, utilise `sur-clair` ; sur fond sombre, utilise `sur-sombre`.
- **Ne renomme aucun fichier** sans mettre à jour la page Outline « Fichiers et nommage ». Les URLs jsDelivr publiées en dépendent.
- Les textes des SVG sont convertis en courbes. Les dégradés utilisent l'id `g` : renomme-le si plusieurs SVG sont intégrés en ligne dans une même page.
- Tout changement de forme, de couleur ou de fond met à jour la charte **et** « Décisions » dans Outline (on ajoute une entrée, on ne supprime rien).

## Publication (jsDelivr)

```text
https://cdn.jsdelivr.net/gh/Shiyamii/shiyamii-brand@<version>/<chemin>
```

- **Toujours un tag**, jamais `@main`.
- Tags semver **sans `v`** : `1.0.0`, pas `v1.0.0`.
- Tout changement visuel donne lieu à un nouveau tag (`1.1.0`…). On ne déplace ni ne supprime jamais un tag existant.
- Dans le `README.md`, utilise des **chemins relatifs** (`logos/…`) pour les aperçus. Les URLs jsDelivr servent seulement au tableau de liens à copier.

## État

- Publié en `1.0.0` le 2026-11-04. Le dépôt est public et jsDelivr sert les SVG, PNG et ICO avec le bon type (vérifié).
- Licence : **tous droits réservés** (voir `LICENSE`). Ne la change pas sans l'accord de Tamas.
- Les pages Outline de la charte affichent les images par lien jsDelivr `@1.0.0`.

## Points en attente

- Teste le favicon dans un navigateur et le `.ico` sous Windows.
- Confirme que l'instance Outline affiche bien les images externes.
- Confirme les tailles minimales du logo.
- Décide si `dark-aurore` est vraiment utilisé ou reste une variante.

## Conventions Outline

- Archive, ne supprime jamais. Crée des pages plutôt que de réécrire lourdement l'existant.
- Aucun secret (jeton, clé) dans le wiki.
- Distingue ce qui est **vérifié** de ce qui est **supposé**.
- Après chaque modification, dis en une ligne ce qui a été créé ou modifié, et où.
