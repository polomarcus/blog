---
title: 'Paris test conf #1'
description: 'Je développe, donc je teste'
date: '2019-11-25T14:23:42.730Z'
categories: []
keywords: []
slug: /@polomarcus/paris-test-conf-1-65fafec0e0c6
---

[Une première édition](https://paristestconf.com/programme/) où toutes les places ont été vendues, le test intéresse, certains diront passionne. Indispensable pour notre industrie logiciel en manque de stabilité, il est néanmoins bâclé ou oublié par une belle partie de notre industrie à raison de fausses excuses de rapidité ou un manque d’habitude. A ne pas tester on le paye toujours plus tard, **souvent lorsqu’on veut être capable de passer à l’échelle.**

![](https://cdn-images-1.medium.com/max/800/0*yvIjy8Skpa1IcDXi)

#### Le test, c’est du dev

Jean Pierre Lambert qui anime [Scrum Life](https://www.youtube.com/channel/UCMCnZGIOeLVO65-LBxkkHyQ) nous le dit si bien

> On ne part pas en dev tant qu’on ne sait pas comment le tester

Ne pas prévoir comment on va tester une tâche c’est prendre le risque de la revoir apparaître dans le backlog une semaine après lorsqu’on sera passé à autre chose en ayant oublié la plupart des détails 😬

J’ai souvent fait et vu un tableau SCRUM avec une colonne TEST juste avant celle de DONE. [Thomas Lelong](https://www.linkedin.com/in/thomas-lelong-47109b85/), ingénieur quality & assurance chez back market, nous fait part de son expérience de faire un “shift left” sur la colonne des tests dans notre tableau SCRUM pour la placer ou l’incorporer directement dans la colonne du développement.

_Selon moi_, le risque en ayant une équipe de test détachée de l’équipe de dev, ou que la tâche soit faite après l’étape de développement, c’est une **dé-responsabilisation de l’équipe de développeurs sur le produit final, qui aboutira sur le long terme à des bugs** et des délais plus long pour mettre en production, avec plusieurs aller-retours qui peuvent mettre en péril la cohésion des équipes.

#### Tester, c’est une vraie compétence

[Stéphane Colson](https://twitter.com/s_colson) nous a montré 6 exemples d’erreurs monumentales faite par les GAFAM. Malgré leur tests poussés (ou non 😅) il peut toujours y avoir une erreur, le but étant d’ajouter de plus en plus de couche de tests pour les éviter.

![](https://cdn-images-1.medium.com/max/800/0*DdDfsegk3u9bmMBP)

Kevin Roulleau, nous a présenté les tests bout à bout mobiles iOS et Android chez Happn avec [Appium](http://appium.io/) et [Cucumber](http://cucumber) pour s’assurer de la qualité de leur app. Ils monitorent les temps d’exécution pour s’assurer des performances et pour tester sur de nombreux appareils sans devoir en acheter et les maintenir à jour, ils utilisent les services de [Sauce Labs](https://saucelabs.com/).

#### Le vocabulaire du test

Le _Behaviour Driven Development_ pour écrire nos scénarios de tests accessibles à tous avec les mots de [la syntaxe Gherkin](http://agileutile.fr/outils/gherkin-tests-acceptance/):

*   **Étant donné que** (une situation de départ)
*   **Et** (des précisions)
*   **Quand** (une action)
*   **Et** (des précisions)
*   **Alors** (une conséquence ou situation d’arrivée)

Les [**tests exploratoires**](https://latavernedutesteur.fr/2017/11/03/les-tests-exploratoires/) : tester la plateforme de la façon la plus bizarre que vous puissiez, qui résulte en général à la découverte de bug 😁 Pour ne pas s’y perdre, on peut s’aider de cette syntaxe:

> explore \_\_\_ with \_\_\_ to discover \_\_\_

Les [**sanity tests**](https://en.wikipedia.org/wiki/Sanity_check) cherchent si les bugs ou la fonctionnalité marchent bien lors des mises en production, à travers un humain testant manuellement les nouveautés livrées : c’est le sommet dans la hiérarchie de la pyramide des tests car ils peuvent prendre du temps.

A l’inverse, les tests unitaires qui sont situés à la base de la pyramide sont rapides à coder (ou alors c’est un signe que nous devons refactorer notre code 😜), ils sont aussi idéaux pour trouver des erreurs, refactorer avec plus sérénité, mais aussi documenter notre code. Ils devraient être présents à presque tous les endroits de notre app.

Les tests d’intégration permettent de tester plusieurs systèmes entre eux, ils sont réputés pour planter pour aucune raison logique (comprendre : cache, concurrence, 3rd party, …) une fois sur 3, et pour être durs à maintenir. Cependant, ils permettent de gagner en confiance lors des mises en production et grâce à eux on peut franchir l’étape de déploiement continu avec plus d’aisance.

![](https://cdn-images-1.medium.com/max/800/0*46PPoSKGnR1iJmD5)

#### Des visions différentes

J’ai entendu pour la première fois le terme automaticien pour parler de testeur. Ce mot est employé pour différencier les différents types de testeurs, certains plus orientés métier et d’autres plus techniques. Selon moi, ces derniers sont des développeurs qui s’ignorent 😛

A la manière du mouvement DevOps, qui rapproche dev et ops, je n’ai pas pu m’empêcher de penser à lancer le mouvement **DevQA**, _il doit certainement exister d’ailleurs je suis curieux d’apprendre son nom_ 😁 Une équipe experte en test qui met en place les outils et s’occupe de la diffusion des bonnes pratiques parmi les équipes de développement. Cette équipe aiderait ponctuellement les développeurs à tester leur code, car progressivement les développeurs deviendraient indépendants sur les tests.

#### Docker chez les testeurs

[Arnaud Bailly](http://drcode.io) et moi avons parlé Docker 😬 Cette technologie peut nous aider à tester et développer plus efficacement : faciliter l’accès à n’importe quel projet en pouvant le lancer avec une ligne de commande, nous évite d’être fainéant pour tester nos montées de versions de bases de données, et nous permet même de simuler des coupures réseaux pour tester la résilience de nos apps.

La conférence a pu paraître très technique, on est convaincu que cette technologie, qui peut faire peur au démarrage, peut amener un changement de mentalité nécessaire à nos organisations en y ajoutant plus de collaboration, et ça, du product owner au data engineer.

#### L’agilité chez les managers

Bertrand Foucault nous parle d’avoir un prisme de l’intention positive : chaque résultat a été fait du mieux qu’on pouvait avec l’information dont on disposait, d’accepter que le modèle du monde de chacun est différent, et qu’on a tous en nous les moyens de franchir les obstacles.

#### Mot de la fin

Il faut responsabiliser les développeurs à la production, et ça passe par acquérir un savoir faire métier mais aussi un savoir faire de testeur pour casser les frontières entre le monde du dev et du test : #DevQA 😁. En comprenant les forces et les faiblesses d’un produit qu’on développe, on devient plus efficace pour coder, tester et déployer et on contribue activement à la réussite du produit.
