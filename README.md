# Jumeau numérique: le jumeau et l'usine

Un paquet pour Claude, pour les personnes qui ne codent pas.

- Le jumeau vous interroge, une question à la fois, sur votre façon de faire. Il l'écrit avec vous dans une fiche, que vous validez.
- L'usine en fait un outil. Elle vous propose des choix, avec leur coût, le temps qu'ils vous demandent, ce qui part chez l'éditeur et comment en sortir. Elle construit avec vous, puis essaie l'outil sur vos vraies situations.
- Un tableau de bord, une seule page privée, montre vos besoins, vos outils, ce qu'ils ont produit, ce qu'ils attendent de vous, leur niveau de permission, que vous choisissez, et comment en sortir.

## Installer

Il faut une offre Claude payante (Pro, Max, Team ou Enterprise).

1. Sur claude.ai ou dans l'application de bureau de Claude, ouvrez Personnaliser (« Customize »), puis Plugins.
2. Choisissez « Add marketplace » et collez: `Gallisatyricon/jumeau-usine`
3. Choisissez « jumeau-usine », puis « Install ».
4. Activez « Sync automatically »: les nouvelles versions arriveront seules.

Le paquet sert ensuite dans Cowork, dans l'onglet Code et dans le chat.

Dans Claude Code en ligne de commande, une seule ligne suffit:

```
/plugin install jumeau-usine --marketplace Gallisatyricon/jumeau-usine
```

## Commencer

Dans Cowork ou dans l'onglet Code, ouvrez un dossier et écrivez ce que vous voulez, par exemple: « Je voudrais un outil pour relancer mes devis en retard. »

Conseil: choisissez le mode « Auto ». Dans un autre mode, chaque mise à jour du tableau peut vous demander un clic, ou être refusée.

## Ce qu'il ne fait pas

- Jamais, à aucun niveau: demander ou recopier un mot de passe, payer, supprimer des fichiers, créer un compte, collecter des données sur d'autres personnes.
- Les limites techniques, avec leurs sources: [limites.md](plugins/jumeau-usine/skills/usine/references/limites.md).

## Vos données

Ce que Claude lit et écrit pour vous passe chez Anthropic, et chez l'éditeur de chaque connecteur que vous autorisez (Google, par exemple). Le tableau de bord est une page privée de votre compte Claude.

## Droits

Tous droits réservés.
