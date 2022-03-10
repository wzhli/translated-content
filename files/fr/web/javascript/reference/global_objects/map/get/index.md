---
title: Map.prototype.get()
slug: Web/JavaScript/Reference/Global_Objects/Map/get
tags:
  - ECMAScript 2015
  - JavaScript
  - Map
  - Méthode
  - Prototype
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Map/get
original_slug: Web/JavaScript/Reference/Global_Objects/Map/get
---
{{JSRef}}

La méthode **`get()`** renvoie un élément précisé d'un objet `Map`. Si la valeur associée à la clé fournie est un objet, alors on obtient une référence à cet objet et tous changements apporté à cet objet sera aussi visible à l'intérieur de l'objet `Map`.

{{EmbedInteractiveExample("pages/js/map-prototype-get.html")}}

## Syntaxe

    maMap.get(clé)

### Paramètres

- `clé`
  - : La clé de l'élément à renvoyer depuis l'objet `Map`.

### Valeur de retour

L'élément associée à la clé donnée ou {{jsxref("undefined")}} si la clé ne fait pas partie de l'objet `Map`.

## Exemples

```js
var maMap = new Map();
maMap.set("truc", "toto");

maMap.get("truc");     // Renvoie "toto".
maMap.get("machin");   // Renvoie undefined.
```

## Spécifications

| Spécification                                                                                | État                         | Commentaires         |
| -------------------------------------------------------------------------------------------- | ---------------------------- | -------------------- |
| {{SpecName('ES2015', '#sec-map.prototype.get', 'Map.prototype.get')}} | {{Spec2('ES2015')}}     | Définition initiale. |
| {{SpecName('ESDraft', '#sec-map.prototype.get', 'Map.prototype.get')}} | {{Spec2('ESDraft')}} |                      |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Map.get")}}

## Voir aussi

- {{jsxref("Map")}}
- {{jsxref("Map.prototype.set()")}}
- {{jsxref("Map.prototype.has()")}}
