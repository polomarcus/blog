---
title: Un an de télétravail chez TabMo
description: >-
  Mon retour d’expérience sur l’importance de la communication et de la
  transparence
date: '2019-07-02T07:40:46.479Z'
categories: []
keywords: []
slug: /@polomarcus/un-an-de-t%C3%A9l%C3%A9travail-chez-tabmo-e477fc1e8e3a
---

Trouver son rythme et ses manières de communiquer pour s’épanouir en travaillant à distance.

On est tous différent, ce qui fait notre force (🌈). Parmis nos amis, certains préfèrent les textos, d’autres les appels. On apprend ça avec le temps. C’est pareil au travail, et quand on est amené à travailler avec plusieurs personnes, il faut savoir s’adapter, quitte à s’effacer parfois, lorsque cela demande trop d’énergie.

### Trouver son rythme

J’ai été marqué par la découverte du [“Bus factor”](https://en.wikipedia.org/wiki/Bus_factor), ou plutôt du “[facteur risque vélo” comme on l’appelle à Montpellier](http://www.jesuisundesdeux.org/) ou ailleurs, et par la croissance folle de ma première start up qui a connu les défis de montée de charge.

Le principe du “bus factor” c’est d’éviter d’avoir **des personnes clés** avec toute la connaissance des projets, — je ne parle pas [de développeur rockstar — ,](https://www.jesuisundev.com/tu-nes-pas-un-developpeur-rockstar/) mais de personnes responsables de projets qui **ne prennent pas le temps, n’ont pas le réflexe, ou la culture** d’écrire des readme de qualité, de pousser la **qualité de leur projet au maximum** à travers les tests, l’intégration continue... Tout va bien pour ces personnes et l’entreprise, jusqu’au jour où l’entreprise grossit ou lorsque ces personnes veulent prendre des vacances (ou en cas de mort subite ou pire, en cas de mort subite en vacances.)

[**Aimant prendre des vacances** pour ma santé mentale](https://dev.to/s44d/comment-quitter-mon-job-et-voyager-pendant-un-an-ma-permis-de-mieux-travailler-59kh) et ma qualité de vie**,** mais aussi étant sensible [à l’accueil des nouveaux](https://dev.to/helenanders26/how-do-you-onboard-a-new-team-member-1khg), j’essaie de suivre ces principes, en communiquant le plus possible sur mon travail.

#### Pas de message privé, tout sur des channels publics

> J’ai souvent choisi de me taire, au moins j’étais sûr de pas me tromper. [“Des histoires à raconter “ — Casseur Flowters](https://www.youtube.com/watch?v=7WpIAWjna0U)

Je reconnais, ça peut être intimidant de parler sur un channel slack avec plusieurs dizaines de personnes. Notre petite voix dans notre tête, nous en empêche souvent, on préfère le confortable message privé pour potentiellement ne pas passser pour un idiot.

Ayant commencé ma carrière en support niveau 2, certains devs me fuyaient comme leur rétrospective agile bi-mensuelle, et mes messages restaient ignorés ou ne suscitaient que peu d’intêret, _quel dev digne de ce nom voudrait être sûr que son app tourne comme il le faut après tout_. Jusqu’au jour où je me suis trompé en posant une question sur de l’encodage vidéo, la [**loi de Cunningham**](https://meta.wikimedia.org/wiki/Cunningham%27s_Law) ne m’a pas trahi et a fondu sur moi tel un faucon: je me suis fait fumer par une dizaine de personnes me soulignant que je m’étais trompé, là où je galèrais d’habitude à obtenir une réaction…

> Quoi ?! Ca t’arrive de te tromper, Paul ?!

Vacciné par cet épisode, car jusqu’à preuve du contraire je suis toujours en vie, cela ne me gène plus de communiquer sur mon travail, à la manière de `ping paul@work` , je parle de mes difficultés ou mes succès de la journée régulièrement, dans l’espoir qu’une erreur soit repérée, d’obtenir une information loupée ou d’en donner implicitement.

Je me sers aussi souvent de mes anciens messages pour me souvenir d’un sujet lorsqu’on me demande plus d’info plusieurs semaines plus tard.

![](https://cdn-images-1.medium.com/max/800/1*RLkFPyFUWi91014fjehZnw.png)

[_Secrètement, j’espère que par l’exemple mes collègues soient petit à petit convaincus de cette utilité_](https://critter.blog/2020/11/05/respond-to-vulnerability-with-vulnerability/) _🙈 et je pense que ça viendra lorsqu’ils seront plus nombreux en télétravail_

#### Être précis, pour limiter les malentendus

Se mettre à la place de quelqu’un qui n’a pas pu tout suivre, et faciliter sa comprehension au maximum. **Je parle d’un fix par rapport à une alerte?** Bim je mets le lien vers le contexte de l’alerte si quelqu’un a besoin de détails. **Je découvre une nouvelle fonctionnalité d’une lib?** Je ne manque pas de mettre le lien qui m’a permis de mieux comprendre cette fonctionnalité.

Je me trouve des fois incapable d’aider simplement parce qu’il me manque le contexte. _Laissez moi vous aider svp_ 😛

#### Dire je ne sais pas

C’est **le boss final de la communication**, mais en le battant, ça apaise toute l’entreprise et crée une ambiance où il fait bon apprendre.

Il faut garder en tête que personne ne naît encore en maitrisant Kubernetes 😕 _Vivement les micro-puces tant vantées par_ [_Laurent Alexandre_](https://bonpote.com/analyse-et-critique-du-discours-de-laurent-alexandre/) _ou Musk, n’est ce pas ?_

#### Ce que j’aime faire, mais que je ne fais pas.

J’ai eu des echos positifs d’autres équipes sur les dailys ecrits. Mais comme pour les glaces, certaines personnes n’aiment pas le chocolat 🍫 et ça n’a pas pris, pour le moment, les daily standups meeting à vive voix ont de beaux jours devant eux.

![](https://cdn-images-1.medium.com/max/800/0*rhM3zFkcIWJODadT.png)

#### Ce que j’aime faire, et ce que je fais

**Une opération à faire sur un système ?** Je la joue équipe avec une autre personne, on prend le temps de prévoir, définir les critères d’acceptance, on se relit, et on prévient qu’on va la faire, on la fait et on laisse une trace écrite dans une documentation qu’on publie sur Slack pour historique. Un point bonus si les commandes sont enregistrées via [https://asciinema.org](https://asciinema.org/)

Un cercle vertueux se crée derrière ça, de plus en plus de personnes sont potentiellement, si elles dégagent du temps, capables de faire ce genre de tâches, ce qui fait de nous **des personnes non clés.** _Le facteur vélo, vous vous souvenez ?_

**J’utilise une librairie qui me fait gagner du temps ?** Je prevois que d’autres personnes auront les mêmes problèmes que moi ? Je pense à contribuer ou à la partager, de façon à ce qu’elle soit utilisée. Et désolé, partager un lien brut sur Slack ne suffit pas 😛 il faut un peu de description et des exemples.

![](https://cdn-images-1.medium.com/max/800/1*vK-TbMekqd48sc39XfCRRg.png)

### Les reproches

> On écrit trop

Certes, mais malgré cela, je constate qu’il reste toujours des situations où on se plaint d’un manque d’info sur une tâche ou une documentation. C‘est pourquoi on décide de prendre du temps pour câler une réunion et clarifier les malentendus de l’écrit pour en créer des nouveaux à l’oral pour ensuite écrire les décisions finales 😅

Pour les travaux créatifs ou d’innovation l’oral est le meilleur moyen, par contre pour les tâches plus individuelles, le remote est trés bien adapté.

> Ca prend trop de temps d’avoir Slack ouvert

Avec les bonnes configurations de notifications Slack, on peut optimiser notre temps. [Savez vous qu’on peut configurer les notifs par channel ou par mots clés ?](https://get.slack.help/hc/fr-fr/articles/201355156-Guide-des-notifications-de-Slack-)

#### Les appels vidéos

Je suis globalement fan, à moins que je sois le seul sur mon ordinateur et 20 autres personnes sur l’autre. Ca me donne clairement l’impression d’être mal voyant et mal entendant. [Le CTO de Saagie a trouvé quelques astuces pour ça et l’explique ici](https://www.youtube.com/watch?v=5MXSGW1uHck&feature=youtu.be&t=177)

> Paul, tu dors pas ?

_⬆️ La blague classique durant les réunions_

#### Le remote exceptionnel

Quand il est exceptionnel, le travail est aussi exceptionnel, mais pas dans le sens qu’on voudrait 😕 On peut se permettre de ne pas faire cette réunion car X est en télétravail aujourd’hui. Ou changer les habitudes de l’équipe:

> pas de daily aujourd’hui car je suis en remote

_Ah? Du coup faudrait il que_ j’arrête _les daily standup moi aussi ?_💭

Les réunions en remote (_me_) force à prendre des notes et faire prendre des décisions pour les comptes rendus. Ces derniers assurent que tout le monde valide les décisions prises durant la réunion, les historisent, et évitent les malentendus potentiels. Ce que je n’avais pas tendance à faire dans les locaux car _honnêtement, on était tous trés attentif,_ **_on s’est même regardé dans les yeux_**_, et on se souviendra de tout ce qui a été dit car on est des travailleurs productifs, non ?_

#### Les projets fantômes

Je vois passer des fois de trop rares messages sur certains projets, où je sens que je pourrais aider, ce qui est frustrant. Mais ne pouvant pas changer les habitudes d’autres personnes, le mieux est de s’effacer. Avec l’expérience et sachant que **les conflits sont normaux**, car je ne suis pas toi et tu n'es pas moi, ne pas pouvoir tout faire me parait judicieux. Cela permet de me concentrer sur mes projets en cours ou d’autres où des messages passent regulièrement sur Slack.

### Le télétravail accentue nos valeurs

Les valeurs ne sont pas ce qu’il y a écrit en gros sur vos murs ou ne sont pas ce que votre C-level répète sans arrêt, du style:“TEAMWORK” “CHALLENGE” “WORK HARD, PLAY HARD”

![](https://cdn-images-1.medium.com/max/800/1*naDrHJpxpWskmBbs1Usx5Q.jpeg)

**Je bosse pour un salaire**, _ce que les recruteurs essaient de nous faire oublier en mettant en avant la passion_, mais aussi **pour l’équipe.**

Même si il m’arrive d’écrire ironiquement “TEAMWORK” avec 8 points d’exclamation et 6 Ô consécutifs lors d’une pull request, _l’ironie est parfois dure à déceler, surtout à l’écrit, et peut aussi devenir vite toxique_, ça ne m’empêche pas d’être obsédé par le travail d’équipe et les remerciements que je donne ou que je reçois sont mes petites victoires du quotidien.

![](https://cdn-images-1.medium.com/max/800/1*IHgZGOFR6qMYYy398QaMvw.png)

_Je suis convaincu que cette obsession du travail d’équipe serait moins marquée si je n’étais pas en télétravail._

### La qualité de vie

A penser qu’au travail, on oublie nos difficultés du quotidien, et [cette lutte contre le temps accentuée par l’économie de l’attention](https://www.youtube.com/watch?v=gsci0h9vw7M) (_coucou les GAFA_) qu’on subit tous, pour garder du temps pour lire, écrire, courir, profiter de notre famille… Ne pas à avoir à faire 40 minutes de voiture, _ou 15 minutes en vélo,_ le matin et le soir, c’est 1h20 de gagnée par jour pour faire de choses utiles, s_ans parler de la pause déjeuner durant laquelle on peut manger plus sainement ou aller récupèrer ses enfants à l’école._

[Vincent Agnano](https://www.linkedin.com/in/vincentagnano) en parle parfaitement dans l’émission [“ça fait echo”](https://www.youtube.com/watch?v=gbpNBWLxQgY):

> Dans une entreprise, on est juste là tous les jours, et on est fatigué d’être là tous les jours

### Les remarques qu’on me fait le plus

> Tu te sens pas seul ?

Non, grâce au slack ou aux appels vidéos. Il faut s’assurer aussi d’avoir une vie hors des horaires du bureau: sport/culture/asso 😃

Je suis également présent 2 fois par mois dans les bureaux.

> Je n’arriverais pas à travailler chez moi

Les premiers jours peuvent être durs, j’ai eu tendance à travailler sur mon lit. On se rend vite compte que si on veut épargner notre dos, il faut du matériel adapté. Une pièce dédié, si possible, un deuxième écran, un clavier, une souris… Depuis petit, j’ai toujours aimé travailler dans le calme, et travailler depuis chez moi me le garantit, _à part quand mon voisin met du hard rock ou qu’une moto passe dans ma rue._

> Je regarderais la télé/jouerais à la PS4

On est censé produire des choses dans la journée, si personne ne le remarque, tant mieux pour toi, mais tu as peut être un [“job à la con”](https://fr.wikipedia.org/wiki/Bullshit_jobs)

### Conclusion

Il faut [se méfier des dogmes et des règles](https://twitter.com/allenholub/status/1116402948844638208), et les adapter, car comme les glaces, on a tous nos préférences. Il faut aussi les modifier [lorsque la routine devient trop lourde à supporter](https://twitter.com/sadoperator/status/969618247535312897). Le télétravail, au départ, peut paraître perturbant et intimidant pour vous et vos collègues avec ses clichés qui ont encore la belle vie, mais avec l’expérience il peut vous rendre plus productif (je ne citerai pas les études qui le disent) et peut changer totalement la manière dont vous travaillez tout en gagnant en qualité de vie 😎

### Inspirations

[**Great Teams Are About Personalities, Not Just Skills**  
_At the start of 2016 Google announced that it had discovered the secret ingredients for the perfect team. After years…_hbr.org](https://hbr.org/2017/01/great-teams-are-about-personalities-not-just-skills "https://hbr.org/2017/01/great-teams-are-about-personalities-not-just-skills")[](https://hbr.org/2017/01/great-teams-are-about-personalities-not-just-skills)

[**Managing Remote Teams - A Crash Course**  
_Hey folks, I haven't been blogging for quite some time, so everything is a bit rusty for me, but i thought this article…_klinger.io](https://klinger.io/post/180989912140/managing-remote-teams-a-crash-course "https://klinger.io/post/180989912140/managing-remote-teams-a-crash-course")[](https://klinger.io/post/180989912140/managing-remote-teams-a-crash-course)

[**Travailler seul(e) de chez soi**  
_Auto-entrepreneuse depuis presque 5 ans, je passe l'essentiel de mon temps à travailler de chez moi, en tête à tête…_fromsomewherewithlove.fr](https://fromsomewherewithlove.fr/travailler-seul-de-chez-soi/ "https://fromsomewherewithlove.fr/travailler-seul-de-chez-soi/")[](https://fromsomewherewithlove.fr/travailler-seul-de-chez-soi/)

**Merci aux relect.eur.trices.**