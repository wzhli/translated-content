---
title: TypedArray.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/TypedArray/toString
tags:
  - ECMAScript 2015
  - JavaScript
  - Méthode
  - Prototype
  - Reference
  - TypedArray
translation_of: Web/JavaScript/Reference/Global_Objects/TypedArray/toString
original_slug: Web/JavaScript/Reference/Objets_globaux/TypedArray/toString
---
{{JSRef}}

La méthode **`toString()`** renvoie une chaîne de caractères qui représente le tableau typé et ses éléments. Cette méthode utilise le même algorithme que {{jsxref("Array.prototype.toString()")}}_._ Dans la suite de cet article, _TypedArray_ fait référence à [l'un des types de tableau typé listés ici](/fr/docs/Web/JavaScript/Reference/Objets_globaux/TypedArray#Les_objets_TypedArray).

{{EmbedInteractiveExample("pages/js/typedarray-tostring.html")}}

## Syntaxe

    typedarray.toString()

### Valeur de retour

Une chaîne de caractères qui représente les éléments du tableau typé.

## Description

Les objets {{jsxref("TypedArray")}} surchargent la méthode `toString` de {{jsxref("Object")}}. Pour les objets `TypedArray`, la méthode `toString` fusionne le tableau et renovoie une chaîne de caractères contenant les éléments du tableau, chacun séparés par une virgule. Par exemple :

```js
var numbers = new Uint8Array([2, 5, 8, 1, 4])
numbers.toString(); // "2,5,8,1,4"
```

JavaScript appelle automatiquement la méthode `toString()` lorsqu'un tableau typé doit être manipulé sous une forme textuelle (par exemple lorsqu'il est utilisé avec une chaîne de caractères dans une concaténation).

### Compatibilité

Si un navigateur ne prend pas encore en charge la méthode `TypedArray.prototype.toString()`, le moteur JavaScript utilisera la méthode `toString` rattachée à {{jsxref("Object")}} :

```js
var numbers = new Uint8Array([2, 5, 8, 1, 4])
numbers.toString(); // "[object Uint8Array]"
```

## Spécifications

| Spécification                                                                                                                    | État                         | Commentaires         |
| -------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | -------------------- |
| {{SpecName('ES2015', '#sec-%typedarray%.prototype.tostring', 'TypedArray.prototype.toString')}} | {{Spec2('ES2015')}}     | Définition initiale. |
| {{SpecName('ESDraft', '#sec-%typedarray%.prototype.tostring', 'Array.prototype.toString')}}         | {{Spec2('ESDraft')}} |                      |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.TypedArray.toString")}}

## Voir aussi

- {{jsxref("TypedArray.prototype.join()")}}
