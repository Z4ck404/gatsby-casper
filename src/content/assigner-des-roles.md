---
layout: post
title: 'Assigner des rôles basés sur des ips ou des noms d’hôtes'
author: [Zakaria ELBAZI]
image: img/host.jpg
date: '2020-12-03T23:00:37.121Z'
draft: false
tags:
  - Search-guard
  - Tips
---
L'une des caractéristiques les plus méconnues de Search Guard est la possibilité d'utiliser le nom d'hôte ou l'adresse IP pour associer des rôles à une requête.

Le cas d'utilisation le plus courant est de permettre l'accès complet à toutes les données d'Elasticsearch si la requête a été effectuée directement depuis un nœud du cluster
### **Mapper des utilisateurs à des rôles**

Dans une configuration typique Elasticsearch / Search Guard, créez deux ou trois rôles qui définissent les autorisations d'accès, puis affectez des utilisateurs à ces rôles.

Les deux attributs gatbles plus courants pour [attribuer des rôles aux utilisateurs](https://docs.search-guard.com/latest/mapping-users-roles) :

- Nom d'utilisateur

- Rôles backend, par exemple, groupe LDAP ou JWT payload

Une cartographie des rôles type pourrait ressembler à cela :
```
sg_read_write:
  users:
    - janedoe
    - johndoe
  backend_roles:
    - 'cn=ldaprole,ou=groups,dc=example,dc=com'

```
Cette définition attribue le rôle sg_read_write aux utilisateurs dont le nom d'utilisateur serait janedoe ou johndoe, et aux utilisateurs qui appartiennent au groupe LDAP : `cn=ldaprole,ou=groupes,dc=exemple,dc=com`.

Le rôle sg_read_write définit les autorisations dont disposent ces utilisateurs pour accéder au cluster Elasticsearch.
### **Utilisation des noms d'hôtes et des adresses IP pour mapper les rôles**
En plus du nom d'utilisateur (username) et des rôles backend (backend_roles), vous pouvez également utiliser le nom d'hôte ou l'adresse IP de l’utilisateur pour attribuer des rôles.

Cette fonction permet essentiellement d'attribuer des rôles de manière dynamique, en fonction de la provenance de la demande.

Par exemple, vous pouvez vouloir n'accorder à un utilisateur qu'un ensemble limité de permissions si le cluster est accessible depuis l'extérieur de votre réseau. Si l'accès se fait de l'intérieur, l'utilisateur peut disposer de permissions plus larges.

Le cas le plus fréquent est probablement d’accorder à un utilisateur un accès complet à tous les indices et données si la demande provient d'un nœud de votre cluster lui-même. Alors que les utilisateurs ne devraient disposer que d’un accès limité, vous souhaitez accorder des autorisations DevOps complètes si quelqu'un s’y connecte en SSH à des fins de troubleshooting. 
### **Pour mapper des rôles :**

Vous pouvez mettre en place un simple rôle Search Guard sans aucune limitation d'accès : 
```
allow_internal_network:
  type: "net_mask"
  verdict: "allow"
  value: ["192.168.0.0/16"]
  description: "Allow internal network"
```
Après avoir téléchargé le fichier blocks.yml en utilisant sgadmin, les changements prennent effet immédiatement. L'accès n'est désormais possible que depuis le réseau interne. Comme alternative, vous pouvez utiliser l’ [API REST Blocks](https://docs.search-guard.com/latest/rest-api-blocks#put) tel que : 
```
sg_all_access:
  cluster_permissions:
    - *
  index_permissions:
    - index_patterns:
        - "*"
      allowed_actions:
        - "*"
```
Configurez ensuite une cartographie des rôles qui attribue toutes les demandes de 127.0.0.1 à ce rôle :
```
sg_all_access:
  hosts:
    - "127.0.0.1"

```
### **Avancé : Recherche par nom d'hôte**
Search Guard propose trois modes différents de résolution du nom d'hôte réel par rapport à la cartographie des hôtes configurée.

- Ip-only Match : Adresses IP uniquement. Par défaut.

- Ip-hostname Match : Adresses IP et noms d'hôtes.

- ip-hostname-lookup : Fait correspondre les adresses IP et les noms d'hôtes, et effectue une recherche inversée de noms d'hôtes
Cela peut être configuré dans sg_config.yml :
```
searchguard
        dynamic
            hosts_resolver_mode: <mode>
```

### Pour aller plus loin : 
Lire la documentation sur [l'utilisation du rôle mapping](https://docs.search-guard.com/latest/mapping-users-roles) pour assigner des rôles Si vous avez des questions, rendez-vous sur notre [forum](https://forum.search-guard.com/c/alerting-signals/12) !
> Publié le 19/11/2020 sur [le blog Search Guard](https://search-guard.com/elasticsearch-assign-role-ip-hostname/)

> <span>Photo par <a href="https://unsplash.com/@fantasyflip?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Philipp Katzenberger</a> sur <a href="https://unsplash.com/s/photos/security?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>