---
title: HTTP/2
slug: Glossary/HTTP_2
tags:
  - Glossaire
  - HTTP
  - Infrastructure
  - Performance du Web
  - Reference
  - l10n:priority
translation_of: Glossary/HTTP_2
original_slug: Glossaire/HTTP_2
---
**HTTP/2** est une révision majeure du [Protocole de réseau HTTP](/fr/docs/Web/HTTP/Basics_of_HTTP). Les principaux objectifs de HTTP/2 sont de réduire la {{glossary("latency","latence")}} en permettant le multiplexage complet des demandes et des réponses, minimiser la surcharge du protocole grâce à une compression efficace des champs d'en-tête HTTP, et ajouter la prise en charge de la priorisation des demandes et de la diffusion sur le serveur.

HTTP/2 ne modifie en aucune façon la sémantique d'application de HTTP. Tous les concepts fondamentaux de HTTP 1.1, tels que les méthodes HTTP, les codes d'état, les URL et les champs d'en-tête, restent en place. En revanche, HTTP/2 modifie la façon dont les données sont formatées (encadrées) et transportées entre le client et le serveur, qui gèrent tous deux l'ensemble du processus, et dissimule la complexité de l'application dans la nouvelle couche d'encadrement. Par conséquent, toutes les applications existantes peuvent être fournies sans modification.

## Voir aussi

1.  Culture générale

    1.  [HTTP sur le MDN](/fr/docs/Web/HTTP)
    2.  {{interwiki("wikipedia", "HTTP/2", "HTTP/2")}} sur Wikipedia

2.  [Glossaire](/fr/docs/Glossaire)

    1.  {{glossary("HTTP")}}
    2.  {{glossary("Latency","Latence")}}
