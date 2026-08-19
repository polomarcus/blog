---
title: "Analyse de 237 000 reportages des JT : on a triplé le volume, pas le fond"
date: 2026-08-17
draft: true
thumbnail: "images/2026/jt-2026-part-climat-par-chaine@2x.png"
images:
    - "images/2026/jt-2026-part-climat-par-chaine@2x.png"
series: ["jt"]
tags: ["climat", "médias", "jt", "data"]
description: "Quatre ans après l'analyse des 60 000 reportages, le corpus atteint 237 668 : la couverture climat des JT a triplé, mais pas le fond. On filme les larmes plutôt que les causes, on dit pourrait, on efface les responsables."
---

*Suite de l'article de 2022 "[Analyse de 60 000 reportages des JT de 20h France 2 et TF1](https://www.epauler.fr/article/analyse-de-60000-reportages-des-jt/)".*

Le 26 juin 2026, en pleine canicule, [Jean-Marc Jancovici est l'invité du 20H de France 2](https://www.francetvinfo.fr/environnement/evenements-meteorologiques-extremes/vagues-de-chaleur-canicules/canicule-ce-qui-est-tres-difficile-pour-nous-aujourd-hui-c-est-de-comprendre-que-le-monde-est-fini-estime-jean-marc-jancovici-president-de-the-shift-project_8081849.html). Face à lui, Laurent Delahousse cherche une sortie, presque plaintif : "Ça veut dire que je dis quoi à ma fille qui a 10 ans, ce soir ? Je lui dis : “Écoute, la planète elle est foutue, mais on peut faire quelques efforts pour lui limiter le pire qui arrive quand même” ?" Réponse de l'invité : "Pardonnez-moi d'être un peu taquin, mais à votre fille, vous pouvez lui dire : “Tu sais, papa va se mettre à parler un peu plus du sujet, de telle sorte qu'on s'en occupe un peu plus.”" Le présentateur se défend en assurant qu'"on en parle beaucoup en tout cas, et notamment en magazine", c'est-à-dire ailleurs qu'au JT, avant de concéder que "vous avez probablement raison, peut-être qu'on devrait encore en parler plus".

Qui a raison ? Il y a quatre ans, j'analysais 60 000 reportages des JT de 20h et je découvrais que 99,2 % d'entre eux ne contenaient ni "réchauffement", ni "dérèglement", ni "changement climatique". [L'observatoire](https://observatoire.climatmedias.org/) continue depuis de scanner chaque jour les pages des JT de TF1 et France 2, si bien que le corpus atteint aujourd'hui 237 668 reportages qui couvrent février 2013 au 14 août 2026. Et la part des reportages qui nomment le climat a presque triplé depuis 2021. Delahousse aurait donc raison ? J'ai refait tourner l'analyse, et ma réponse tient en une phrase : **on a triplé le volume, pas le fond.** La quantité de reportages a explosé, mais les règles implicites qui les fabriquent n'ont pas bougé, puisqu'on filme toujours les larmes plutôt que les causes, qu'on dit toujours "pourrait" et qu'on efface toujours les responsables.

---

## Avant de commencer

La méthode n'a pas changé : un programme scanne les pages web des JT et cherche dans le titre et le texte de chaque reportage "réchauffement / dérèglement / changement(s) / crise climatique" et leurs variantes, ainsi que "GIEC", "gaz à effet de serre", "transition écologique", "bas carbone" ou "jour du dépassement". [Tout est open source](https://github.com/polomarcus/television-news-analyser), données comprises. Ce comptage mesure si le sujet est *nommé*, pas si le reportage est bon, et c'est précisément ce que je veux mesurer.

Trois limites sont à avoir en tête, et je les détaille en fin d'article. Le texte récupéré sur TF1 a été divisé par deux à partir de 2024, ce qui tire son score vers le bas. France 3 a disparu des données en septembre 2023, quand la direction de France Télévisions a supprimé l'édition nationale du 19/20. Enfin, les comparaisons d'une année sur l'autre restent solides tant que les conditions de collecte ne changent pas.

---

## 2022, l'année où la pendule a été remise à l'heure

Le chiffre qui avait marqué en 2022, c'était **99,2 % de silence**. Quand je le recalcule sur le corpus complet, je trouve que **0,89 %** des reportages de 2013-2021 nomment le climat, autrement dit 99,1 % de silence, contre **2,46 %** depuis 2022, ce qui laisse tout de même 97,5 % de silence. L'année charnière saute aux yeux :

| Année | France 2 | TF1 |
|---|---|---|
| 2019 | 1,65 % | 1,03 % |
| 2020 | 0,80 % | 0,57 % |
| 2021 | 1,36 % | 1,34 % |
| **2022** | **2,80 %** | **1,67 %** |
| 2023 | 3,57 % | 2,90 % |
| 2024 | 2,78 % | 1,83 %* |
| 2025 | 2,89 % | 0,89 %* |
| 2026 (janvier-août) | 3,49 % | 1,01 %* |

*\* chiffres TF1 2024-2026 sous-estimés et non comparables aux années antérieures, mais comparables entre eux (voir limites).*

{{< figure src="/images/2026/jt-2026-part-climat-par-chaine.svg" alt="Part annuelle des reportages nommant le climat, France 2 et TF1, 2013-2026 : quasi-triplement après 2021, décrochage de TF1 après 2023" >}}

2022, c'est l'année des canicules à répétition et des mégafeux, mais c'est aussi celle où plus de 1 500 journalistes signent la [Charte pour un journalisme à la hauteur de l'urgence écologique](https://chartejournalismeecologie.fr/), poussés par des collectifs citoyens comme [QuotaClimat](https://www.quotaclimat.org/) ou [Climat Médias](https://climatmedias.org/). Le climat gagne alors la hiérarchie de l'info : France 2, qui n'avait ouvert son JT que **17 fois sur le sujet en neuf ans**, le fait **47 fois en quatre ans et demi**, et la part des reportages climat dans les cinq premiers sujets monte de 23,5 % à 34,6 %. Le 26 mars 2026, la chaîne ouvre même sur "[Le retour de la neige en basse altitude, “un marqueur du changement climatique”](https://www.francetvinfo.fr/environnement/meteo/neige/le-retour-de-la-neige-en-basse-altitude-un-marqueur-du-changement-climatique_7896344.html)", une phrase qui aurait sans doute été coupée au montage en 2021.

C'est la bonne nouvelle de cet article. Elle s'arrête à peu près ici.

---

## TF1 fait marche arrière

Après un pic à 2,90 % en 2023, où TF1 faisait presque jeu égal avec France 2, la collecte change en 2024 et les niveaux d'après ne sont plus comparables à ceux d'avant. Mais ce que l'on peut affirmer à méthode strictement constante suffit : **de 2024 à 2025, TF1 divise sa couverture climatique par deux** (1,83 % → 0,89 %), sans annonce et sans débat, pendant que France 2 se maintient entre 2,8 et 3,6 %. L'écart entre les deux chaînes n'a jamais été aussi grand. La Charte de 2022 a-t-elle tenu ses promesses ? Chez TF1, la réponse est dans le tableau.

Quant au test "Don't Look Up" de mon [article sur la vague de chaleur de décembre 2021](https://www.epauler.fr/article/vague-de-chaleur-decembre-2021-dont-look-up-a-la-francaise/), ces JT qui trinquaient au rosé pendant le Noël le plus doux jamais enregistré sans prononcer le mot "climat", il s'améliore, mais au gré du thermomètre, comme un élève qui ne révise que la veille du contrôle : décembre 2024, doux et sans COP marquante, retombe sous 1,5 %, alors que pendant les canicules de juin 2026 France 2 monte à 5,3 % quand TF1 reste à 1,7 %. Surtout, nommer ne veut pas dire relier, car d'après un décompte que QuotaClimat a publié en juin 2026, France 2, pourtant le bon élève, ne liait canicule et réchauffement que dans 37 % des séquences dédiées.

---

## Plus on en parle, moins on explique

**La couverture climat de 2015 était rare mais substantielle, celle de 2026 est abondante mais ressemble à un bulletin météo.** C'est le résultat central de cette mise à jour, et il répond directement au "on en parle beaucoup" de Delahousse.

Pour le mesurer, j'ai fait classifier par IA les 3 448 reportages qui nomment le climat afin de savoir quel angle ils adoptent, qui y parle et quels secteurs émetteurs y sont nommés, avec une grille proche de celle de [l'Observatoire des médias sur l'écologie](https://observatoiremediaecologie.fr/audiovisuel/methodologie/), le tout [publié](https://github.com/polomarcus/television-news-analyser/blob/main/docs/data-aggregated-news-json/classification-climat.README.md) et [explorable année par année](https://observatoire.climatmedias.org/annees.html).

Les reportages climat "de fond", ceux qui expliquent les causes, qui couvrent la politique climatique ou les rapports scientifiques, représentaient **de l'ordre de 40 % de la couverture entre 2014 et 2017**. Ils tombent à 20,8 % sur 2022-2026, puis à **14,8 % en 2026**, alors même que c'est l'été des cinq canicules. Le calendrier diplomatique n'explique pas tout, puisqu'en 2023, année d'une COP et de la synthèse du GIEC, le fond ne remonte qu'à 21,3 %. La couverture de la politique climatique s'effondre, passant de 12,7 % des reportages climat avant 2022 à **4,8 %** depuis, le constat des conséquences domine avec 46,6 % en 2026, et le climat "cité en passant" a triplé. Cité en passant, ça donne "[Un ours brun capturé après quatre jours de panique au nord de Tokyo](https://www.francetvinfo.fr/monde/japon/un-ours-brun-capture-apres-quatre-jours-de-panique-au-nord-de-tokyo_8052308.html)", où le réchauffement explique dans une subordonnée pourquoi les ours descendent en ville. Chez TF1, sur 2022-2026, c'est même devenu la première catégorie (37,3 %).

{{< figure src="/images/2026/jt-2026-part-fond.svg" alt="Part des reportages climat de fond (causes, politique, science) : environ 40 % en 2014-2017, 14,8 % en 2026" >}}

Le triplement du volume est donc un triplement du constat, pas de l'explication, puisque les reportages centrés sur les causes restent à 5 % sur toute la période. Ils existent pourtant, et "[Aux origines du réchauffement climatique : la vidéo exceptionnelle de TF1 pour tout comprendre en 6 minutes](https://www.tf1info.fr/environnement-ecologie/aux-origines-du-rechauffement-climatique-la-video-exceptionnelle-en-realite-augmentee-de-tf1-pour-tout-comprendre-en-6-minutes-2277936.html)" (avril 2024) reste un modèle du genre.

---

## Le spectacle : la grand-mère en pleurs a remplacé le ministre

Comment parle-t-on d'une catastrophe sans parler de ses causes ? En filmant les larmes. Sur les **23 144 reportages** du corpus qui traitent d'un événement météo extrême, 34,4 % relèvent du registre émotionnel ou victimaire alors que **1,3 % seulement nomment une cause**, et 0,3 % font les deux. Ces proportions n'ont pas bougé avant ou après 2022, l'émotion est identique au dixième de point près. La grand-mère en pleurs devant sa maison brûlée est un format, pas un accident, un format aussi rodé que le reportage sur les soldes : "[“On a mis tout notre amour dans cette maison” : à Biscarrosse, la détresse de ceux qui ont “tout perdu” dans l'incendie](https://www.francetvinfo.fr/faits-divers/incendie/on-a-mis-tout-notre-amour-dans-cette-maison-a-biscarrosse-la-detresse-de-ceux-qui-ont-tout-perdu-dans-l-incendie_8131622.html)" (France 2, août 2026). TF1 le dit même sans s'en rendre compte dans "[**Spectacle** de désolation après les incendies dans le Gard](https://www.tf1info.fr/regions/videos/video-spectacle-de-desolation-apres-les-incendies-dans-le-gard-77883-2451713.html)" (juillet 2026). Aucun des deux ne prononce le mot "climat".

La classification mesure la même bascule côté micro. Avant 2022, un reportage climat faisait parler un politique (36,3 %) ou un scientifique (27,3 %), et le témoin anonyme n'apparaissait que dans 9,3 % des cas. Depuis, le témoin a **triplé (30,8 %)** jusqu'à dépasser le scientifique, pendant que le politique recule (26,2 %). L'ère COP21 interviewait des ministres, l'ère des canicules interviewe des sinistrés.

{{< figure src="/images/2026/jt-2026-intervenants.svg" alt="Intervenants des reportages climat avant/depuis 2022 : le témoin anonyme triple (9,3 % à 30,8 %) et dépasse le scientifique, le politique recule" >}}

Ce n'est pas anodin. Shanto Iyengar (*Is Anyone Responsible?*) a montré expérimentalement que ce cadrage "épisodique", celui de l'événement, de la victime et de l'émotion, conduit le public à chercher des responsabilités individuelles, quand le cadrage "thématique" le conduit à en demander compte aux institutions. Filmer les larmes plutôt que le baril de pétrole n'est pas une neutralité, c'est un choix politique qui s'ignore.

---

## La logocratie du 20H : quatre figures pour parler sans affirmer

Dans *Le Pouvoir rhétorique*, Clément Viktorovitch, que je citais déjà en 2022, défend une idée simple : nous vivons en **logocratie**. Le pouvoir appartient à ceux qui maîtrisent la parole, et les choix de mots fabriquent ce qui est discutable. Les tics rhétoriques du 20H se mesurent, en voici quatre.

**La nomination.** "Réchauffement climatique", le terme le plus doux, écrase "crise climatique" et "urgence climatique", qui restent marginaux, pendant que le vocabulaire qui naturalise prospère, de la "catastrophe naturelle" aux "aléas climatiques". Un épisode se termine, un aléa n'a pas de coupable.

**La modalisation.** 22,0 % des reportages climat de 2013-2021 contiennent "pourrait(nt)", et 22,3 % depuis. Treize ans de consensus scientifique croissant n'ont pas déplacé la prudence d'un millimètre.

**L'interrogation.** **16,7 %** des reportages climat portent un titre interrogatif, contre 12,9 % pour le reste du corpus, et la figure progresse puisqu'on passe de 14,5 % avant 2022 à 18,1 % depuis. "[Vers une 4e canicule : est-ce le signe de l'accélération du réchauffement climatique ?](https://www.francetvinfo.fr/replay-jt/france-2/13-heures/vers-une-4e-canicule-est-ce-le-signe-de-l-acceleration-du-rechauffement-climatique_8127200.html)" : le GIEC a répondu il y a des années, le titre repose la question.

**L'effacement de l'agent.** "La planète *se* réchauffe" : cette tournure sans sujet responsable est **sept fois plus fréquente** que l'attribution explicite du réchauffement à l'activité humaine. Dans le JT, le climat se dérègle tout seul, comme il pleut. Et quand il n'y a pas d'agent, il n'y a pas de responsable, donc pas de politique à mener.

{{< figure src="/images/2026/jt-2026-vocabulaire.svg" alt="Nombre de reportages par expression : réchauffement climatique 1931, catastrophe naturelle 714, la planète se réchauffe 396, épisode caniculaire 252, aléas climatiques 191, contre urgence climatique 82, crise climatique 57, attribution à l'activité humaine 54" >}}

Aucune de ces figures n'est un mensonge, et c'est bien pour cela qu'elles sont efficaces. Dans une logocratie, compter les mots, c'est contester le pouvoir de ceux qui les choisissent.

---

## Le lendemain de Jancovici, le 13H partait pour le Sri Lanka

Revenons au 26 juin 2026. Le 20H de ce soir-là ouvre sur six sujets canicule d'affilée, mais le seul qui nomme le dérèglement, "[malgré 50 ans d'alerte, un dérèglement climatique qui s'accentue inexorablement](https://www.francetvinfo.fr/environnement/evenements-meteorologiques-extremes/vagues-de-chaleur-canicules/environnement-malgre-50-ans-d-alerte-un-dereglement-climatique-qui-s-accentue-inexorablement_8081801.html)", arrive en **septième position**, avant le pape et France-Norvège. Le 13H du même jour se termine par "[Voyage en Suisse normande](https://www.francetvinfo.fr/france/normandie/voyage-en-suisse-normande-entre-riviere-et-paysages-grandioses_8081258.html)" et "[la gentiane auvergnate, pour un apéritif à l'amertume particulière](https://www.francetvinfo.fr/france/auvergne-rhone-alpes/cantal/la-gentiane-auvergnate-une-fleur-jaune-pour-un-aperitif-a-l-amertume-particuliere_8081378.html)". Le lendemain midi, pendant que la France comptait ses morts, la même chaîne diffusait "[Paysages à couper le souffle, thé noir… À la découverte du train bleu du Sri Lanka](https://www.francetvinfo.fr/replay-jt/france-2/13-heures/paysages-a-couper-le-souffle-the-noir-a-la-decouverte-du-train-bleu-du-sri-lanka_8082641.html)". Le 30 juin, le Conseil d'État [donnait son feu vert à l'A69](https://www.francetvinfo.fr/replay-jt/france-2/13-heures/le-conseil-d-etat-donne-son-feu-vert-au-chantier-de-l-a69-entre-toulouse-et-castres_8086811.html), traité sans le mot "climat".

Ce zapping est un format mesurable, car sur les 2 327 JT du corpus qui contiennent un sujet climat, **502, soit plus d'un sur cinq, contiennent aussi une carte postale touristique dans la même édition**. Le 6 août 2026, le 20H enchaîne [la sécheresse "prévue pour la fin du siècle" déjà là](https://www.francetvinfo.fr/environnement/crise-climatique/l-objectif-c-est-d-avoir-la-secheresse-prevue-pour-la-fin-du-siecle-en-2100-comment-les-scientifiques-testent-les-arbres-pour-tenter-de-repondre-a-la-crise-climatique_8137721.html) et "[l'île de Lamu, un joyau séculaire du Kenya](https://www.francetvinfo.fr/monde/afrique/kenya/maisons-en-corail-transport-en-ane-et-aucun-vehicule-a-moteur-l-ile-de-lamu-un-joyau-seculaire-de-kenya-preserve-du-tourisme-de-masse_8137736.html)". Ces cartes postales sont une rubrique à part entière, puisque sur 968 reportages croisières et paquebots, **98,1 % ne prononcent jamais le mot "climat"**, dont "[Croisière : le plus grand paquebot du monde embarquera 10 000 personnes](https://www.francetvinfo.fr/economie/tourisme/croisiere-le-plus-grand-paquebot-du-monde-embarquera-10-000-personnes_6078288.html)" (2023, alors l'année la plus chaude jamais mesurée) et "[Les Maldives : à la découverte de ces îles d'exception](https://www.francetvinfo.fr/replay-jt/france-2/13-heures/les-maldives-a-la-decouverte-de-ces-iles-d-exception_8107721.html)" (juillet 2026, en pleine canicule). On en parle, puis on repart en croisière, et cette dissonance n'est pas un accident de conducteur, elle est dans le conducteur.

---

## Ce que le JT préfère au climat

Un seul graphique suffit, sur les 237 668 reportages, à situer les priorités.

{{< figure src="/images/2026/jt-2026-priorites.svg" alt="Nombre de reportages par thème en treize ans de JT : Tour de France 701, écogestes 378, énergies fossiles 203, galette des rois 99, adaptation 51, GIEC 13, éco-anxiété 6" >}}

Les 13 titres sur le GIEC en treize ans datent, pour les derniers, de mars 2023, dont celui-ci chez TF1 : "[Le nouveau rapport du Giec sur le climat : il y a urgence mais chaque geste compte](https://www.tf1info.fr/environnement-ecologie/video-dereglement-climatique-il-y-a-urgence-selon-le-giec-mais-chaque-geste-compte-2251612.html)". Et si on reprend la grille des postes d'empreinte carbone de [nosgestesclimat.fr](https://nosgestesclimat.fr/), **56 % des reportages climat ne nomment aucun secteur émetteur**, et la viande et l'élevage, qui pèsent parmi les tout premiers postes, n'apparaissent comme source d'émissions que dans 124 reportages en treize ans, soit **0,05 % de tout ce que diffusent les JT**.

Quant à l'éco-anxiété, six reportages en treize ans, dont deux qui sont des sujets "nouveaux mots du dictionnaire". Le dernier, "[“Il n'y a pas de profil type” : ces personnes qui souffrent d'éco-anxiété](https://www.francetvinfo.fr/replay-jt/france-2/20-heures/il-n-y-a-pas-de-profil-type-ces-personnes-qui-souffrent-d-eco-anxiete_8146616.html)" (août 2026), range en rubrique psychologique la souffrance que ce régime d'information contribue lui-même à produire.

---

## Que fait une décennie de ce régime à un pays ?

Ce régime événementiel, émotionnel, prudent et dissonant, qui s'appauvrit à mesure qu'il s'étend, ne fabrique pas de l'ignorance, car les Français savent. Il fabrique une **connaissance sans conséquence** : le sujet est livré comme une météo, un état du ciel plutôt qu'un état des rapports de force. [L'Observatoire des médias sur l'écologie](https://observatoiremediaecologie.fr/) mesure le même mécanisme sur tout l'audiovisuel, qui n'a consacré que 4,9 % de son temps d'antenne à l'écologie en 2025. Et pendant la campagne des municipales de 2026, le moment où les responsabilités se décident, la couverture a même [reculé de 24 %, à 2,8 % en mars, son plus bas niveau depuis 2023](https://quotaclimat.org/actualites/municipales-2026-la-couverture-mediatique-des-enjeux-environnementaux-a-subi-un-recul-historique/). Quand le sujet devient électoral, donc politique, il disparaît, et c'est exactement la thèse de Jean-Baptiste Comby, que nos données vérifient année après année.

Clément Sénéchal (*Pourquoi l'écologie perd toujours*, 2024) pousse le diagnostic plus loin : l'écologie perd quand elle renonce au conflit, quand elle ne désigne plus d'adversaire. Nos données décrivent le versant médiatique de ce mécanisme, car un JT qui n'explique les causes que dans 5 % de ses reportages climat n'offre littéralement aucun conflit à trancher. Et même dans ces 5 %, près d'un reportage sur trois s'en tient aux "activités humaines", ce flou universalisant dont Comby notait déjà qu'il "ne favorise pas une discussion sur les logiques productives, industrielles ou financières". On peut être informé de tout et incapable de rien.

---

## À qui profite ce traitement ?

Reste la vraie question : pourquoi rien ne bouge, alors que les rédactions savent, signent des chartes et créent des postes dédiés ? Parce que ce traitement n'est pas une paresse, il remplit une fonction.

C'est la thèse des *Nouveaux Chiens de garde* (Serge Halimi, 1997, puis le documentaire de Balbastre et Kergoat en 2012) : les grands médias appartiennent à des groupes industriels pour qui l'information est un instrument d'influence, et le journalisme dominant, socialement intégré aux élites qu'il devrait surveiller, garde l'ordre établi. Le cas d'école est sous nos yeux depuis 1987, puisque TF1 appartient à Bouygues, un groupe qui vit du béton, des routes et de la commande publique, c'est-à-dire de l'un des secteurs qu'un traitement sérieux du climat devrait nommer. Un chien de garde ne mord pas la main qui le nourrit. Julia Cagé a ajouté l'autre moitié du bilan comptable en montrant qu'une information financée par la publicité ne peut pas traiter ses annonceurs en adversaires, et les écrans qui encadrent le 20H vendent des voitures, des voyages et de la grande distribution.

Le dernier verrou n'a pas besoin de consigne. L'émission "Rhinocéros" de Blast l'a montré en disséquant les JT de la canicule de mai 2026 : un JT de classes moyennes supérieures, où l'on compare les climatiseurs à 10 000 euros et les piscines privées "éco-responsables" avec la fédération professionnelle en plateau mais sans les associations en face, et où la mort d'un ouvrier de 19 ans sur une toiture en plein cagnard ne trouve pas sa place entre deux sujets tomates-mozzarella. Expliquer réellement les causes reviendrait à mettre en accusation un mode de vie, celui des dirigeants des rédactions, de leurs invités et d'une partie de leur public. Les croisières, les SUV, les Maldives.

Un cas résume tout. Pendant cette canicule de mai, la géographe Magali Reghezza-Zitt, venue parler d'adaptation au 20H, se voit demander par Léa Salamé s'il faut "mettre le ventilo" et s'il y aura "des moustiques du futur". Or le reportage écrit qui accompagnait ce passage, "[“Les solutions sont déjà là”](https://www.francetvinfo.fr/environnement/evenements-meteorologiques-extremes/vagues-de-chaleur-canicules/les-solutions-sont-deja-la-face-au-rechauffement-la-geographe-magali-reghezza-zitt-estime-qu-il-va-falloir-changer-nos-habitudes-de-vie_8030114.html)", figure dans notre top 3 des *meilleurs* reportages climat de 2026. Le fond existe dans la rédaction, c'est le plateau qui le dissout.

Et ce vide a un occupant. Pendant que le JT constate sans expliquer, d'autres expliquent à sa place, en faux. Blast documente comment les influenceurs d'extrême droite recyclent les argumentaires de l'industrie fossile, comme cette vidéo climatosceptique du Raptor qui recopie Steven Koonin, un ancien directeur scientifique de BP, pendant que la désinformation climatique s'intensifie depuis l'été 2022 d'après les travaux de David Chavalarias. Un public à qui le 20H n'a jamais expliqué les causes est un public désarmé face à ceux qui lui en proposent de fausses.

Le sursaut de 2022, lui, n'était pas venu des rédactions mais de la pression organisée des journalistes signataires, des collectifs citoyens et des observatoires. Et TF1 vient de montrer, en divisant sa couverture par deux sans débat, ce qu'il advient quand la pression retombe.

---

## Conclusion

Delahousse n'a pas tort : son JT parle presque trois fois plus du climat qu'en 2021, s'ouvre dix fois par an sur le sujet, et sa rédaction tient un cap pendant que TF1 recule. Jancovici n'a pas tort non plus : 97,5 % des reportages n'en parlent toujours pas, la part de fond des reportages climat est tombée de 40 % à 15 %, et le lendemain de son passage, le 13H partait pour le Sri Lanka. Les deux ont raison, et c'est bien le problème, car le rattrapage quantitatif a eu lieu pendant que le traitement restait celui que décrivait la sociologie des médias il y a dix ans.

---

## Limites méthodologiques (à lire avant de citer ces chiffres)

- **Détection par mots-clés** sur le titre et le texte des pages web des JT : indicateur de *nommage*, pas d'analyse de contenu.
- **Les mesures lexicales** (émotion, causes, comparaisons thématiques, marqueurs rhétoriques, cartes postales) reposent sur des lexiques publiés dans [les scripts du projet](https://github.com/polomarcus/television-news-analyser/tree/main/scripts). Ordres de grandeur robustes, frontières approximatives ; chaque exemple cité a été vérifié à la main.
- **La classification fine** (angle, intervenants, secteurs, impacts) est produite par LLM, en mono-label pour l'angle. Pilote validé à la main, contrôles d'intégrité, [méthodologie et jeu de données publiés](https://github.com/polomarcus/television-news-analyser/blob/main/docs/data-aggregated-news-json/classification-climat.README.md). Effectifs à quelques unités près selon la date d'extraction (3 448 reportages climat au 14 août 2026). **Validation par juge indépendant** : 98 reportages ré-annotés en aveugle par un modèle plus puissant avec une consigne reformulée : accord de 80 % sur la dichotomie fond/non-fond qui porte le résultat central (54 % sur les 8 catégories, kappa 0,44, désaccords concentrés aux frontières constat/science et constat/adaptation). Surtout, la baisse du fond est confirmée par le juge : 53 % → 25 % sur l'échantillon, contre 47 % → 22 % pour la classification de production.
- Le 37 % de QuotaClimat (mai 2026) provient d'un décompte publié par l'association sur ses réseaux en juin 2026.
- **TF1 depuis 2024** : texte collecté deux fois plus court ; niveaux sous-estimés, non comparables aux années antérieures, comparables entre eux.
- **France 3** : plus collectée depuis le 3 septembre 2023, veille du lancement d'ICI 19/20.
- **France 2, juin-août 2026** : une refonte du site avait cassé la récupération des titres (détection intacte) ; corrigé, données réparées.
- 2026 est une **année partielle** (au 14 août), portée par un été caniculaire.

---

*Données et code : [github.com/polomarcus/television-news-analyser](https://github.com/polomarcus/television-news-analyser). Explorez les 237 000 reportages et la classification fine sur [observatoire.climatmedias.org](https://observatoire.climatmedias.org/annees.html).*
