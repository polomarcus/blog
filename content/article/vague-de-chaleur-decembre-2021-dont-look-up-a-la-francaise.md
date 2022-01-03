---
title: "Chaleur de décembre : 'Don't Look Up' version Française ?"
draft: false
description: "Analyse des JTs regardés par 10 millions de personnes chaque soir. Le journal télé est la fin d’un téléphone arabe dont vous ne connaissez ni le nombre de maillons intermédiaires, ni la qualité de transmission entre chaque maillon"
date: 2022-01-03T08:50:07+02:00
thumbnail: "images/dontlookup/dont-look.png"
images:
    - "images/dontlookup/dont-look.png"
---

["Don't Look Up"](https://www.theguardian.com/commentisfree/2021/dec/29/climate-scientist-dont-look-up-madness) a été ma surprise de la fin d'année, et ça a réveillé en moi à quel point on regarde ailleurs dès qu'on a un sujet de fond.
C'est un film parodique sur le traitement de l'information sur le changement climatique et sur les ~~héros~~ **fous volants de l'ultra capitalisme** comme Musk, Branson, et Bezos. Ils nous promettent - avec le sourire - que [la technologie **seule**](https://www.socialter.fr/article/mars-la-morte) sera notre sauveuse et donc qu'il n'y a pas de raison de changer nos modes de vie carbonées et [non respectueuse du vivant](https://ipbes.net/sites/default/files/2021-06/20210609_workshop_report_embargo_3pm_CEST_10_june_0.pdf).

Il y a eu fin décembre 2021 des records de température dans tout le sud de l'Europe. Suite à cela, je me suis demandé si l'information diffusée **à des millions de personnes** dans les JTs de TF1 et France 2 était traitée plus ou moins comme dans le film : un fait divers de plus perdu dans un océan d'infobésité.

{{< twitter_simple 1477651622201282560 >}}

## Avant propos : les faits de sources sûres
Des nouveaux records de températures ont été établis dans plusieurs villes :
> Il s'agit bien de la semaine entre Noël & le nouvel an la plus douce jamais enregistrée depuis 1947. - [Source Météo France](https://twitter.com/meteofrance/status/1476910557634732079)

Et c'est une tendance de fond de plus en plus fréquente :

> Parmi les 20 périodes en fin d’années les plus douces à l’échelle de la France depuis 1947 (24 au 31 décembre), on dénombre huit années appartenant au 21e siècle: 2002, 2015, 2012, 2013, 2017, 2009, 2019 et 2021 [source Météo-France.](https://twitter.com/meteofrance/status/1475793593860304897)

Lors du rapport du groupe 1 du GIEC de 2021, l'augmentation des extrêmes de chaleur liée au changement climatique venant de la consommation d'énergies fossiles des Hommes est claire :

> A.3.1 Il est pratiquement certain que les canicules (y compris les vagues de chaleurs) sont devenues plus fréquentes et plus intenses à travers la plupart des régions continentales depuis les années 1950 - [Source Résumé pour décideurs GIEC 2021](https://resumegiec.wordpress.com/2021/08/11/rapport-du-giec-resume-pour-les-decideurs/)

{{< figure alt="Augmentation des vagues de chaleur liées aux activités humaines fossiles" src="/blog/images/dontlookup/giec_resume_decideurs_temperature.png" title="Augmentation des vagues de chaleur liées aux activités humaines fossiles - source GIEC SPM-12" >}}

## Méthodologie
J'avais déjà fait l'exercice sociologique de regarder certains JTs, mais je n'avais pas continué l'expérience longtemps car cela prend du temps et que j'aurais certainement fini en convalescence. J'ai remercié 1000 fois [l'équipe d'Arret sur Images d'avoir fait cette expérience pendant **36 heures** pour la sortie du rapport du groupe 1 du GIEC cet été : résultat moins d'une heure cumulée sur le sujet...](https://www.arretsurimages.net/articles/climat-bfmtv-et-cnews-regardent-ailleurs)

 > Notre maison brûle, et nous regardons Messi arriver au PSG - [BonPote](https://bonpote.com/comment-les-medias-politiques-et-lobbies-ont-accueilli-le-rapport-du-giec/)

J'ai regardé les 3 jours de reportages sur les sites des JTs de TF1 et France 2 citant la vague de chaleur. On remarque en général que ces reportages sont placés après la moitié des JTs, après 15 minutes, en général de COVID, sur 25 minutes de durée totale. Loin de faire la une, donc.

Vous pouvez voir par vous même la source pour [France 2 ici](https://www.francetvinfo.fr/replay-jt/france-2/20-heures/jt-de-20h-du-mardi-28-decembre-2021_4873339.html) et [TF1 là en cliquant sur "extraits"](https://www.tf1.fr/tf1/jt-20h/videos/le-20-heures-du-29-decembre-2021-37902016.html) pour faire vos propres analyses sur différents sujets.

*Les textes des reportages sont écrits, ça m'a donné l'idée d'automatiser avec un scrapper et de faire une analyse par mot clé avec un peu de code. La suite j'espère pour bientôt.*

## Quand les JTs en parlent, sans en parler
Voici des citations extraites des reportages de 1 min 30 à 2 min 20, où on ne parle pas une fois **du changement climatique.** Quand le problème climatique n'existe pas, on comprend qu'il est facile pour [la chef adjoint spécialisée en science de TF1 d'être fan du tourisme spacial et de Richard Branson](https://www.linkedin.com/in/christine-chapel-38621999/?originalSubdomain=fr)

> On a une chance exceptionnelle de s'installer en terrasse - [JT du 20h de TF1, 27 décembre 2021](https://www.tf1.fr/tf1/jt-20h/videos/temperatures-une-fin-dannee-exceptionnellement-douce-84415115.html)

Mon extrait préféré : 
> Avec cette douceur, on trinque comme en été : au rosé - [JT du 20h de TF1, 29 décembre 2021](https://www.tf1.fr/tf1/jt-20h/videos/22-degres-en-decembre-des-records-de-douceur-27070617.html)

{{< figure alt="Deux personnes trinquant au rosé en terrasse un 31 décembre" src="/blog/images/dontlookup/rosé.png" title="Santé !" >}}

> Des températures largement positives, et de la pluie : à 2 000 mètres d’altitude en Savoie, la douceur est remarquable. - [JT du 20h de France 2, 29 décembre 2021](https://www.francetvinfo.fr/meteo/montagne-des-conditions-meteo-delicates-sur-les-pistes-de-ski-tres-frequentees_4897963.html)

> La douceur estivale profite aux commerçants de Biarritz - [JT du 13h de France 2, 30 décembre 2021](https://www.francetvinfo.fr/meteo/meteo-la-douceur-estivale-profite-aux-commercants-de-biarritz_4898879.html)

{{< figure alt="Une personne buvant un café et un jus d'orange" src="/blog/images/dontlookup/cafe.png" title="'Il va faire 22 cette après midi : c'est toppisme !'" >}}


> Le glacier se frotte les mains - [JT du 20h de France 2, 30 décembre 2021](https://www.francetvinfo.fr/meteo/meteo-des-temperatures-printanieres-pour-les-vacanciers-d-hiver_4899073.html)

{{< figure alt="Un glacier vendant des glaces un 31 décembre" src="/blog/images/dontlookup/glacier.png" title="'Le glacier se frotte les mains'" >}}

> On est en t-shirt c'est très très très agréable - [JT de 20h TF1, 30 décembre 2021](https://www.tf1.fr/tf1/jt-20h/videos/temperatures-record-une-canicule-dhiver-61808760.html)

{{< figure alt="Une personne en camping en maillot en décembre" src="/blog/images/dontlookup/camping.png" title="'Il fait bon, là !'" >}}

A noter dans ce reportage de TF1 qu'une femme **est inquiète des température**, mais les journalistes ont préféré rebondir avec cette phrase comme [dans cette scène du film](https://www.youtube.com/watch?v=RiJdBAOtL5Y) où les scientifiques annoncent une nouvelle bouleversante pour l'humanité et que les journalistes passent sans transition vers un nouveau médicament :
> Et en terrasse, on est nombreux à en profiter - [JT de 20h TF1, 30 décembre 2021](https://www.tf1.fr/tf1/jt-20h/videos/temperatures-record-une-canicule-dhiver-61808760.html)

## Quand les JTs en parlent vraiment, enfin presque
[Ce reportage du 28 décembre](https://www.francetvinfo.fr/meteo/climat/meteo-des-temperatures-printanieres-en-plein-hiver_4896927.html) de France 2 du JT de 20h interview le météorologue Jean Yves Choplin. Il nous avertit dans un court passage sur l'augmentation des fréquences des vagues de chaleur, cela devrait être développé pendant au moins tout le reportage mais son expertise a le même poids que les restaurateurs :
> Ce genre de phénomènes sera de plus en plus fréquent à l'avenir. - Jean Yves Choplin

Sur ce, la voix off enchaîne telle une séquence du "Zapping" de Patrick Menay :
> Sur la côté basque où le mécure approche les 20 degré, les restaurateurs se frottent les mains. 

Même la restauratrice a droit à son témoignage :
> On a eu beaucoup de monde pour les crèpes, les gauffres...

{{< figure alt="Une partie de pétanque en décembre" src="/blog/images/dontlookup/petanque.png" title="'Les amateurs de pétanque vont pouvoir en profiter'" >}}

Ce même prévisionniste de Météo France a été interviewé par les journalistes de TF1, le problème reste le même, lorsque Jean Yves Choplin parle de la variabilité de la météo et qu'il enchaîne avec le problème de l'augmentation des fréquences sans que la cause ne soit citée... ([voir à 0:50 de ce JT de TF1 du 28 décembre 2021](https://www.tf1.fr/tf1/jt-20h/videos/climat-lhiver-de-tous-les-extremes-12707249.html)). Enfin la cause a le mérite d'être cité seulement par TF1, mais c'est à la fin du reportage et **avec moins de temps de parole que les skieurs qui sont sous la pluie.** Cela donne l'impression que le réchauffement climatique vient d'une source [magique, inconnue et qu'on est impuissant pour le combattre](https://polomarcus.github.io/blog/article/r%C3%A9sum%C3%A9-du-resum%C3%A9-ar6-sud-france/) : 

> En Arctique, le réchauffement climatique est 3 fois plus rapide que dans le reste du monde. - [JT du 20h de TF1, 28 décembre 2021](https://www.tf1.fr/tf1/jt-20h/videos/climat-lhiver-de-tous-les-extremes-12707249.html)

{{< figure alt="La fonte de la banquise et les températures extrêmes au Groenland" src="/blog/images/dontlookup/groenland.png" title="9 secondes sur le réchauffement climatique" >}}


[Au 13h de France 2 du 30 décembre](https://www.francetvinfo.fr/meteo/climat/meteo-des-temperatures-tres-douces-pour-la-derniere-semaine-de-l-annee-2021_4898877.html), nous avons droit à 1min30 (noter la durée) sur le sujet, **mais sans évoquer l'augmentation des fréquences liée au changement climatique.** 
Apparement, la courte intervion de Jean Yves Choplin 2 jours avant n'a pas marqué les journalistes qui ont préparé le sujet. Chloé Nabédian, celle qui présente ce sujet, est ["journaliste spécialisée sur l'environnement et le climat" et a déjà couvert la COP21](https://fr.wikipedia.org/wiki/Chlo%C3%A9_Nab%C3%A9dian). Elle avait parlé du changement climatique pour le même genre de sujet dans [un JT de France 2 en 2016](https://www.youtube.com/watch?v=rhqtw4EUCUQ). Pourquoi une personne compétente sur le sujet n'en parle tout simplement pas : Limite de temps ? Excuses des vacances de Noël ? Le manque de régularité pose questions.

{{< figure alt="La fonte de la banquise et les températures extrêmes au Groenland" src="/blog/images/dontlookup/2016.png" title="Dans ce reportage de 2016 par la même journaliste, le constat était clair" >}}

## Sur la télévision
Ceux qui ont suivi les cours des Mines ont pu être marqués par [comment apprécier le traitement d'une information par les médias.](https://youtu.be/PEY6LmscKc4?t=4963) En quelques mots, on vit dans un monde avec l'information imparfaite **où le nouveau passe devant l'important.**

> Le journal est la fin d'un téléphone arabe dont vous ne connaissez ni le nombre de maillons intermédiaires, ni la qualité de transmission entre chaque maillon - [Cours des Mines 5 - Jancovici](https://youtu.be/PEY6LmscKc4?t=5425)

La chose également inquiétante est qu'un JT a également plusieurs millions de personnes, on parle d'environ 10 millions en tout pour TF1 et France 2, qui l'écoutent tous les soirs alors [qu'une experte du style de Marie Currie](https://twitter.com/valmasdel/status/1475133934803591168) aura rarement cette audience totalisée **durant toute sa carrière.**

Dans un reportage, **sous couvert de neutralité**, on ne dira pas pourquoi on a interviewé ce monsieur plutôt qu'un autre, pourquoi on a traité ce sujet, plutôt qu'un autre. Et pour un reportage "long" de 2 minutes où on va voir une ou 2 personnes parler, le temps d'interview pour ces 2 personnes est de 30 minutes pour chaque personne pour seulement 20 secondes d'antenne. Et la personne interviewée ne décidera pas ce qu'il considère être important et ce qui passera à la télé, et s'il pourra vérifier avant que ça soit publié.

### Les coupures au montage
J'en ai moi même fait l'amer expérience pour [un reportage sur les "coronapistes cyclables" avec France 2](https://www.francetvinfo.fr/sante/maladie/coronavirus/mobilite-les-villes-face-au-casse-tete-des-pistes-cyclables_3998451.html?fbclid=IwAR2O4fLbI1AGx77LS6qWMYdl51_cbXDHZOJGvRawHvWj6Sn2U7B6e1ZjJOY), où pour 45 minutes d'interview dans plusieurs coins de Marseille, j'avais repété plusieurs fois ma punchline préparée sur la sécurité des enfants, mais j'avais eu droit au final à 6 secondes de parole tronquée, et 20 secondes où on me voyait faire du vélo

> Cette piste cyclable, c'est juste un trait de peinture et c'est insuffisant [coupé au montage]pour qu'un enfant puisse rouler dessus en autonomie et en sécurité[/coupé au montage] et ça laisse libre accès aux voitures pour s'y garer

Je n'en ai pas voulu aux 2 journalistes qui m'ont interviewé, et avec qui les échanges étaient très cordiaux, l'un m'avait même demandé des conseils pour acheter un vélo et on avait échangé ensuite sur ça par texto, et je l'avais remercié pour la beauté de certains plans. Mais **c'est une remarque systémique au métier**, que Pierre Bourdieu a décrit dans ["Sur la télévision"](https://www.youtube.com/watch?v=TixuLxKht2g)

> En remplissant ce temps rare avec du rien, ou avec du vide, on écarte les informations pertinentes que les citoyens devraient posséder pour exercer ses droits démocratiques. (...) Paradoxalement on peut cacher en montrant autre chose.

Si je parle de ça, c'est que Jean Yves Choplin, le prévisionniste à Météo France interviewé par [TF1](https://www.tf1.fr/tf1/jt-20h/videos/climat-lhiver-de-tous-les-extremes-12707249.html) et France 2, a forcément parlé du changement climatique pour justifier son argument de l'augmentation des fréquences comme l'ont fait d'autres collègues comme Christine Berne qui explique à l'AFP que **["ces vagues de douceur en hiver sont le marqueur du changement climatique"](https://www.francesoir.fr/afp-afp-france/meteo-2021-se-cloture-sur-un-record-de-douceur)**. 

Ce passage sur le changement climatique a a été coupé au montage **et cela enlève tout la substance à son intervention.** Surtout qu'il avait déjà pu justifier du changement climatique dans d'autres interventions comme [sur FranceInfo lors d'une des canicules de 2020](https://twitter.com/franceinfoplus/status/1288746537691086851)

## Conclusion
Cette vague de chaleur traitée comme un fait décorrélé [du plus grand défi de l'humanité](https://www.youtube.com/watch?v=tk-QuMCbw2I), montre à quel point nous sommes loins d'être prêts à affronter [le changement climatique déjà en cours](https://bonpote.com/les-10-photos-qui-ont-marque-lannee-2021/) et des solutions pour le combattre : [-5% des émissions de gaz à effet de serre par an pendant 30 ans.](https://datagir.ademe.fr/blog/budget-empreinte-carbone-c-est-quoi/) **C’est une économie de guerre.**

Cette absence de raison dans les médias, qui sont à la base de nos démocraties, doit nous faire questionner la qualité de l'information pour l'améliorer à l'image des travaux de [Julia Cagé](https://www.francetvinfo.fr/economie/medias/medias-jamais-on-a-vu-autant-de-coups-portes-contre-l-independance-des-journalistes-selon-julia-cage_4300265.html), [Gilles Raveaud](https://mobile.twitter.com/RaveaudGilles/status/1428300795565518849), [Sophie Eustache](https://www.placedeslibraires.fr/livre/9782354802073-batonner-comment-l-argent-a-detruit-le-journalisme-sophie-eustache/), ou [d'Acrimed](https://www.acrimed.org/IMG/png/carte17_2hd.png). Soutenir les medias (indépendants) comme [BonPote](https://bonpote.com/soutenir-bon-pote/), [Le Réveilleur](https://www.utip.io/lereveilleur/tip), [Mediapart](https://abo.mediapart.fr/abonnement/decouverte), [Blast](https://www.blast-info.fr/soutenir)... alors que nous sommes habitués à ne pas payer pour ça. Et pour tout ceux qui ne peuvent pas payer pour ça mettre en place des garde-fous pour que les normes puissent être respectées dans les médias privés ou publics : [garantir un nombre minimum de journalistes](https://www.lesechos.fr/tech-medias/medias/la-redaction-de-science-vie-se-vide-de-ses-journalistes-1302865) dans les rédactions, inviter d'autres personnes sur les plateaux [mêmes ceux qui ont du mal devant une caméra](https://www.youtube.com/watch?v=RiJdBAOtL5Y), interroger le modèle economique des médias, la course à l'audience, garantir que l'indépendance du travail des journalistes ne soit pas (auto-)censuré par les rédactions ou [les milliardaires qui les rachètent](https://www.lemonde.fr/economie/article/2021/06/30/des-salaries-d-europe-1-manifestent-contre-l-emprise-croissante-de-vincent-bollore-dans-les-medias_6086396_3234.html) et dont [9 d'entre eux possèdent 90% de l'audience en France](https://www.youtube.com/watch?v=41lAe0mgjjU) - sans que le public en ait conscience - qui [n'ont pas d'intêret à ce que les choses changent.](https://youtu.be/Vjkq8V5rVy0?t=3672)

> Nous appelons enfin les enfants, les jeunes, les parents, les anciens et les grands-parents, les éducateurs, les autorités publiques, à une véritable insurrection pacifique contre les moyens de communication de masse qui ne proposent comme horizon pour notre jeunesse que la consommation marchande, le mépris des plus faibles et de la culture, l’amnésie généralisée et la compétition à outrance de tous contre tous. - [Appel des résistants (2004)](https://www.acrimed.org/Un-appel-de-resistants) - **Raymond et Lucie Aubrac, et les résistants de de la France Libre (1940-1945)**

> La curiosité de l'habitant des démocraties est tout a la fois insatiable et satisfaite à peu de frais ; car il tient à savoir vite beaucoup, plutôt qu'à bien savoir.
Il n'a guère le temps, et il perd bientôt le goût d'approfondir.
Ainsi donc, les peuples démocratiques sont graves, parce que leur état social et politique les porte sans cesse à s'occuper de choses sérieuses ; et ils agissent inconsidérablement, parce qu'ils ne donnent que peu de temps et d'attention à chacune de ces choses. L'habitude de l'inattention doit être considérée comme le plus grand vice de l'esprit démocratique. - **Alexis de Tocqueville "De la démocratie en Amérique" (1835)**