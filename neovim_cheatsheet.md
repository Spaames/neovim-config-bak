# Cheatsheet Neovim - Guide Complet

## Table des matières
- [Modes de base](#modes-de-base)
- [Navigation](#navigation)
- [Édition de texte](#édition-de-texte)
- [Sélection (Mode Visuel)](#sélection-mode-visuel)
- [Copier/Coller](#copiercoller)
- [Recherche et Remplacement](#recherche-et-remplacement)
- [Fichiers et Buffers](#fichiers-et-buffers)
- [Fenêtres (Splits)](#fenêtres-splits)
- [Commandes spécifiques à la config](#commandes-spécifiques-à-la-config)

---

## Modes de base

| Commande | Description |
|----------|-------------|
| `Esc` | Retour au mode Normal |
| `i` | Mode Insertion (avant le curseur) |
| `a` | Mode Insertion (après le curseur) |
| `I` | Mode Insertion (début de ligne) |
| `A` | Mode Insertion (fin de ligne) |
| `o` | Nouvelle ligne en dessous + Insertion |
| `O` | Nouvelle ligne au-dessus + Insertion |
| `v` | Mode Visuel (sélection caractère) |
| `V` | Mode Visuel Ligne (sélection ligne) |
| `Ctrl+v` | Mode Visuel Bloc (sélection rectangulaire) |

---

## Navigation

### Déplacement de base
| Commande | Description |
|----------|-------------|
| `h` `j` `k` `l` | ← ↓ ↑ → (ou flèches directionnelles) |
| `w` | Mot suivant |
| `b` | Mot précédent |
| `e` | Fin du mot |
| `0` | Début de ligne |
| `^` | Premier caractère non-vide de la ligne |
| `$` | Fin de ligne |
| `gg` | Début du fichier |
| `G` | Fin du fichier |
| `:42` ou `42G` | Aller à la ligne 42 |

### Navigation avancée
| Commande | Description |
|----------|-------------|
| `{` | Paragraphe précédent |
| `}` | Paragraphe suivant |
| `%` | Aller à la parenthèse/accolade correspondante |
| `Ctrl+d` | Descendre d'une demi-page |
| `Ctrl+u` | Monter d'une demi-page |
| `Ctrl+f` | Descendre d'une page |
| `Ctrl+b` | Monter d'une page |
| `Ctrl+o` | Revenir à la position précédente |
| `Ctrl+i` | Aller à la position suivante |
| `''` | Revenir à la dernière position |

---

## Édition de texte

### Supprimer
| Commande | Description |
|----------|-------------|
| `x` | Supprimer caractère sous le curseur |
| `X` | Supprimer caractère avant le curseur |
| `dd` | Supprimer ligne entière |
| `dw` | Supprimer mot |
| `d$` ou `D` | Supprimer jusqu'à fin de ligne |
| `d0` | Supprimer jusqu'au début de ligne |
| `dG` | Supprimer jusqu'à la fin du fichier |
| `dgg` | Supprimer jusqu'au début du fichier |
| `diw` | Supprimer le mot sous le curseur |
| `di"` | Supprimer texte entre guillemets |
| `di(` ou `dib` | Supprimer texte entre parenthèses |
| `di{` ou `diB` | Supprimer texte entre accolades |

### Changer (supprimer + mode Insertion)
| Commande | Description |
|----------|-------------|
| `cc` ou `S` | Changer ligne entière |
| `cw` | Changer mot |
| `c$` ou `C` | Changer jusqu'à fin de ligne |
| `ciw` | Changer le mot sous le curseur |
| `ci"` | Changer texte entre guillemets |
| `ci(` | Changer texte entre parenthèses |
| `ci{` | Changer texte entre accolades |

### Autres éditions
| Commande | Description |
|----------|-------------|
| `r` | Remplacer un caractère |
| `R` | Mode Remplacement |
| `~` | Changer la casse (majuscule/minuscule) |
| `J` | Joindre la ligne suivante |
| `u` | Annuler (Undo) |
| `Ctrl+r` | Refaire (Redo) |
| `.` | Répéter la dernière commande |
| `>>` | Indenter ligne |
| `<<` | Dé-indenter ligne |
| `==` | Auto-indenter ligne |
| `gg=G` | Auto-indenter tout le fichier |

---

## Sélection (Mode Visuel)

### Entrer en mode visuel
| Commande | Description |
|----------|-------------|
| `v` | Mode Visuel caractère |
| `V` | Mode Visuel ligne |
| `Ctrl+v` | Mode Visuel bloc |
| `gv` | Re-sélectionner la dernière sélection |

### Sélections rapides
| Commande | Description |
|----------|-------------|
| `viw` | Sélectionner mot sous le curseur |
| `vip` | Sélectionner paragraphe |
| `vi"` | Sélectionner texte entre guillemets |
| `vi(` ou `vib` | Sélectionner texte entre parenthèses |
| `vi{` ou `viB` | Sélectionner texte entre accolades |
| `vit` | Sélectionner texte entre balises HTML/XML |
| `ggVG` | Sélectionner tout le fichier |

### Actions en mode visuel
| Commande | Description |
|----------|-------------|
| `y` | Copier (yank) |
| `d` | Couper (delete) |
| `c` | Changer (supprimer + insertion) |
| `>` | Indenter |
| `<` | Dé-indenter |
| `=` | Auto-indenter |
| `~` | Inverser la casse |
| `u` | Mettre en minuscules |
| `U` | Mettre en majuscules |

---

## Copier/Coller

| Commande | Description |
|----------|-------------|
| `yy` ou `Y` | Copier ligne entière |
| `yw` | Copier mot |
| `y$` | Copier jusqu'à fin de ligne |
| `yiw` | Copier mot sous le curseur |
| `yip` | Copier paragraphe |
| `p` | Coller après le curseur/ligne |
| `P` | Coller avant le curseur/ligne |
| `"+y` | Copier vers le presse-papier système |
| `"+p` | Coller depuis le presse-papier système |
| `"ayy` | Copier ligne dans le registre 'a' |
| `"ap` | Coller depuis le registre 'a' |

---

## Recherche et Remplacement

### Recherche
| Commande | Description |
|----------|-------------|
| `/motif` | Rechercher "motif" vers le bas |
| `?motif` | Rechercher vers le haut |
| `n` | Résultat suivant |
| `N` | Résultat précédent |
| `*` | Rechercher mot sous le curseur (suivant) |
| `#` | Rechercher mot sous le curseur (précédent) |
| `:noh` | Désactiver le surlignage de recherche |

### Remplacement
| Commande | Description |
|----------|-------------|
| `:s/ancien/nouveau/` | Remplacer première occurrence (ligne courante) |
| `:s/ancien/nouveau/g` | Remplacer toutes occurrences (ligne courante) |
| `:%s/ancien/nouveau/g` | Remplacer dans tout le fichier |
| `:%s/ancien/nouveau/gc` | Remplacer avec confirmation |
| `:5,10s/ancien/nouveau/g` | Remplacer lignes 5 à 10 |

---

## Fichiers et Buffers

### Fichiers
| Commande | Description |
|----------|-------------|
| `:w` | Sauvegarder |
| `:w nomfichier` | Sauvegarder sous un nouveau nom |
| `:q` | Quitter |
| `:wq` ou `ZZ` | Sauvegarder et quitter |
| `:q!` | Quitter sans sauvegarder |
| `:wqa` | Sauvegarder et quitter tous les buffers |
| `:e fichier` | Ouvrir un fichier |
| `:e!` | Recharger le fichier (annuler modifications) |
| `:saveas fichier` | Sauvegarder sous |

### Buffers
| Commande | Description |
|----------|-------------|
| `:ls` ou `:buffers` | Lister les buffers |
| `:bn` | Buffer suivant |
| `:bp` | Buffer précédent |
| `:b3` | Aller au buffer 3 |
| `:b nomfichier` | Aller au buffer par nom |
| `:bd` | Fermer le buffer courant |
| `:bd!` | Fermer le buffer sans sauvegarder |

---

## Fenêtres (Splits)

### Créer des splits
| Commande | Description |
|----------|-------------|
| `:sp` ou `:split` | Split horizontal |
| `:vsp` ou `:vsplit` | Split vertical |
| `:sp fichier` | Ouvrir fichier en split horizontal |
| `:vsp fichier` | Ouvrir fichier en split vertical |

### Navigation entre splits (natif)
| Commande | Description |
|----------|-------------|
| `Ctrl+w h` | Aller à la fenêtre de gauche |
| `Ctrl+w l` | Aller à la fenêtre de droite |
| `Ctrl+w j` | Aller à la fenêtre du bas |
| `Ctrl+w k` | Aller à la fenêtre du haut |
| `Ctrl+w w` | Cycler entre les fenêtres |

### Gestion des splits
| Commande | Description |
|----------|-------------|
| `Ctrl+w q` ou `:q` | Fermer la fenêtre courante |
| `Ctrl+w o` | Fermer toutes sauf la courante |
| `Ctrl+w =` | Égaliser la taille des fenêtres |
| `Ctrl+w _` | Maximiser hauteur |
| `Ctrl+w |` | Maximiser largeur |
| `Ctrl+w +` | Augmenter hauteur |
| `Ctrl+w -` | Diminuer hauteur |
| `Ctrl+w >` | Augmenter largeur |
| `Ctrl+w <` | Diminuer largeur |

---

## Commandes spécifiques à la config

### Navigation (config custom)
| Commande | Description |
|----------|-------------|
| `Ctrl+h` | Aller à la fenêtre de gauche (simplifié) |
| `Ctrl+l` | Aller à la fenêtre de droite (simplifié) |
| `Ctrl+j` | Aller à la fenêtre du bas (simplifié) |
| `Ctrl+k` | Aller à la fenêtre du haut (simplifié) |

### Explorateur de fichiers (NvimTree)
| Commande | Description |
|----------|-------------|
| `Space+e` | Toggle explorateur de fichiers |
| `Enter` | Ouvrir fichier/dossier (dans NvimTree) |
| `a` | Créer nouveau fichier (dans NvimTree) |
| `d` | Supprimer fichier (dans NvimTree) |
| `r` | Renommer fichier (dans NvimTree) |
| `x` | Couper fichier (dans NvimTree) |
| `c` | Copier fichier (dans NvimTree) |
| `p` | Coller fichier (dans NvimTree) |
| `R` | Rafraîchir arbre (dans NvimTree) |

### Telescope (Fuzzy Finder)
| Commande | Description |
|----------|-------------|
| `Space+ff` | Rechercher fichiers |
| `Space+fg` | Rechercher dans le contenu (grep) |
| `Space+fb` | Lister les buffers |
| `Ctrl+n/p` | Naviguer dans les résultats (dans Telescope) |
| `Ctrl+c` ou `Esc` | Fermer Telescope |
| `Enter` | Ouvrir la sélection |

### LSP (Language Server)
| Commande | Description |
|----------|-------------|
| `gd` | Aller à la définition |
| `gr` | Voir les références |
| `K` | Afficher la documentation (hover) |
| `Space+rn` | Renommer symbole |
| `Space+ca` | Actions de code |
| `Space+f` | Formater le code |
| `[d` | Diagnostic précédent |
| `]d` | Diagnostic suivant |

### Diagnostics (Trouble)
| Commande | Description |
|----------|-------------|
| `Space+xx` | Toggle liste des erreurs/warnings |

### Gestion des fenêtres/buffers (config custom)
| Commande | Description |
|----------|-------------|
| `Space+q` | Fermer fenêtre courante |
| `Space+bd` | Fermer buffer courant |

### Auto-complétion (nvim-cmp)
| Commande | Description |
|----------|-------------|
| `Ctrl+Space` | Déclencher auto-complétion |
| `Tab` | Sélectionner suggestion suivante |
| `Shift+Tab` | Sélectionner suggestion précédente |
| `Enter` | Accepter la suggestion |
| `Ctrl+e` | Fermer le menu de complétion |
| `Ctrl+b` | Scroll docs vers le haut |
| `Ctrl+f` | Scroll docs vers le bas |

### Git (Gitsigns)
| Commande | Description |
|----------|-------------|
| `]c` | Aller au changement suivant |
| `[c` | Aller au changement précédent |
| `:Gitsigns stage_hunk` | Stager le hunk courant |
| `:Gitsigns undo_stage_hunk` | Annuler le stage |
| `:Gitsigns preview_hunk` | Prévisualiser le changement |

### Go spécifique (go.nvim)
| Commande | Description |
|----------|-------------|
| `:GoRun` | Exécuter le fichier Go |
| `:GoTest` | Lancer les tests |
| `:GoCoverage` | Afficher la couverture de code |
| `:GoFmt` | Formater le code (fait automatiquement à la sauvegarde) |

---

## Astuces et combinaisons puissantes

| Commande | Description |
|----------|-------------|
| `d5j` | Supprimer 5 lignes vers le bas |
| `y3w` | Copier 3 mots |
| `5dd` | Supprimer 5 lignes |
| `ci"` | Changer le contenu entre guillemets |
| `di{` | Supprimer contenu entre accolades |
| `va{` | Sélectionner tout y compris les accolades |
| `=ap` | Auto-indenter le paragraphe |
| `gwip` | Re-formater le paragraphe (wrap) |

---

## Commandes Vim utiles diverses

| Commande | Description |
|----------|-------------|
| `:help commande` | Aide sur une commande |
| `:set number` | Activer numéros de ligne |
| `:set relativenumber` | Numéros de ligne relatifs |
| `:set paste` | Mode paste (évite auto-indent) |
| `:set nopaste` | Désactiver mode paste |
| `:%!command` | Filtrer tout le fichier via une commande shell |
| `:r !command` | Insérer sortie d'une commande shell |
| `:term` | Ouvrir un terminal dans Neovim |

---

## Raccourcis clavier système

| Commande | Description |
|----------|-------------|
| `Ctrl+z` | Suspendre Neovim (retour terminal) |
| `fg` | Reprendre Neovim (depuis terminal) |

---

## Conseils pour débutants

1. **Commence simple** : `i` pour écrire, `Esc` pour sortir, `:wq` pour sauvegarder
2. **Pratique la navigation** : `hjkl` au lieu des flèches
3. **Utilise `.`** : Répète la dernière commande (super puissant !)
4. **Pense en "verbes + objets"** : `d` (delete) + `w` (word) = supprimer mot
5. **Ne reste pas en mode Insertion** : Utilise le mode Normal pour tout sauf écrire
6. **`:help` est ton ami** : `:help dd` pour apprendre une commande

---

## Pour aller plus loin

- `:Tutor` - Tutorial interactif Vim intégré
- `:help quickref` - Référence rapide complète
- `:help user-manual` - Manuel utilisateur complet
- [vimawesome.com](https://vimawesome.com) - Découvrir plus de plugins