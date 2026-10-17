# Les limites qui ne dépendent ni du cas ni de la personne

Ces limites valent pour tout outil fabriqué par l'usine. Chacune a sa source: une page officielle, lue à la date dite, ou un fait constaté par le projet, avec sa date. Ce qui y était écrit ce jour-là n'est pas une preuve du jour: avant d'écrire « établi » à la personne, relis la page. Une page introuvable ou changée se dit, et la limite redevient « à vérifier ».

Ne les récite pas toutes. Dis-les au bon moment, en mots simples:
- à l'étape 2, chaque choix porte une ligne « Ce que l'outil ne pourra pas faire », tirée de cette liste: seulement les limites qui touchent ce choix;
- dans `dependances.md`, la section « Ce que l'outil ne peut pas faire »;
- au tableau, dans `outil-<cle>`, le champ `ne_peut_pas`: une liste de phrases courtes.

## 1. Où vit le paquet

- Pour la personne: « L'outil vit dans l'application Claude (Cowork, ou l'onglet Code), avec une offre payante, sauf peut-être pour un paquet ajouté à la main (à vérifier). »
- Source: les plugins se chargent dans les tâches de Cowork, et leur répertoire est ouvert aux offres Pro, Max, Team et Enterprise (https://claude.com/docs/plugins/overview, lu le 14 octobre 2026); les tâches planifiées de Cowork sont « available on all paid plans » (https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork, lu le 16 octobre 2026). Une page cite aussi l'offre gratuite pour les skills (https://support.claude.com/en/articles/12512180-using-skills-in-claude, lu le 14 octobre 2026): l'offre requise pour un paquet ajouté à la main reste « à vérifier ». Le prix de chaque offre: https://claude.com/pricing, à lire le jour même, sinon « à vérifier ».

## 2. Un outil, c'est surtout des consignes

- Pour la personne: « L'outil ne travaille que quand Claude tourne, dans une tâche que vous ouvrez ou une tâche planifiée. Chaque passage compte sur l'usage de votre compte Claude. »
- Source: constaté le 16 octobre 2026: l'outil fabriqué est un dossier de consignes que suit une nouvelle tâche de Claude (rejeu du banc du projet). Les routines du cloud comptent sur l'usage de l'abonnement comme une séance ordinaire (https://code.claude.com/docs/en/routines, lu le 16 octobre 2026). Pour les tâches de Cowork et les tâches locales, le coût n'est pas écrit: « à vérifier ».

## 3. Travailler à heure fixe

- Pour la personne, selon le choix:
  - tâche locale de l'onglet Code: « Elle ne tourne que si l'ordinateur est éveillé et l'application ouverte. Un passage manqué n'est rattrapé qu'une fois, au réveil. »
  - tâche Cowork: « Depuis le 6 octobre 2026, une nouvelle tâche Cowork des offres Pro et Max tourne dans le cloud, ordinateur éteint, mais n'atteint les fichiers de l'ordinateur que si l'application est ouverte. Une tâche qui a besoin des fichiers ou des applications de l'ordinateur tourne seulement sur l'ordinateur. Pour les offres Team et Enterprise: à vérifier. »
  - routine du cloud: « Elle tourne ordinateur éteint, mais ne lit pas les fichiers de l'ordinateur: seulement Google Drive (par un connecteur) ou GitHub. Une heure au moins entre deux passages. »
- Source: https://code.claude.com/docs/en/desktop-scheduled-tasks (tâches locales: « Tasks only run while the desktop app is running and your computer is awake »), https://support.claude.com/en/articles/15520349-use-claude-cowork-on-web-desktop-and-mobile (« new Cowork tasks on Pro and Max plans run in the cloud ») et https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork (« If a scheduled task requires local files or apps, it will only run locally »), https://code.claude.com/docs/en/routines (routines, intervalle d'une heure au moins), lus le 16 octobre 2026.

## 4. Le tableau

- Pour la personne: « Un clic dans le tableau n'arrive à l'outil qu'à son passage suivant (à vérifier). Le tableau ne garde que du texte. Hors du mode Auto, une écriture au tableau peut être refusée; elle peut aussi demander votre clic (à vérifier). »
- Source: constaté le 16 octobre 2026, séances d'essai du projet sur un tableau d'essai: en mode « ne pas demander », l'écriture dans la base a été refusée; en mode Auto, elle est passée. À vérifier: le clic réel dans le tableau (l'essai a écrit le champ à la place du clic, puis l'outil l'a appliqué à son passage suivant), et le clic demandé dans un autre mode qu'Auto. Texte seul: https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them (« text only »), lu le 16 octobre 2026.

## 5. Agir sur un site

- Pour la personne: « Pour agir sur un site, l'outil passe par Claude in Chrome. Pas depuis l'onglet Code de l'application. Vous vous connectez vous-même, et vous passez vous-même les vérifications anti-robot. Les conditions du site s'appliquent, et Chrome peut refuser une action. »
- Source: pour Claude Code, Claude in Chrome est documenté pour la ligne de commande et VS Code, pas pour l'application de bureau (https://code.claude.com/docs/en/chrome, lu le 16 octobre 2026). Pour Cowork, l'accord par site et ce qui est toujours demandé: https://support.claude.com/en/articles/12902446-claude-in-chrome-permissions-guide (lu le 14 octobre 2026). La personne répond de ce qui est publié ou envoyé: https://support.claude.com/en/articles/12902428-use-claude-in-chrome-safely (lu le 14 octobre 2026). Un refus de cliquer « Publier » est possible: à dire s'il arrive.

## 6. Jamais, à aucun niveau

- Pour la personne: « Jamais, à aucun niveau: vos mots de passe, un paiement, la suppression de fichiers, la création d'un compte, la collecte de données sur d'autres personnes. »
- Source: règle du paquet (« Ce qui reste interdit », dans le texte de l'usine). Les achats et la création de comptes sont aussi interdits à Claude in Chrome: https://support.claude.com/en/articles/12902446-claude-in-chrome-permissions-guide (lu le 14 octobre 2026).

## 7. Ni serveur ni abonnement

- Pour la personne: « L'usine ne crée ni serveur ni abonnement. Si l'outil en demande un, elle le décrit, et c'est vous qui décidez et qui le faites. »
- Source: règle du paquet (étape 3 du texte de l'usine: « Ce qui exige un serveur, un abonnement ou un compte: tu le décris »).

## 8. Où vont les données

- Pour la personne: « Ce que Claude lit et écrit passe par Anthropic. Ce qui passe par un connecteur passe aussi par son éditeur, par exemple Google. »
- Source: pour Anthropic, https://code.claude.com/docs/en/data-usage (lue le 7 octobre 2026; à relire le jour même). Pour l'éditeur de chaque connecteur: sa page de confidentialité, à lire le jour même, sinon « à vérifier ». Un contrat de sous-traitance des données n'existe chez Anthropic que dans ses offres commerciales (voir `references/sources-de-depart.md`).
