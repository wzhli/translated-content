---
title: Date.prototype.setSeconds()
slug: Web/JavaScript/Reference/Global_Objects/Date/setSeconds
tags:
  - Date
  - JavaScript
  - Méthode
  - Prototype
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Date/setSeconds
original_slug: Web/JavaScript/Reference/Objets_globaux/Date/setSeconds
---
{{JSRef}}

La méthode **`setSeconds()`** définit les secondes pour la date, selon l'heure locale.

{{EmbedInteractiveExample("pages/js/date-setseconds.html")}}

## Syntaxe

    dateObj.setSeconds(valeurSecondes[, valeurMs])

### Versions antérieures à JavaScript 1.3

    dateObj.setSeconds(valeurSecondes)

### Paramètres

- `valeurSecondes`
  - : Un entier entre 0 et 59.
- `valeurMs`
  - : Paramètre optionnel, un nombre entre 0 et 999, représentant les millièmes de secondes.

### Valeur de retour

Le nombre de millisecondes écoulées entre le premier janvier 1970 minuit, UTC et la date mise à jour.

## Description

Si le paramètre `valeurMs` n'est pas utilisé, la valeur renvoyée par la méthode {{jsxref("Date.getMilliseconds", "getMilliseconds()")}} sera utilisée.

Si un paramètre utilisé est en dehors des limites attendues, `setSeconds()` tentera de mettre à jour la date en conséquence. Par exemple, si on utilise la valeur 100 pour `valeurSecondes`, les minutes de la date seront incrémentées de 1, et 40 sera utilisé pour les secondes.

## Exemples

### Utiliser `setSeconds()`

```js
var leGrandJour = new Date();
leGrandJour.setSeconds(30)
```

## Spécifications

| Spécification                                                                                                        | État                         | Commentaires                                          |
| -------------------------------------------------------------------------------------------------------------------- | ---------------------------- | ----------------------------------------------------- |
| {{SpecName('ES1')}}                                                                                             | {{Spec2('ES1')}}         | Définition initiale. Implémentée avec JavaScript 1.0. |
| {{SpecName('ES5.1', '#sec-15.9.5.30', 'Date.prototype.setSeconds')}}                         | {{Spec2('ES5.1')}}     |                                                       |
| {{SpecName('ES6', '#sec-date.prototype.setseconds', 'Date.prototype.setSeconds')}}         | {{Spec2('ES6')}}         |                                                       |
| {{SpecName('ESDraft', '#sec-date.prototype.setseconds', 'Date.prototype.setSeconds')}} | {{Spec2('ESDraft')}} |                                                       |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Date.setSeconds")}}

## Voir aussi

- {{jsxref("Date.prototype.getSeconds()")}}
- {{jsxref("Date.prototype.setUTCSeconds()")}}
