---
title: CacheStorage.has()
slug: Web/API/CacheStorage/has
tags:
  - API
  - CacheStorage
  - Experimental
  - Méthode
  - Reference
  - Service Workers
  - ServiceWorker
  - has
translation_of: Web/API/CacheStorage/has
---
{{APIRef("Service Workers API")}}{{SeeCompatTable}}

La méthode **`has()`** de l'interface {{domxref("CacheStorage")}} retourne une {{jsxref("Promise", "Promesse")}} qui renvoie `true` si un objet {{domxref("Cache")}} est égal au `cacheName`.

Vous pouvez accéder à `CacheStorage` via la propriété globale {{domxref("WindowOrWorkerGlobalScope.caches", "caches")}}.

## Syntaxe

    caches.has(cacheName).then(function(true) {
      // le cache existe!
    });

### Paramètres

- cacheName
  - : Un  {{domxref("DOMString")}} représentant le nom de l'objet {{domxref("Cache")}} que vous cherchez dans le {{domxref("CacheStorage")}}.

### Retour

Une {{jsxref("Promise", "Promesse")}} qui renvoie `true` si le cache existe.

## Exemples

L'exemple suivant vérifie qu'un cache nommé 'v1' exists. Si c'est le cas, nous lui ajoutons une liste d'assets. Si non (la promesse `has()` est rejetée) alors nous exécutons une sorte d'initialisation du cache.

```js
caches.has('v1').then(function() {
  caches.open('v1').then(function(cache) {
      return cache.addAll(myAssets);
  });
}).catch(function() {
  someCacheSetupfunction();
});;
```

## Spécifications

| Spécification                                                                                        | Statut                               | Commentaire          |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------ | -------------------- |
| {{SpecName('Service Workers', '#cache-storage-has', 'CacheStorage: has')}} | {{Spec2('Service Workers')}} | Définition initiale. |

## Compatibilités des navigateurs

{{Compat("api.CacheStorage.has")}}

## Voir aussi

- [Utiliser les Service Workers](/fr/docs/Web/API/Service_Worker_API/Using_Service_Workers)
- {{domxref("Cache")}}
- {{domxref("WorkerGlobalScope.caches")}}
