---
title: DataView.prototype.getUint8()
slug: Web/JavaScript/Reference/Global_Objects/DataView/getUint8
tags:
  - DataView
  - JavaScript
  - Méthode
  - Prototype
  - Reference
  - TypedArrays
translation_of: Web/JavaScript/Reference/Global_Objects/DataView/getUint8
original_slug: Web/JavaScript/Reference/Objets_globaux/DataView/getUint8
---
{{JSRef}}

La méthode **`getUint8()`** permet de lire un entier non-signé sur 8 bits à l'octet donné par rapport au début de la {{jsxref("DataView")}}.

{{EmbedInteractiveExample("pages/js/dataview-getuint8.html")}}

## Syntaxe

    dataview.getUint8(positionOctet)

### Paramètres

- `positionOctet`
  - : La position, exprimée en nombre d'octets depuis le début de la vue, à laquelle lire les données.

### Valeur de retour

Un entier sur 8 bits, non-signé.

### Erreurs renvoyées

- {{jsxref("RangeError")}}
  - : Renvoyée si `positionOctet` est tel qu'il est en dehors de la vue.

## Description

Il n'y a pas de contrainte d'alignement, les valeurs codées sur plusieurs octets peuvent être obtenues depuis n'importe quelle position.

## Exemples

### Utilisation de la méthode `getUint8`

```js
var buffer = new ArrayBuffer(8);
var dataview = new DataView(buffer);
dataview.getUint8(1); // 0
```

## Spécifications

| Spécification                                                                                                            | État                             | Commentaires                                    |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------- | ----------------------------------------------- |
| {{SpecName('Typed Array')}}                                                                                     | {{Spec2('Typed Array')}} | Remplacée dans ECMAScript 2015.                 |
| {{SpecName('ES2015', '#sec-dataview.prototype.getuint8', 'DataView.prototype.getUint8')}} | {{Spec2('ES2015')}}         | Définition initiale au sein d'un standard ECMA. |
| {{SpecName('ESDraft', '#sec-dataview.prototype.getuint8', 'DataView.prototype.getUint8')}} | {{Spec2('ESDraft')}}     |                                                 |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.DataView.getUint8")}}

## Voir aussi

- {{jsxref("DataView")}}
- {{jsxref("ArrayBuffer")}}
