---
title: "L'ingénieur reprend le produit - et l'AI lui en donne enfin le temps"
date: 2026-05-03
draft: false
thumbnail: "images/2026/couverture_article_devpo.png"
images:
    - "images/2026/couverture_article_devpo.png"
tags: ["devpo", "product", "engineering", "ai", "devops"]
description: "Pourquoi l'AI rend la séparation dev/PO obsolète, comme DevOps a fait tomber celle entre dev et ops, et redonne à l'ingénieur le temps de posséder le produit de bout en bout."
---

En 2020, j'écrivais que [le silo dev/PO méritait le même traitement que le silo dev/ops](https://www.epauler.fr/article/la-culture-de-la-r%C3%A9silience-%C3%A0-travers-le-devops-devpo-et-devqa/). J'appelais ça DevPO - savoir *pourquoi* on construit, inséparable de la compréhension de la machine.

Quelques années plus tard, le terrain a répondu - dans l'article PostHog ["Product management is broken. Engineers can fix it"](https://newsletter.posthog.com/p/product-management-is-broken-engineers), dans le podcast d'[un managing director chez Khosla Ventures](https://www.youtube.com/watch?v=xCd9ykretlg), dans celui d'[un ex-CPO de Credit Karma](https://www.youtube.com/watch?v=yUohoaC8_Hs), et dans les coulisses d'Anthropic. Un peu moins en France.

---

## Ce texte n'est pas un procès des PMs

La guerre PM vs dev est un symptôme, pas le sujet.

La cible, c'est un type de rôle : l'*information mover* - celui dont la valeur ajoutée est de reformater, synthétiser, et faire circuler de l'information entre des gens qui pourraient se parler directement. Ce rôle-là, l'AI le supprime. Pas la compétence, pas la vision, pas la relation utilisateur. Mais la circulation d'information.

Le vrai sujet, c'est **qui est responsable de la qualité du produit livré** - de bout en bout, du besoin au code en production. Tant que cette responsabilité est floue, distribuée, négociable, tout le monde optimise pour son périmètre. Le PM défend sa roadmap. L'ingénieur défend son code. Personne ne possède le résultat final.

[DevOps](https://fr.wikipedia.org/wiki/Devops) a résolu ça entre dev et ops en rendant la responsabilité indivisible : tu déploies ce que tu codes, tu monitores ce que tu déploies. DevPO pose la même question au niveau produit. Ce n'est pas une question de rôles - c'est une question d'architecture organisationnelle.

Une précision s'impose d'emblée : en 2010, les ops avaient peur que DevOps les supprime. Ils sont devenus SREs, platform engineers, cloud architects. Le rôle a changé, pas disparu. DevPO raconte la même histoire pour les PMs - pas une suppression, une transformation. La partie mécanique du rôle disparaît. Ce qui reste est plus intéressant.

---

## Le problème que DevPO cherchait à nommer

Le PM classique est un traducteur. Il prend les besoins utilisateurs, les traduit en specs, les transmet à l'ingénierie qui exécute. Ce modèle a une limite structurelle : sans appréciation du coût technique, le PM écrit des specs sans signal de résistance interne. Il ne sait pas où couper, donc il ne coupe pas. La spec grossit vers la version complète parce que c'est plus facile à vendre en interne - et surtout personne ne paie le coût de la complexité au moment de l'écrire.

Soit l'ingénieur corrige silencieusement - dette technique invisible, frustration accumulée, burn out... Soit personne ne corrige, et on livre quelque chose qui tient en prod comme un château de cartes. Dans les deux cas, c'est l'équipe technique qui porte le bébé, et les astreintes. Les risques ne sont pas symétriques.

Ce n'est pas la faute du PM. C'est la conséquence d'un système qui lui confie une responsabilité sans lui donner les outils pour l'exercer correctement.

---

## Pourquoi c'est plus accentué en France

Le mur dev/PO en France est alimenté par deux pipelines.

Les écoles de commerce forment des PMs à la vision stratégique sans jamais les confronter à la machine. Mais le pipeline le plus discret vient des écoles d'ingénieurs elles-mêmes : le PM y est devenu la sortie naturelle pour ceux que la technique fatigue ou n'a jamais vraiment intéressé. Rester dev après 30 ans, dans beaucoup de boîtes françaises, ça ressemble encore à un aveu d'échec.

Ce qu'on oublie dans cette course vers le management : les bases techniques ne bougent pas. Les tests, le monitoring, la capacité à communiquer sur la complexité - ça reste, quelle que soit la stack. C'est précisément ce socle qui permet de comprendre ce qu'on construit. En partant, les seniors emportent ce capital avec eux - et laissent des juniors sans la légitimité pour dire non à une mauvaise spec.

En Amérique du Nord, j'ai vécu l'inverse. À 28 ans, j'étais le plus jeune de mon équipe, en train de discuter de p99 avec des ingénieurs de 40 ans encore passionnés. Des gens qui auraient dû devenir PM depuis longtemps et qui avaient choisi de rester. Ce n'est pas un détail - c'est toute la différence.

À 35 ans, je ne me vois pas abandonner les compétences construites en entreprise et sur des side projects. Comprendre le besoin, posséder la décision, monitorer ce que je livre - c'est ce que je fais depuis que j'ai commencé à coder. Ce n'est pas une ambition de product engineer, c'est juste ce que ça veut dire de faire ce métier sérieusement. **La séparation des rôles n'est pas une évolution naturelle - c'est un choix organisationnel qu'on doit refuser, pour mieux servir le produit.**

[Emilien Pecoul](https://medium.com/@Ouarzy/la-france-g%C3%A2che-son-talent-num%C3%A9rique-9e7a010585e5) posait déjà la question : pourquoi les États-Unis créent des GAFAM pendant qu'on crée des Capgemini et des Atos ? Le silo dev/PO est une partie de la réponse.

---

## PostHog, Rabois, Singhal, Anthropic - le même diagnostic

Récemment, plusieurs voix très différentes sont arrivées à la même conclusion.

[PostHog](https://newsletter.posthog.com/p/product-management-is-broken-engineers) avec *"Product management is broken. Engineers can fix it."* : les *product engineers* possèdent le roadmap, parlent aux utilisateurs, définissent ce qu'on construit. Les PMs informent sans posséder.

[Keith Rabois](https://www.youtube.com/watch?v=xCd9ykretlg) - vétéran de PayPal, COO de Square - dans un épisode du Lenny's Podcast : la vraie compétence pour les ingénieurs qui vont compter, c'est pas maîtriser Scala sur le bout des doigts - c'est comprendre ce qu'on construit et pourquoi. Il cite Levchin, Stoppelman : les meilleurs ingénieurs ont toujours eu des instincts commerciaux. C'est DevPO sans le nommer.

[Amol Avasare](https://www.youtube.com/watch?v=k-H4nsOTuxU), head of growth chez Anthropic, apporte une perspective depuis l'intérieur. Chez eux, les ingénieurs gagnent 3x de productivité avec Claude Code - et les PMs sont écrasés. Leur réponse concrète : la règle des deux semaines. En dessous, l'ingénieur est le PM - il parle aux legal, aux stakeholders, il drive. Au dessus, le PM reprend la main. Ce n'est pas une expérimentation - c'est la pratique quotidienne de la boîte qui croît le plus vite du monde. Et leur conclusion : les ingénieurs product-minded voient leur valeur exploser d'un ordre de grandeur.

Ce modèle fonctionne aussi parce qu'Anthropic a fait un autre choix radical : la transparence totale. Chaque employé a un channel Slack public où il partage ses pensées, priorités, doutes - à l'opposé du cliché du dev asocial qui attend qu'on lui dépose des tickets. Les débats avec le CEO se font en public. C'est la condition structurelle qui rend DevPO possible : une spec naïve ne peut pas survivre longtemps dans une organisation où les ingénieurs lisent tout en temps réel.

[Nikhyl Singhal](https://www.youtube.com/watch?v=yUohoaC8_Hs) - ex-Meta, ex-Google, CPO de Credit Karma - va dans le même sens : les PMs se divisent en deux camps. Les *builders*, qui construisent activement et ont des instincts produit. Et les *information movers*, qui font circuler l'information entre équipes sans jamais toucher la machine.

> L'information mover est essentiellement en train de devenir un dinosaure - Nikhyl Singhal

Il observe quelque chose d'ironique : pendant des années, réussir en product management c'était apprendre à ne plus rien construire soi-même. L'AI a inversé cette logique. Les meilleurs product leaders redeviennent des faiseurs - et c'est ce qui les rend à nouveau passionnés par leur métier.

Là où nos analyses divergent : Rabois et Singhal pensent que la compétence "comprendre ce qu'on construit" est dissociable de la technique. Je pense qu'elles sont liées. Le cas Anthropic le confirme brutalement : Amol explique que chez eux les PMs de Claude Code sont "basically engineers themselves anyway". Ce n'est pas un détail de culture - c'est une nécessité. Un PM qui ne comprend pas ce qu'est un context window, un system prompt, ou ce que coûte un million de tokens en inférence ne peut pas prioriser correctement sur ce produit. **Le contexte produit *est* la technique.**

Sur le fond, tous convergent avec DevPO : le modèle du PM *information mover* est mort. **Tant qu'on ne répond pas à ça, on reproduit le modèle col blanc qui décide, col bleu qui exécute - juste avec des MacBooks et du Jira.**

---

## BMAD, ou la preuve par l'outillage

[BMAD](https://github.com/bmad-code-org/BMAD-METHOD) - Breakthrough Method for Agile AI-Driven Development - rend le problème encore plus concret. Un pipeline d'agents IA spécialisés : Analyst, PM, Architect, Scrum Master. Chaque agent reçoit les artefacts du précédent, contraint par ce qui précède.

Dans BMAD, l'agent PM ne peut pas écrire une spec naïve sans que l'agent Architect le recadre. Le circuit de feedback que le PM humain n'a pas - parce qu'il n'a pas la compréhension technique pour s'auto-corriger - est ici câblé dans le workflow.

Ce que ça révèle : la "traduction" ne nécessite pas un humain non-technique. Elle nécessite une contrainte technique. Ce qui reste une fois ce travail automatisé - contexte marché, relation utilisateur, vision stratégique - c'est exactement ce que PostHog, Rabois, Singhal et Anthropic identifient comme la vraie valeur. BMAD ne remplace pas le PM. Il remplace l'*information mover*.

Mais il reste un risque que ni BMAD ni Claude ne résolvent. Un PM peut maintenant demander à Claude si une feature se fait - et obtenir une réponse honnête en 30 secondes. C'est réel. Le seuil d'entrée technique s'est abaissé. Sauf que sans comprendre suffisamment la technique pour juger la réponse, le PM ne sait pas si elle est fiable dans *son* contexte. Une erreur 500 sur une API externe devient un bug à fixer. Une spec validée par Claude devient une décision solide - alors qu'elle ignore la dette de la codebase, l'état de l'infrastructure, les contraintes d'équipe.

C'était déjà le même avertissement dans les cours [Coursera de data science en 2014](https://www.coursera.org/learn/data-scientists-tools) : compétence technique + compétence analytics, sans fondamentaux ML - et on produisait des algorithmes qui tournaient parfaitement, racontaient des histoires convaincantes, et étaient complètement faux. **La confiance sans le discernement est plus dangereuse que l'ignorance. Le PM armé de Claude sans compréhension technique, c'est le même risque - en mieux habillé.**

---

## Ce que le terrain a confirmé

PostHog a montré qu'une organisation peut fonctionner sans que le PM possède le roadmap. Rabois a montré que les meilleurs ingénieurs ont toujours eu des instincts commerciaux. Anthropic a montré que la règle des deux semaines fonctionne en prod. BMAD a montré que la traduction technique peut être automatisée. Et Singhal l'a formulé sans détour : les builders vont avoir la vie de leur rêve - et les information movers vont disparaître.

**DevPO n'est pas une évolution du rôle PM. C'est le retour du dev au centre** - à condition qu'il se bouge, qu'il possède une culture DevOps, qu'il monitore ce qu'il livre et qu'il accepte la responsabilité du résultat.

Un PM ne mettra jamais quelque chose de solide en prod seul. Un dev expérimenté, si. Et avec l'AI, ce dev peut maintenant pondre des specs pointues qui répondent aux besoins utilisateurs - via tests IHM, analytics, feedback direct. Ce que PostHog a fait n'est pas une innovation organisationnelle. C'est un retour à l'état naturel des choses, rendu enfin possible.

La vraie question n'est pas "dev ou PM après 30 ans". C'est : **est-ce que ton organisation te donne une trajectoire où la profondeur technique est récompensée autant que le management ?** Si la réponse est non, le problème est dans l'organisation, pas dans le dev.

Singhal parle de PMs "builders" - des gens qui ouvrent Claude Code et livrent vite. Le problème : sans comprendre ce qu'on construit, le vibe coding finit toujours par crasher en prod. Le DevPO produit avec la compréhension que ça va servir à quelque chose - pas juste livrer.

---

DevPO c'est toujours d'actualité. Et ça va bouger très vite.
