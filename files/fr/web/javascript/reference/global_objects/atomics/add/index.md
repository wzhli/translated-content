---
title: Atomics.add()
slug: Web/JavaScript/Reference/Global_Objects/Atomics/add
tags:
  - Atomics
  - JavaScript
  - Mémoire partagée
  - Méthode
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Atomics/add
original_slug: Web/JavaScript/Reference/Objets_globaux/Atomics/add
---
{{JSRef}}

La méthode statique **`Atomics.add()`** ajoute une valeur donnée à un élément du tableau à une position donnée. Elle renvoie l'ancienne valeur qui était contenue à cet emplacement. Cette opération atomique garantit qu'aucune autre opération d'écriture n'est appliquée tant que la valeur modifiée n'est pas écrite.

{{EmbedInteractiveExample("pages/js/atomics-add.html")}}

## Syntaxe

    Atomics.add(typedArray, index, valeur)

### Paramètres

- `typedArray`
  - : Un tableau typé entier partagé parmi {{jsxref("Int8Array")}}, {{jsxref("Uint8Array")}}, {{jsxref("Int16Array")}}, {{jsxref("Uint16Array")}}, {{jsxref("Int32Array")}} ou {{jsxref("Uint32Array")}}.
- `index`
  - : La position du tableau `typedArray` auquel on souhaite ajouter une `valeur`.
- `valeur`
  - : La valeur à ajouter.

### Valeur de retour

L'ancienne valeur qui était contenue à (`typedArray[index]`).

### Exceptions levées

- Cette méthode lève {{jsxref("TypeError")}} si le type de `typedArray` n'est pas un des types entiers autorisés.
- Cette méthode lève {{jsxref("TypeError")}} si `typedArray` n'est pas tableau typé partagé.
- Cette méthode lève {{jsxref("RangeError")}} si `index` est en dehors des limites de `typedArray`.

## Exemples

```js
var sab = new SharedArrayBuffer(1024);
var ta = new Uint8Array(sab);

Atomics.add(ta, 0, 12); // renvoie 0, l'ancienne valeur
Atomics.load(ta, 0);    // 12
```

## Spécifications

| Spécification                                                                | État                         | Commentaires                     |
| ---------------------------------------------------------------------------- | ---------------------------- | -------------------------------- |
| {{SpecName('ESDraft', '#sec-atomics.add', 'Atomics.add')}} | {{Spec2('ESDraft')}} | Définition initiale avec ES2017. |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Atomics.add")}}

## Voir aussi

- {{jsxref("Atomics")}}
- {{jsxref("Atomics.sub()")}}
