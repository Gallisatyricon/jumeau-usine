# Le tableau et le contrat des données

Le tableau est la page où la personne suit tous ses besoins et tous ses outils. Il y en a un seul par personne. L'usine et le jumeau (le texte voisin, `skills/jumeau/`) suivent ce même contrat. Le modèle est `assets/tableau-du-jumeau.html`. La page lit sa base en direct: dès qu'un document change, elle change sous les yeux de la personne. Toi, tu n'écris que dans sa base. Jamais tu ne republies ni ne modifies la page d'un tableau existant: la page se change par le projet, pas par l'usine.

## Les outils du tableau

Les outils du tableau s'appellent ArtifactData (lire et écrire dans la base) et Artifact (publier, lister ses pages). S'ils ne sont pas déjà chargés, charge-les par ToolSearch avec la requête exacte `select:ArtifactData,Artifact`. Une recherche par mots ne suffit pas: l'outil n'est « absent » que si cette requête exacte ne le trouve pas.

## Trouver le tableau

Dans cet ordre, et arrête-toi au premier trouvé:

1. un lien de tableau dans `tableau.md` du dossier de l'outil;
2. un lien de tableau dans la fiche;
3. une page publiée de la personne dont le titre contient « Tableau de bord du jumeau », dans la liste de ses pages publiées, si l'outil de liste existe dans la séance;
4. sinon, demande en une question: « Avez-vous déjà un tableau de bord du jumeau ? Collez son lien, ou dites non. »

Sur « non »: publie le modèle `assets/tableau-du-jumeau.html` tel quel, comme nouvelle page, avec les capacités `db` et `user`. Avant, préviens la personne en une phrase que l'application va demander son accord pour cette première publication.

Le lien trouvé ou créé s'écrit dans `tableau.md` du dossier de l'outil. Le jumeau l'écrit dès le cadrage, avec la clé qu'il a choisie, même hors ligne (« Lien: aucun, tableau hors ligne »). L'usine reprend cette clé et ne la change jamais.

```
# Le tableau du jumeau

- Lien: <lien du tableau>
- Clé de cet outil: <cle>
```

## Sans outil d'écriture dans la base

Si l'outil d'écriture dans la base n'existe pas dans la séance, ou si aucun tableau n'a pu être trouvé ni publié: dis-le en une phrase, continue dans la conversation, et garde dans le dossier de l'outil un fichier `tableau-hors-ligne.json` avec les documents qui auraient été écrits. Ce fichier est un seul objet JSON: chaque clé est l'identifiant d'un document, chaque valeur ce document, dans son dernier état. À chaque écriture, change seulement les champs qui changent: ne raccourcis ni ne résume jamais un document déjà écrit. Ne fais jamais semblant d'avoir écrit au tableau.

## Les documents

Tout va dans la collection `data/users/me` de la base du tableau. Elle est privée à la personne. `me` désigne la personne pour l'outil d'écriture; la page lit la même collection sous son identifiant. Un document par chose, d'identifiant `<sorte>-<cle>`. `<cle>` est le nom court de l'outil, en minuscules et tirets, par exemple `posts-asso`. Le champ `type` est obligatoire.

### `besoin-<cle>`

- `type`: `"besoin"`.
- `titre`, `resume`.
- `etat`: « en entretien », « décrit », « à faire », « en fabrication », « en essai », « en service » ou « en pause ». Le jumeau écrit « en entretien » dès le cadrage, puis « décrit » à la validation de la fiche; une procédure décrite mais pas encore outillée reste « décrit ».
- `ou_en_est`: une phrase. À « décrit », elle donne le lien de la fiche (son chemin dans le dossier).
- `etape`: de 1 à 7 pendant la fabrication; absent sinon.
- `maj`: l'heure de l'écriture. La page ne l'affiche pas aujourd'hui.

### `outil-<cle>`

- `type`: `"outil"`.
- `titre`, `resume`.
- `etat`: « en fabrication », « en essai », « en service », « en pause » ou « arrêté ». La page montre « en service » en vert et « arrêté » en rouge.
- `niveau`: de 0 à 4. `niveau_texte`: ce niveau en une phrase. `niveau_le`: l'heure du dernier changement de `niveau`, écrite à chaque changement.
- `limites`: au niveau 4, ce que l'outil fait seul, combien par période, ce qu'il ne fait jamais; une liste de phrases courtes.
- `declencheur`: quand il travaille. `ou`: où il tourne.
- `depend`: liste. `editeur`: liste.
- `ne_peut_pas`: liste de phrases courtes, ce que l'outil ne peut pas faire, tirées de `references/limites.md`. La page les montre sous « Ce qu'il ne peut pas faire ».
- `risque`, `sortie` (comment en sortir), `maj`.

La page écrit elle-même `niveau_demande` et `niveau_demande_le` quand la personne demande un autre niveau. Tu les lis, tu ne les inventes jamais. Une demande ne vaut que si `niveau_demande_le` est plus récent que `niveau_le`, ou si `niveau_le` est absent. Une demande qui vaut et qui est plus basse que `niveau` s'applique au prochain passage de l'outil ou de l'usine: celui qui la lit l'écrit dans `niveau`, avec `niveau_le`, et ajoute une ligne à `journal-<cle>`. Plus haute, elle attend l'usine, qui suit la règle « Monter le niveau ».

### `productions-<cle>`

- `type`: `"productions"`, `outil`: la clé de l'outil.
- `items`: liste de `{cle, date, titre, texte, statut, reste, essai}`. `essai`: `true` pour un essai de l'usine, `false` pour une sortie de l'outil. `statut`: « à relire », « à publier », « publié » ou « envoyé »; la page montre « publié » en vert. `reste`: ce qui reste à faire à la personne, ou vide.

Une production nouvelle qui refait la même chose (même situation, même sujet) remplace l'élément de même `cle`: la personne ne voit que la dernière version. Cinquante éléments au plus, les plus récents.

### `attente-<cle>-<code>`

- `type`: `"attente"`.
- `titre`, `detail`, `outil`, `cree`.
- `choix`: liste de `{id, nom, detail}`.
- `suite`: ce qui se passera après la réponse.

La page écrit `reponse` et `repondu_le` au clic. Quand tu as pris la réponse en compte, écris `pris_en_compte_le` et mets à jour `suite`. Si la personne répond dans la conversation, écris toi-même `reponse` et `repondu_le`, pour que le tableau dise la même chose.

### `journal-<cle>`

- `type`: `"journal"`.
- `items`: liste de `{quand, qui, texte}`. Cent éléments au plus.

Chaque écrivain a son propre document de journal. Le jumeau, l'usine et l'outil écrivent dans `journal-<cle>`, avec `qui` égal à « le jumeau », « l'usine » ou « l'outil ». Jamais dans le document `journal` d'un autre.

## Les règles d'écriture

- Lis le document avant de l'écrire, et passe sa version: c'est une écriture épinglée. En cas de refus parce que la version a changé, relis et refais une fois, puis dis-le.
- Ne supprime jamais un document.
- Ne touche jamais aux documents d'un autre outil.
- Heures en UTC, au format `AAAA-MM-JJTHH:MM:SSZ`, lues par une commande, jamais estimées.
- Texte seul.
- Aucun mot de passe, code ou clé. Dans tout ce qui va au tableau, les noms et adresses de tiers sont remplacés par « [client] » ou « [contact] ».
