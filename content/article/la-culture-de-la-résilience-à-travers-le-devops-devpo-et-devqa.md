---
title: 'La culture de la résilience à travers le DevOps, DevPO, et DevQA'
description: 'Revendiquer la polyvalence de nos métiers de développeurs'
date: '2020-10-25T14:23:42.730Z'
thumbnail: "https://cdn-images-1.medium.com/max/800/1*S44E7BO_Ft09Mri7uJ6zRg.jpeg"
---

> **La résilience** peut être définie comme la capacité d’un système à maintenir ou retrouver ses fonctions essentielles lorsqu’il est soumis à une perturbation. — source : [Les Greniers d’abondance](https://resiliencealimentaire.org/definition-de-la-resilience/)

Front, back, data, PO, … La division du travail permet d’être expert sur un sujet mais sans vraiment tout maîtriser. A l’inverse on peut être un peu bon partout sans être expert nulle part, nos amis anglophones utilisent l’expression _“jack of all trades, master of none”_.

En s’attardant trop sur un sujet précis on peut avoir du mal à se comprendre et employer un vocabulaire commun dès lors qu’on travaille en équipe, victime de l’effet bulle, et des malentendus et des aller-retours commencent avec le risque d’être le seul capable d’effectuer certaines opérations.

> [](https://twitter.com/brenankeller/status/1068615953989087232)

_Est-ce que l’on a bien compris le besoin, ce qu’on devra tester, comment ce sera déployé ou l’architecture avant de commencer à coder ?_

### [Yet another](https://fr.wikipedia.org/wiki/Yet_another) article about DevOps

On entend parler de [DevOps](https://fr.wikipedia.org/wiki/Devops) depuis 2010, une éternité dans le numérique, pourtant il reste un terme plutôt flou sur lequel on a du mal à mettre le doigt, à mi-chemin entre utopie et fourre-tout. Wikipédia le définit comme une pratique technique pour **l’unification** entre **développement** logiciel et l’administration des **infrastructures**. Donc, une histoire de collaboration avant une histoire [d’orchestration de conteneurs.](https://kubernetes.io/fr/) C’est bien sûr cela qui vous vient à l’esprit quand on commence à parler DevOps, n’est ce pas ?

![](https://cdn-images-1.medium.com/max/800/1*f0yiWid7EYwO-qOIec_QFw.png)

L’évolution de la recherche “DevOps” : [https://trends.google.com/trends/explore?date=all&geo=PL&q=DevOps](https://trends.google.com/trends/explore?date=all&q=DevOps)

### **Entre travail d’équipe et guerre d’égo**

Certains disent que les métiers du numérique c’est essentiellement travailler en équipe, j’en fais partie, [et j’ai mis longtemps à m’en rendre compte, ébloui par une soif d’apprendre et de vouloir aller toujours plus loin, mais seul.](https://youtu.be/DU-5eDRtjJ4?t=108)

Il y a aussi la crainte de toucher à quelque chose car ce n’est pas [notre technologie de coeur](https://www.jesuisundev.com/la-religion-chez-les-developpeureuses-informatiques/), [ou qu’elle ne servira à rien sur notre CV.](https://tra38.github.io/blog/t16-resume-driven-development.html) Alors que c’est grâce à ça que le produit final et l’équipe avanceraient. Bien entendu, si vous touchez à du PHP 5.6 depuis plusieurs mois il est temps [d’aller voir](https://www.linkedin.com/jobs/search/?) [ailleurs](https://www.welcometothejungle.com/fr/jobs).

Travailler en équipe, c’est aussi accepter de se montrer vulnérable aux autres en disant clairement que l’on ne sait pas tout faire. Quand les guerres d’ego et la politique font rage dans les entreprises et que nos salaires en dépendent, il est compréhensible de ne pas vouloir montrer que l’on est débutant sur telle technologie, qu’on a des points faibles et besoin de ses collègues dans certaines situations pour maximiser ses chances d’avoir une promotion et ainsi augmenter [son capital symbolique](https://fr.wikipedia.org/wiki/Capital_symbolique).

### DevOps — ou se concentrer sur le collectif

Dans une entreprise, nous sommes de la même équipe, pourtant il arrive que l’on se renvoie les erreurs d’un camp à l’autre “_c’est aux ops de faire ça_”, “c_’est la faute aux devs si c’est buggué_”, “_le product owner a mal défini les specs_”, ou mon préféré : le simple “_ça marche pas._” sans contexte et sans que la personne ait la moindre idée du pourquoi.

Quand ces phrases peuvent s’échanger entre les équipes, il est urgent pour les décideurs de l’entreprise de chercher à corriger le tir. En cherchant l’origine de **la culture du blâme**, on pourrait citer les entretiens individuels annuels, où l’on se fera reprocher certaines erreurs si on ne déplace pas la responsabilité vers d’autres, là où des entretiens collectifs auraient beaucoup plus de sens pour amener de la solidarité dans le monde de l’entreprise et réduire l[’individualisme négatif](https://youtu.be/DnHUyRfY3Wc?t=5361). On parle aussi d’augmentation collective pour que ça marche 😉

> La compartimentation dans le travail détermine l’affaiblissement du sens de la solidarité, lequel détermine l’affaiblissement du sens de la responsabilité — Edgar Morin

Ces entretiens collectifs permettraient d’assumer enfin que notre travail, notre projet, est avant tout un travail d’équipe, où chacun apporte. Cela encouragerait aussi **une culture du partage et de la confiance**, où chacun souhaite que les autres progressent avant de vouloir briller seul.

> [](https://twitter.com/ctrlshifti/status/1281046876054097920?s=19)

Un outil comme git est souvent détourné pour devenir l’outil parfait pour reporter la faute sur quelqu’un d’autre 😣 (et je plaide coupable de l’avoir fait…)

### Apprendre à être polyvalent

[Quand la responsabilité passe de l’individu au collectif](https://basecamp.com/shapeup/0.3-chapter-01#making-teams-responsible), le bien-être et la qualité du produit final s’améliorent. Pour cela, chaque personne doit être responsabilisée de A à Z sur la livraison d’un produit, cela va du recueil des besoins au monitoring de l’application une fois livrée. Et la philosophie qu’on connaît le mieux est DevOps, mais ce concept peut aisément être décliné [en DevPO, DevQA](https://labs.tabmo.io/paris-test-conf-1-65fafec0e0c6) pour représenter la polyvalence et la nécessité de collaboration de nos métiers.

#### “C’est aux DevOps de faire ça”

DevOps c’est avant tout casser les silos de l’entreprise : on a beau créer des postes DevOps pour changer les habitudes de notre industrie et mettre de l’agile à toutes les sauces, les silos de spécialité existent toujours. Certains postes avec l’intitulé “DevOps” ressemblent énormément aux administrateurs systèmes à la seule différence que les développeurs disent maintenant “_C’est aux DevOps de faire ça_” plutôt que “_C’est aux administrateurs systèmes de faire ça_” : belle évolution des mentalités 😐

Il est autant du devoir du développeur que de l’ops, de pouvoir automatiser son déploiement tout en garantissant la qualité de son application, sa surveillance et la maîtrise des coûts d’infrastructure.

Hors de question d’utiliser une instance trop puissante (💸), ou pas assez (💥), car ce n’est pas notre domaine d’expertise, analyser le CPU ou la mémoire d’une instance est à la portée de tous. Interdit également de s’apercevoir que l’application est restée hors service pendant plusieurs jours sans avoir reçu d’alerte automatique par email ou par Slack.

#### DevPO, DevQA, DevOps— Revendiquer sa polyvalence

Etonnamment on parle surtout de DevOps depuis 10 ans, [à croire que la norme du devéloppeur est de coder, de s’occuper de l’infrastructure, et de suivre les instructions des tickets Jira définis par les Product Owner — une sorte d’ouvrier moderne.](https://www.usinenouvelle.com/article/developpeurs-et-ouvriers-du-batiment-partagent-la-conscience-professionnelle-de-l-ouvrier-de-metier-explique-benjamin-tainturier.N542734) De mon expérience, c’est lorsque je comprends à 100% le besoin que je fais des projets fabuleux. L’avenir du métier de développeur est dans l’unification de tous les métiers du logiciel : du recueil des besoins jusqu’au monitoring. La gestion de projet ne doit être réservée à des personnes ‘“_retraitées du code_”.

J’ai actuellement une casquette d’expert Kafka, et je dois avouer que si je ne lis pas la documentation tous les 6 mois je deviens aussi novice que le premier des débutants. On peut en conclure qu’au bout de 5 ans sans coder on peut difficilement comprendre la technique, et le dialogue inter-équipe devient forcément problématique, là où la communication est la clé pour le succès des projets...

**Pour le succès de ces derniers, il faut que les développeurs s’approprient le recueil des besoins, la gestion de projet, pour sortir de** [**leur rôle de col bleu**](https://medium.com/france/les-d%C3%A9veloppeurs-sont-devenus-des-cols-bleus-457bd6287631) **et pour améliorer** [**la perception des développeurs en France.**](https://www.jesuisundev.com/comment-considerees-developpeurs-france/)

Sur ce sujet, [Emilien Pecoul](https://medium.com/u/99b656781b81) résume bien la situation avec cette phrase dans son article [“La France gâche son talent numérique”](https://medium.com/@Ouarzy/la-france-g%C3%A2che-son-talent-num%C3%A9rique-9e7a010585e5)

> Tel analyste financier ne comprenant pas pourquoi les États Unis créaient des [GAFAM](https://fr.wikipedia.org/wiki/GAFAM) pendant que nous créons des CapGemini et des Atos.

#### Toyotisme — un équilibre à trouver

Néanmoins, [en allant trop loin dans ce toyotisme](https://fr.wikipedia.org/wiki/Toyotisme#Application_pratique_:_le_syst.C3.A8me_de_production_de_Toyota_.28SPT.29), cet auto contrôle poussé pour ainsi dire, on risque de se culpabiliser de ne pas aller assez loin dans la démarche, de ne pas être excellent partout, et de finir par s’épuiser au travail : [**il n’y a pas meilleur exploiteur que soi-même.**](https://www.youtube.com/watch?v=K9zS0zBYIDc&feature=youtu.be&t=513)

Appliquer tous ces principes de tests, communication, surveillance, l’infrastructure comme code dans un contexte collectif peut paraître clairement intimidant, surtout car on doit livrer rapidement très souvent sans que toutes les problématiques aient bien été pesées — **la culture du sprint dans laquelle nous sommes privilégie la quantité plutôt que la qualité.** Devenir expérimenté.e dans son métier veut dire savoir ralentir les cadences, recentrer les priorités techniques, prendre du temps pour l’architecture technique de l’application, la partager, expliquer les nuances, changer les rituels qui ne marchent plus, mettre en place les tests, l’intégration et les déploiements continus, pour ensuite économiser du temps de façon exponentiel tout le long de la vie de l’application pour le consacrer à l’amélioration du projet et du service client.

#### Facteur vélo — Le danger de la personne clé

Si vous avez déjà passé plus d’une heure sur un projet avec moi, il se peut — et j’en suis désolé — que j’ai pu évoquer 3 fois [le facteur vélo, une déclinaison du facteur d’autobus](https://fr.wikipedia.org/wiki/Facteur_d%27autobus). Si vous n’avez pas la chance de le connaître il s’explique par le fait qu’avec [l’absence d’infrastructure cyclable](http://cartonumerique.blogspot.com/2019/04/cartes-des-pistes-cyclables.html) et [une société accro à la voiture](https://twitter.com/inafr_officiel/status/1187413945507823625), une personne derrière son volant peut me blesser, moi sur mon vélo. Que se passera-t-il si je suis la personne clé d’un projet ? Beaucoup, beaucoup de retard. A moins que l’equipe ait dès le début du projet pensé à partager, automatiser les tests, documenter entre plusieurs personnes. Avoir ce principe en tête lorsqu’on est sur un projet permet de partir en vacances serein, d’avoir moins de problèmes en astreintes, car nous avons confiance en nos collègues pour gérer toutes les situations. Cela construit une réelle coopération, bref je ne peux que vous le conseiller— ainsi que [de rouler à vélo](https://www.velo.qc.ca/boite-a-outils/vaincre-les-prejuges/).

### Une culture de la résilience

Quand une culture de la résilience basée sur l’automatisation et le partage est créée, les erreurs humaines sont réduites et **l’entraide et la confiance** commencent à être naturelles. Cette culture permet d’assurer une meilleure disponibilité de la plateforme pour répondre au service attendu par les clients et au meilleur coût.

Dans ces conditions, l’accueil des nouveaux est aussi facilité : des documentations à jour, moins de procédures orales grâce à l’automatisation et [des outils comme Docker et Docker Compose](https://labs.tabmo.io/simplify-your-tests-and-development-with-docker-and-docker-compose-d3d55fe70de) pour automatiser le lancement des stacks.

![](https://cdn-images-1.medium.com/max/800/1*S44E7BO_Ft09Mri7uJ6zRg.jpeg)

La culture de la résilience, ou celle du [roseau](https://open.spotify.com/track/0hgO48TplQchSVuBrqZeML?si=vkV_plZdRo6XOxJ3aNj_4g) (credit [unsplash](https://unsplash.com/photos/5paRSKtn6rc))

#### Les reverts de l’excellence technique

Les capacités à s’entraider peuvent être négligées au prix d’expertises techniques et d’exploits individuels appréciés par certains chefs d’entreprises responsables de nos primes et de nos augmentations. Il est souvent plus facile de remarquer les exploits d’une personne plutôt que quelqu’un qui met en avant l’équipe. Avec ceci, c’est la culture du [Stakhanovisme](https://fr.wikipedia.org/wiki/Stakhanovisme) qui s’installe, à base de [développeurs rockstars](https://www.jesuisundev.com/tu-nes-pas-un-developpeur-rockstar/).

Ces personnes peuvent plomber l’ambiance et la productivité d’une équipe à trop vouloir briller seules sans se soucier de qui passera derrière elles. Un manque de respect peut aussi apparaître envers les membres de l’équipe en allant jusqu’au [harcèlement : quand on est le seul à connaître comment fonctionne un projet on se sent vite protégé par un statut d’intouchable.](https://www.lesechos.fr/tech-medias/hightech/ubisoft-le-numero-deux-debarque-a-la-suite-daccusations-de-harcelement-sexuel-1223175)

Pourtant, [l’entraide est un facteur d’innovation chez le vivant](https://fr.wikipedia.org/wiki/L%27Entraide,_un_facteur_de_l%27%C3%A9volution) dans son [évolution depuis 3.8 milliards d’années](https://www.placedeslibraires.fr/livre/9791020907004-l-entraide-l-autre-loi-de-la-jungle-pablo-servigne-gauthier-chapelle/), la nature nous apprend que seuls [les plus coopératifs](https://fr.wikipedia.org/wiki/Homo_sapiens#Soci%C3%A9t%C3%A9,_gouvernement_et_politique) survivent, mise à part quelques exceptions comme les [Tardigrade](https://fr.wikipedia.org/wiki/Tardigrada) — un nom alternatif pour les développeurs rockstars ?

Bien sûr, il faut savoir trouver l’équilibre entre performances individuelles et collectives, il y aura toujours des meneurs dans les équipes — qui doivent apprendre à parfois s’effacer pour voir les autres évoluer — et il faut aussi savoir se remettre, ou l’organisation, en question si on passe plusieurs longues réunions ou rituels à être passif.

[Les directeurs](https://twitter.com/jaykreps/status/1310810903617482755) et managers qui suivent ce principe rendent leur entreprise résiliente dans les pires crises et s’assurent de longues carrières ou du moins se construisent un réseau fiable de personnes qui souhaitent travailler avec elles.

#### Le dilemme du prisonnier — ou, encore une bonne raison de travailler de façon coopérative

Pour nous aider à enfoncer le clou sur la collaboration, on peut citer les sciences sociales avec la [théorie des jeux](https://ncase.me/trust/) et [le dilemme du prisonnier](https://fr.wikipedia.org/wiki/Dilemme_du_prisonnier). Ce dilemme, [cité dans plus de 5 000 articles scientifiques](https://fr.wikipedia.org/wiki/Robert_Axelrod), nous explique que des acteurs en concurrence sur une longue période, nos chers Stakhanovs — ou Tardigrades, choisissent toujours la pire solution, alors que ceux collaboratifs arrivent à la meilleure. En bref, **le collectif est plus efficace que l’individualisme.**

Dire cela peut paraître naïf, simpliste voir utopiste, mais on a tendance à oublier à quel point notre société est coopérative à travers le bénévolat, le don, et tous les gestes gratuits du quotidien. Même dans des temps extrêmement durs, la guerre de tranchées 14–18 a mis en lumière la coopération. Certains soldats _ennemis_ appliquaient le principe de “laissez vivre pour vivre”, [notamment à Noël ou lors des ravitaillements.](https://fr.wikipedia.org/wiki/Tr%C3%AAve_de_No%C3%ABl)

**La coopération devrait être à notre portée nous qui sommes tranquillement installés à nos bureaux.**

[![](https://cdn-images-1.medium.com/max/800/1*uARYuC5OeRgic9CnY4iv3A.png)](https://ncase.me/trust/)

Pour mettre en pratique ce principe vous pouvez jouer à la théorie des jeux ici (durée 30 minutes) : [https://ncase.me/trust/](https://ncase.me/trust/)

#### **Par où on commence ?**

Reconnaître la présence de silos de développeurs, testeurs, ops, product owner… pour mieux les casser est la première étape pour créer une culture de collaboration et de la résilience. Demander à l’autre qu’est ce qu’il trouve compliqué ou mystérieux dans notre équipe, lui expliquer de la manière que [l’on aurait aimé entendre lorsqu’on a commencé notre spécialité](https://dev.to/paulleclercq/what-i-like-about-data-engineering-2hhe), et citer les sources qui nous ont aidées à y voir plus clair.

**J’aime revendiquer que mes compétences ont été acquises grâce à d’autres, et que je suis redevable de transmettre leur savoir.** Je ne serais pas le même ingénieur si je n’avais pas connu [Martin Kleppman](https://dataintensive.net/) et [ses travaux](https://martin.kleppmann.com/2015/05/11/please-stop-calling-databases-cp-or-ap.html), [Jepsen](https://jepsen.io/), certains collègues que j’ai côtoyés ou que je côtoie toujours, ou tant d’anonymes sur Stackoverflow et ailleurs. La citation qui suit illustre tout cela:

> [Des nains sur des épaules de géants](https://fr.wikipedia.org/wiki/Des_nains_sur_des_%C3%A9paules_de_g%C3%A9ants) — Bernard de Chartres

La seconde étape doit venir des experts et de la direction de l’entreprise, ces personnes doivent **montrer l’exemple, communiquer** et dire qu’ils ne savent pas tout. En posant des questions sur des channels publiques ou en réunion, en répondant aux questions en citant un maximum de sources pour montrer leurs méthodes de recherche, et en indiquant les endroits dans le code où la compréhension est difficile pour eux. Il faut aussi pousser pour que le potentiel de chacun puisse grandir en responsabilisant du recueil des besoins au monitoring, en s’effaçant, en laissant l’autre faire, mais être là en soutien si un blocage perdure.

> Dans un échange intellectuel, celui qui donne ne perd rien et celui qui reçoit prend mais ne dépossède pas son interlocuteur. — Bernard Maris

La troisième étape dépendra de votre maturité **DevOps**, qui faura faire évoluer vers du **DevPO et DevQA** pour avoir de la polyvalence dans les équipes.

### Donnant, donnant

Il sera considérable pour les experts, surtout en période de crise, de ne pas à avoir à porter seuls le poids de leur spécialité en pouvant compter sur d’autres. Ces autres qui étaient peut-être totalement novices sur leur techno 3 mois avant.

Du côté de l’équipe, elle pourra devenir résiliente, **elle saura demander de l’aide plus facilement**, le savoir sera mieux diffusé, la rivalité et le stress seront réduits ainsi que les futures erreurs liées à celui-ci, et le plus important notre bien-être au travail sera amélioré.

Enfin, la dernière étape dépendra de votre culture d’entreprise et de v[otre vision de l’agilité](https://twitter.com/lascardev/status/883337046231846912), mais [il n’y aura jamais de recettes miracles](https://www.jeremiahlee.com/posts/failed-squad-goals/) d’organisation. Cependant, le bien-être, [**avec l’instauration**](https://www.lefigaro.fr/societes/microsoft-teste-la-semaine-de-4-jours-au-japon-20191105) [**de la semaine de**](https://www.lemonde.fr/emploi/article/2020/07/08/en-france-ldlc-est-conquis-par-la-semaine-de-quatre-jours_6045558_1698637.html) [**4 jours par exemple**](https://madame.lefigaro.fr/business/travailler-4-jours-en-etant-paye-5-cest-possible-070220-179540)**,** semble être un excellent levier à utiliser en tant que décideur pour augmenter la productivité de l’entreprise.

