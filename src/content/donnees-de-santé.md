---
title: 'Détection de données de santé exposées'
author: [Sarah L.CORSELIS]
image: img/health.jpg
date: '2021-01-28T10:00:00.000Z'
draft: false
tags:
  - Data privacy
  - Compliance
  - Elasticsearch
  - Data leaks
---
Les fuites de bases de données donnent fréquemment lieu à leur altération / effacement / vol ou encore à des attaques de type ransomware ou de type phishing.

Les données de santé, soumises à une forte cotation sur le dark net, sont de fait particulièrement recherchées par les pirates informatiques, plaçant le secteur de la santé en première ligne face aux attaques.

Ces fuites sont généralisées, poussant par exemple la Cnil à réagir publiquement quelques mois après la vague d’attaque des instances Elasticsearch par le bot « Meow », qui supprimait l’intégralité des indices accessibles pour les remplacer par la tristement féline onomatopée.

Paradoxalement, ces fuites de données massives ne sont souvent les conséquences que de simples erreurs de configuration et seraient donc, pour la majeure partie, évitables.

Le contrôle régulier des infrastructures ou de celles de ses prestataires s'inscrit pleinement dans un cercle vertueux de la mise en œuvre de la conformité des traitements au RGPD. 

> La notion de donnée de santé, considérée comme sensible d'après la CNIL "recouvre non seulement l’ensemble des données collectées et produites dans le cadre du parcours de soins mais aussi celles qui, détenues par d’autres acteurs (développeurs d’application par exemple), constituent une information sur l’état de santé de la personne."

## Concernant la sécurité : 

Dans le référentiel relatif aux traitements de données à caractères personnels destinés à la gestion des cabinets médicaux et paramédicaux, le professionnel de santé est invité par la CNIL à prendre des précautions en amont pour assurer la sécurité de la donnée, de la collecte à la transmission et ce jusqu'au stockage. A la charge du professionnel d'en assurer l'intégrité, ainsi que "d'empêcher que des tiers non autorisés y aient accès". Or :
- Il peut être difficile, au vu de la multitude d'outils et de services tiers impliqués dans la chaîne de traitement de la donnée, de vérifier si oui ou non ces exigences ont été respectées ou si un maillon de la chaîne connait / à connu une vulnérabilité.

- Les vulnérabilités observées ne relèvent parfois tout simplement pas de vos opérations mais de celles de votre prestataire, malgré une responsabilité partagée devant l'autorité de contrôle.

## Un service de détection des données exposées :

Personne n'est à l'abri d'une violation ou d'une fuite de données : il est du devoir des professionnels du numérique d'accompagner les professionnels de santé et de les aider en ces circonstances particulières.

Une simple volonté de procéder à une vérification ? Nous pouvons aider à trouver des informations médicales exposées, dans le cadre d'un audit non intrusif.

**Audit gratuit** -**Echantillon des données trouvées** - **Confidentialité**


## sources:
https://www.silicon.fr/donnees-sante-manne-hackers-rex-mundi-labio-anthem-111812.html

https://www.cnil.fr/fr/quest-ce-ce-quune-donnee-de-sante

https://www.cnil.fr/fr/la-cnil-publie-trois-referentiels-pour-le-secteur-de-la-sante

<span>Photo par <a href="https://unsplash.com/@marceloleal80?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Marcelo Leal</a> sur <a href="https://unsplash.com/s/photos/health-care-data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>