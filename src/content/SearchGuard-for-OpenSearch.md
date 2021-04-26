---
title: 'OpenSearch par AWS & Search Guard™'
author: [Sarah L.CORSELIS]
image: img/opensearch.png
date: '2021-04-26T10:00:00.000Z'
draft: false
tags:
  - OpenSearch
  - SearchGuard
---

Amazon a récemment annoncé l'introduction d'[OpenSearch](https://aws.amazon.com/fr/blogs/opensource/introducing-opensearch/), un fork entièrement Open Source d'Elasticsearch et Kibana, entièrement piloté par la communauté et dont le codebase complet est [publié sous licence Apache 2.0](https://aws.amazon.com/fr/blogs/opensource/stepping-up-for-a-truly-open-source-elasticsearch/). Non seulement Floragunn soutient pleinement OpenSearch, mais nous sommes aussi heureux d'y contribuer en y apportant toute l’expérience en matière de sécurité et d'alerting que nous avons pu acquérir depuis [la création du premier plugin de sécurité en 2013](https://github.com/salyh/elasticsearch-security-plugin/commit/1d52068b0163f4994120a886c95f7de2e04cb5d8).

# Qu'est-ce qu' OpenSearch ?

OpenSearch est un fork des dernières versions d'Elasticsearch et de Kibana sous licence Apache2. Le projet contient OpenSearch (dérivé de la version OSS d'Elasticsearch 7.10.2) et OpenSearch Dashboards (dérivé de la version OSS de Kibana 7.10.2). L'intégralité du code source d' [OpenSearch](https://github.com/opensearch-project/OpenSearch) et d' [OpenSearch Dashboards](https://github.com/opensearch-project/OpenSearch-Dashboards) est sous licence Apache2 et est disponible sur GitHub pour téléchargement - inspection - modification - build - run.

Si AWS est aujourd'hui principalement responsable de la gestion et de la maintenance d'OpenSearch, d'autres grandes entreprises comme [Red Hat, SAP, Capital One et Logz.io](https://aws.amazon.com/fr/blogs/opensource/introducing-opensearch/) ont déjà rejoint le projet OpenSearch. D'après nous, cela démontre qu' OpenSearch a plus qu'assez d'élan pour devenir un projet majeur dans l'espace du logiciel libre. AWS a également mis en ligne un site communautaire, incluant des ["principes de développement du projet OpenSearch"](https://opensearch.org/).
Nous en applaudissons l’arrivée et sommes heureux d’apporter notre expérience dans les domaines de la sécurité et de l’alerting.
 

# Pourquoi forker  - Changements de licence d'Elasticsearch

D’après AWS, la principale raison ayant mené au fork des projets est le récent changement de licence des projets Elasticsearch et Kibana, Elastic ayant annoncé, en Janvier 2021, sa décision de rompre avec les modalités de distributions traditionnellement open source d'Elasticsearch et de Kibana sous licence Apache2. A partir de la version 7.11, leur code respectif est ainsi distribué sous [double licence : Server Side Public License (SSPL)  - Licence Elastic](https://www.elastic.co/blog/licensing-change), le choix de leur application étant ainsi laissé à leurs utilisateurs.

En Février 2021, soit quatre semaines après le changement de licence, Elastic a annoncé l'introduction de [la licence Elastic v2 (ELv2)](https://www.elastic.co/blog/elastic-license-v2), cette dernière ayant vocation à remplacer l'ancienne licence Elastic.

Au moment de la rédaction de cet article, les versions les plus récentes d'Elasticsearch et de Kibana sont ainsi disponibles sous double licence : SSPL et ELv2. L'Open Source Initiative [n’a pas reconnu ces deux licences](https://opensource.org/node/1099) comme répondant à sa [définition de l'Open Source](https://opensource.org/osd). Cela signifie qu' OpenSearch et OpenSearch Dashboards s’avèrent être l’unique option des utilisateurs adhérant aux principes adoptés par l'Open Source Initiative.
 
# Un éventail d'options s'offrent désormais aux utilisateurs de Search Guard™

En tant que partisans convaincus de l'Open Source et particulièrement en ce qui concerne la sécurité, nous ne pouvons que constater la nécessité évidente d’un logiciel de recherche et d'analyse sécurisé, de haute qualité et entièrement Open Source.

Nous nous sommes toujours engagés à soutenir la communauté, c’est pourquoi dès la sortie initiale de Search Guard, [la Community Edition](https://search-guard.com/elasticsearch-security-free-search-guard/), a été mise gratuitement à disposition des utilisateurs d’Elasticsearch. Cette version sous licence Apache2 couvre toutes les fonctionnalités de sécurité majeures requises pour exécuter Elasticsearch en production en toute sécurité. Outre l'option gratuite, nous proposons les éditions commerciales Enterprise et Compliance pour les utilisateurs aux besoins spécifiques.

À l'avenir, les utilisateurs de Search Guard pourront choisir parmi une large gamme d'options :
Nous continuons à fournir des versions de Search Guard pour la pile Elastic sous double licence. Nous avons déjà publié Search Guard pour Elasticsearch [7.11](https://forum.search-guard.com/t/new-release-search-guard-50-for-elasticsearch-7-11-1-and-7-11-2/2136) et [7.12](https://forum.search-guard.com/t/search-guard-for-elasticsearch-7-12-0/2154). Aucun changement n’est à observer quant à l'utilisation ou dans les conditions de licensing de Search Guard.
Si vous vous trouvez, à ce jour, dans l’incertitude quant à votre utilisation d'Elasticsearch quant au fait qu’elle soit toujours autorisée par la licence SSPL ou ELv2 de la société Elastic, vous pourrez requérir un avis juridique.

Nous étudions la possibilité de sortie d’une version alpha/bêta d'un produit Search Guard pour OpenSearch à l’horizon de l'automne 2021, qui vous permettra de bénéficier d’une large gamme d'options concernant la sécurité et l'alerting.

- Notre produit Search Guard actuel sera maintenu et les utilisateurs pourront continuer à en profiter tel qu’ils le connaissent aujourd’hui 
- Un produit Search Guard pour OpenSearch est prévu, avec une version alpha/bêta estimée pour l'automne 2021.
- Les utilisateurs peuvent également choisir de souscrire à l'un des plans d'abonnement Elastic.

Nous sommes ravis de la dynamique de la communauté qui inclut des acteurs aussi notables que Red Hat, SAP, Capital One et Logz.io.
L'équipe de Search Guard croit en cette communauté, autant qu'elle croit profondément en l'Open Source, et attend désormais les développements prévus à l'’été 2021* avec impatience.

Claudia Kressin et l'équipe de Search Guard
Publié le 19/04/2021 : https://search-guard.com/opensearch-aws-search-guard-elasticsearch/ 

> * NDLR : lors du meetup **"OpenSearch & Open Distro for Elasticsearch"** du Mardi 20 Avril 2021, AWS annonçait une GA release pour l’été 2021 – mi-année 2021