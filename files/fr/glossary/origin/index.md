---
title: Origine
slug: Glossary/Origin
tags:
  - Glossaire
  - Mécanismes web
  - origine
translation_of: Glossary/Origin
original_slug: Glossaire/Origine
---
L'**origine** d'une application web est définie par le schéma (protocole), l'hôte (domaine) et le port de l'{{Glossary("URL")}} utilisée pour y accéder. Deux objets ont la même origine seulement quand le schéma, l'hôte et le port correspondent.

Quelques opérations sont limitées au contenu de même origine, et cette restriction peut être levée avec [CORS](/fr/docs/Glossaire/CORS).

## Exemples

Les URL qui suivent partagent la même origine car elles ont le même schéma (`http`), nom d'hôte (`example.com`), et que les chemins de fichiers différents n'impportent pas :

- `http://example.com/app1/index.html`
- `http://example.com/app2/index.html`

Il s'agit ici de la même origine car le contenu HTTP est délivré, par défaut, via le port 80 :

- `http://Example.com:80`
- `http://example.com`

Ici, il ne s'agit pas de la même origine, car ce sont deux schémas différents :

- `http://example.com/app1`
- `https://example.com/app2`

Ce ne sont pas les mêmes origines pour les exemples qui suivent, car le nom d'hôte est différent :

- `http://example.com`
- `http://www.example.com`
- `http://monapp.example.com`

Les deux exemples qui suivent ne sont pas de la même origine, car les ports sont différents :

- `http://example.com`
- `http://example.com:8080`

## Pour en savoir plus

Voir [Same-origin policy](/fr/docs/Web/JavaScript/Same_origin_policy_for_JavaScript) _(politique de même origine)_ pour plus d'informations.
