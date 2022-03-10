---
title: Reflect.getPrototypeOf()
slug: Web/JavaScript/Reference/Global_Objects/Reflect/getPrototypeOf
tags:
  - ECMAScript 2015
  - JavaScript
  - Méthode
  - Reference
  - Reflect
translation_of: Web/JavaScript/Reference/Global_Objects/Reflect/getPrototypeOf
original_slug: Web/JavaScript/Reference/Objets_globaux/Reflect/getPrototypeOf
---
{{JSRef}}

La méthode statique **`Reflect.getPrototypeOf()`** est semblable à la méthode {{jsxref("Object.getPrototypeOf()")}}. Elle renvoie le prototype (c'est-à-dire la valeur de la propriété interne `[[Prototype]]`) de l'objet donné.

{{EmbedInteractiveExample("pages/js/reflect-getprototypeof.html")}}

## Syntaxe

    Reflect.getPrototypeOf(cible)

### Paramètres

- `cible`
  - : L'objet cible dont on souhaite obtenir le prototype.

### Valeur de retour

Le prototype de l'objet ou {{jsxref("null")}} s'il n'y a aucune propriété héritée.

### Exceptions levées

Une erreur {{jsxref("TypeError")}} si `cible` n'est pas un {{jsxref("Object")}}.

## Description

La méthode `Reflect.getPrototypeOf` renvoie le prototype (qui correspond en réalité à la valeur de la propriété interne `[[Prototype]]`) de l'objet passé en argument.

## Exemples

### Utiliser `Reflect.getPrototypeOf()`

```js
Reflect.getPrototypeOf({}); // Object.prototype
Reflect.getPrototypeOf(Object.prototype); // null
Reflect.getPrototypeOf(Object.create(null)); // null
```

### Comparaison avec `Object.getPrototypeOf()`

```js
// Résultat identiques pour les objets
Object.getPrototypeOf({});  // Object.prototype
Reflect.getPrototypeOf({}); // Object.prototype

// Exception levée avec ES5 pour les valeurs qui ne sont pas des objets
Object.getPrototypeOf('toto');  // Throws TypeError
Reflect.getPrototypeOf('toto'); // Throws TypeError

// Avec ES2015 (ES6), seul Reflect lève une exception
// Object convertit automatiquement les valeurs en objets
Object.getPrototypeOf('toto');  // String.prototype
Reflect.getPrototypeOf('toto'); // Throws TypeError

// Pour obtenir le même effet qu'avec Object en ES2015, il
// faut ajouter une opération de conversion explicite
Reflect.getPrototypeOf(Object('toto')); // String.prototype
```

## Spécifications

| Spécification                                                                                                | État                         | Commentaires         |
| ------------------------------------------------------------------------------------------------------------ | ---------------------------- | -------------------- |
| {{SpecName('ES2015', '#sec-reflect.getprototypeof', 'Reflect.getPrototypeOf')}}     | {{Spec2('ES2015')}}     | Définition initiale. |
| {{SpecName('ESDraft', '#sec-reflect.getprototypeof', 'Reflect.getPrototypeOf')}} | {{Spec2('ESDraft')}} |                      |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Reflect.getPrototypeOf")}}

## Voir aussi

- {{jsxref("Reflect")}}
- {{jsxref("Object.getPrototypeOf()")}}
