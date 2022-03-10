---
title: PerformanceTiming.navigationStart
slug: Web/API/PerformanceTiming/navigationStart
tags:
  - API
  - Backwards compatibility
  - Deprecated
  - Navigation Timing
  - PerformanceTiming
  - Property
  - Propriété
  - Read-only
  - legacy
  - navigationStart
translation_of: Web/API/PerformanceTiming/navigationStart
---
{{APIRef("Navigation Timing")}}

> **Attention :** Cette interface est dépréciée dans la spécification [Navigation Timing Level 2](https://w3c.github.io/navigation-timing/#obsolete). Veuillez utiliser l'interface [`PerformanceNavigationTiming`](/fr/docs/Web/API/PerformanceNavigationTiming) à la place.

L'ancienne propriété en lecture seule **`navigationStart`** retourne un `unsigned long long` représentant le moment, en millisecondes depuis l'époque UNIX, juste après la fin de l'invite de déchargement sur le document précédent dans le même contexte de navigation. S'il n'y a pas de document précédent, cette valeur sera la même que [`PerformanceTiming.fetchStart`](/fr/docs/Web/API/PerformanceTiming/fetchStart).

## Syntaxe

```js
let time = performanceTiming.navigationStart;
```

## Spécifications

| Spécification                                                                                                                                                    | Statut                                   | Commentaire          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- | -------------------- |
| {{SpecName('Navigation Timing', '#dom-performancetiming-navigationstart',
        'PerformanceTiming.navigationStart')}} | {{Spec2('Navigation Timing')}} | Définition initiale. |

## Compatibilité des navigateurs

{{Compat("api.PerformanceTiming.navigationStart")}}

## Voir aussi

- L'interface [`PerformanceTiming`](/fr/docs/Web/API/PerformanceTiming) à laquelle elle appartient.
