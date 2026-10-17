# La fiche

Un seul format pour le jumeau et pour l'usine. Le jumeau l'écrit avec la personne, dans `fiche.md` du dossier de l'outil à venir. L'usine la lit pour fabriquer l'outil. Les textes entre `<` et `>` sont à remplacer. Tout est en français courant, phrases courtes, à la première personne quand c'est la personne qui parle.

## Le modèle

Les champs, dans cet ordre. Un champ sans réponse garde son titre, avec « rien pour l'instant » ou ce qui est à confirmer.

```
# <Titre court>

- État: <brouillon | validée le <AAAA-MM-JJ>, par <nom, ou « la personne »>, sur un oui de la personne<, donné d'avance>>
- Quand: <ce qui déclenche la procédure: un seul déclencheur>

## Le besoin
<deux phrases: ce que je fais aujourd'hui, et ce que je voudrais>

## Étapes
1. <étape>
2. <étape>

## Règles de décision
- <règle>. D'après: « <les mots de la personne> »

## Exceptions et cas difficiles
- <le cas, et ce qu'on fait>

## Situations réelles
1. <la situation, en quelques mots>. Source: <fichier du dossier, par exemple `exemples/situation-1.md` | document lu par un connecteur, avec son nom et l'accord donné>
2. <...>

## Exemples à fournir
- <ce qu'on m'a demandé et que je n'avais pas sous la main>

## Pièces jointes
- <nom du fichier>: <ce qu'elle montre, en une phrase> (une capture ou un document qui aide à comprendre, sans être une situation)

## Outils
- <ce que j'utilise aujourd'hui: messagerie, tableur, logiciel de mon métier>

## Sources et ce qu'elles ne voient pas
- <source>: <ce qui lui échappe>

## Niveau souhaité
<0 à 4>: <ce niveau en une phrase>. Les niveaux: 0 observer; 1 à blanc (l'outil montre ce qu'il aurait fait); 2 prépare (je fais l'action); 3 agit sur mon oui (un oui par action); 4 agit seul, dans des limites écrites et acceptées par moi.

## Qui voit le résultat
<personnes ou services>; convenu avec eux: <oui | non | à confirmer>

## Contraintes
- Coût: <« 0 € de plus », ou un plafond>
- Temps: <le temps que je veux y passer>
- Ce que je refuse: <...>

## Ce que je garde en main
<ce que je veux faire moi-même: relire, envoyer, publier, payer>

## À trancher
- <une question ouverte, par exemple « est-ce que ça peut se préparer tout seul chaque lundi ? »>

## À confirmer
- <ce que le jumeau n'a pas encore entendu clairement, ou une règle sans citation>
```

## Les règles de la fiche

- Chaque règle de décision cite les mots de la personne qui la fondent. Une règle sans citation reste dans « À confirmer ».
- Les situations sont réelles et numérotées 1, 2, 3, dans l'ordre. Chacune a sa source lisible: un fichier du dossier (un texte, ou un PDF dont on extrait le texte, pas un simple lien), ou un document atteint par un connecteur avec l'accord de la personne. Une situation inventée se marque « inventée ».
- Aucun nom ni adresse de tiers dans la fiche (« le client A »): la source les garde. Aucun mot de passe, code ou clé.
- La date de validation est donnée par la personne ou lue sur l'horloge de l'ordinateur, jamais estimée. Sans date sûre, écris « validée, par <nom>, sur un oui de la personne », sans date.
- « Validée » seulement sur un oui explicite de la personne. Un oui donné d'avance ne compte que s'il porte en toutes lettres sur la fiche; l'état le dit.
- Une fiche, un déclencheur. Plusieurs déclencheurs font plusieurs fiches liées, chacune dans son dossier.

## Ce que l'usine y relève

L'usine lit ce format et l'ancien (la fiche de besoin, avec « Mes vraies situations », « Mes contraintes », « Ce que je garde en main », « À trancher » et « Automatiser »). Dans les deux, elle relève les mêmes choses:

| Ce que l'usine relève | Dans ce format | Dans l'ancien |
| --- | --- | --- |
| Le titre | `# <Titre court>` | le titre |
| Le besoin | « Le besoin », avec « Quand », « Étapes » et « Règles de décision » | « Mon besoin » |
| Les vraies situations | « Situations réelles » | « Mes vraies situations » |
| Les contraintes | « Contraintes », « Outils », « Qui voit le résultat » | « Mes contraintes » |
| Ce qu'elle garde en main | « Ce que je garde en main » | « Ce que je garde en main » |
| Ce qui est à trancher | « À trancher » et « À confirmer » | « À trancher » |
| Automatiser, ou le niveau souhaité | « Niveau souhaité »: 3 ou 4 vaut une demande d'automatiser pour l'étape 2, sans fixer le niveau; plus bas que 2, il s'applique tel quel; plus haut que 2, il suit « Monter le niveau » après le choix | « Automatiser » |

Une fiche de ce format à l'état « brouillon » n'est pas encore une fiche pour l'usine: l'entretien reprend jusqu'à la validation.
