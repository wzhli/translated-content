---
title: Reflect.has()
slug: Web/JavaScript/Reference/Global_Objects/Reflect/has
tags:
  - ECMAScript 2015
  - JavaScript
  - Méthode
  - Reference
  - Reflect
translation_of: Web/JavaScript/Reference/Global_Objects/Reflect/has
original_slug: Web/JavaScript/Reference/Objets_globaux/Reflect/has
---
{{JSRef}}

La méthode statique **`Reflect.has()`** fonctionne comme [l'opérateur `in`](/fr/docs/Web/JavaScript/Reference/Opérateurs/L_opérateur_in) mais sous forme d'une fonction.

{{EmbedInteractiveExample("pages/js/reflect-has.html")}}

## Syntaxe

    Reflect.has(cible, cléPropriété)

### Paramètres

- `cible`
  - : L'objet cible dont on souhaite savoir s'il contient la propriété donnée.
- `cléPropriété`
  - : Le nom de la propriété dont on souhaite vérifier la présence.

### Valeur de retour

Un {{jsxref("Boolean","booléen","",1)}} qui indique si la propriété recherchée est présente sur l'objet cible.

### Exceptions

Une erreur {{jsxref("TypeError")}} si `cible` n'est pas un {{jsxref("Object")}}.

## Description

La méthode `Reflect.has` vous permet de vérifier si une propriété est présente sur un objet. C'est une fonction qui agit comme l'opérateur [`in`](/fr/docs/Web/JavaScript/Reference/Opérateurs/L_opérateur_in).

## Exemples

```js
Reflect.has({x: 0}, "x"); // true
Reflect.has({x: 0}, "y"); // false

// renvoie true pour les propriétés présentes
// grâce à la chaîne de prototypes
Reflect.has({x: 0}, "toString");

// Proxy avec la méthode .has()
obj = new Proxy({}, {
  has(t, k) { return k.startsWith("bou"); }
});
Reflect.has(obj, "bouchon"); // true
Reflect.has(obj, "bonbon");  // false
```

## Spécifications

| Spécification                                                                | État                         | Commentaires         |
| ---------------------------------------------------------------------------- | ---------------------------- | -------------------- |
| {{SpecName('ES2015', '#sec-reflect.has', 'Reflect.has')}} | {{Spec2('ES2015')}}     | Définition initiale. |
| {{SpecName('ESDraft', '#sec-reflect.has', 'Reflect.has')}} | {{Spec2('ESDraft')}} |                      |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Reflect.has")}}

## Voir aussi

- {{jsxref("Reflect")}}
- [Opérateur `in`](/fr/docs/Web/JavaScript/Reference/Opérateurs/L_opérateur_in)
