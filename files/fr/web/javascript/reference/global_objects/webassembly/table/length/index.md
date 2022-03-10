---
title: WebAssembly.Table.prototype.length
slug: Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/length
tags:
  - API
  - JavaScript
  - Propriété
  - Reference
  - WebAssembly
  - table
translation_of: Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/length
original_slug: Web/JavaScript/Reference/Objets_globaux/WebAssembly/Table/length
---
{{JSRef}}

La propriété **`length`**, rattachée au prototype de l'objet {{jsxref("WebAssembly.Table")}}, renvoie la longueur du tableau WebAssembly, c'est-à-dire le nombre d'éléments qui y sont stockées.

## Syntaxe

    table.length;

## Exemples

Avec l'instruction qui suit, on crée un tableau WebAssembly avec une taille initiale de 2 éléments et avec une taille maximale de 10.

```js
var table = new WebAssembly.Table({ element: "anyfunc", initial: 2, maximum: 10 });
```

On peut ensuite étendre le tableau d'un élément :

```js
console.log(table.length);   // "2"
console.log(table.grow(1));  // "2"
console.log(table.length);   // "3"
```

## Spécifications

| Spécification                                                                                        | État                                 | Commentaires                                       |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------ | -------------------------------------------------- |
| {{SpecName('WebAssembly JS', '#webassemblytableprototypelength', 'length')}} | {{Spec2('WebAssembly JS')}} | Brouillon de définition initiale pour WebAssembly. |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.WebAssembly.Table.length")}}

## Voir aussi

- [Le portail WebAssembly](/fr/docs/WebAssembly)
- [Les concepts relatifs à WebAssembly](/fr/docs/WebAssembly/Concepts)
- [Utiliser l'API JavaScript WebAssembly](/fr/docs/WebAssembly/Using_the_JavaScript_API)
