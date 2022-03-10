---
title: Math.min()
slug: Web/JavaScript/Reference/Global_Objects/Math/min
tags:
  - JavaScript
  - Math
  - Méthode
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Math/min
original_slug: Web/JavaScript/Reference/Objets_globaux/Math/min
---
{{JSRef}}

La fonction **`Math.min()`** renvoie le plus petit nombre d'une série de 0 ou plusieurs nombres ou bien {{jsxref("NaN")}} si au moins un des arguments fourni n'est pas un nombre ou ne peut pas être converti en nombre.

{{EmbedInteractiveExample("pages/js/math-min.html")}}

## Syntaxe

    Math.min([valeur1[,valeur2, ...]])

### Paramètres

- `valeur1, valeur2, ...`
  - : Des nombres.

### Valeur de retour

Le plus petit des nombres passés en arguments. S'il existe un argument qui ne peut pas être converti en nombre, c'est {{jsxref("NaN")}} qui sera renvoyé. Le résultat sera {{jsxref("Infinity")}} si aucun paramètre n'est fourni.

## Description

`min()` est une méthode statique de `Math`, elle doit toujours être utilisée avec la syntaxe `Math.min()` et ne doit pas être utilisée comme la méthode d'un objet qui aurait été créé (`Math` n'est pas un constructeur).

Si aucun argument n'est fourni, le résultat renvoyé par la fonction sera {{jsxref("Infinity")}}.

Si au moins un des arguments ne peut pas être converti en un nombre, le résultat sera {{jsxref("NaN")}}.

## Exemples

### Utiliser `Math.min()`

Dans cet exemple, on trouve le minimum de x et y et on affecte cette valeur à z :

```js
var x = 10, y = -20;
var z = Math.min(x, y);
```

### Ramener une valeur dans un intervalle (_clipping_) avec `Math.min()`

`Math.min()` est souvent utilisée afin de ramener une certaine valeur dans un intervalle donné. Par exemple :

```js
var x = f(toto);

if (x > limite) {
  x = limite;
}
```

peut s'écrire

```js
var x = Math.min(f(toto), limite);
```

{{jsxref("Math.max()")}} peut être utilisée de façon semblable pour ramener une valeur vers un minimum d'un intervalle donné.

## Spécifications

| Spécification                                                        | Statut                       | Commentaires                                          |
| -------------------------------------------------------------------- | ---------------------------- | ----------------------------------------------------- |
| {{SpecName('ES1')}}                                             | {{Spec2('ES1')}}         | Définition initiale. Implémentée avec JavaScript 1.0. |
| {{SpecName('ES5.1', '#sec-15.8.2.12', 'Math.min')}} | {{Spec2('ES5.1')}}     |                                                       |
| {{SpecName('ES6', '#sec-math.min', 'Math.min')}}     | {{Spec2('ES6')}}         |                                                       |
| {{SpecName('ESDraft', '#sec-math.min', 'Math.min')}} | {{Spec2('ESDraft')}} |                                                       |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Math.min")}}

## Voir aussi

- {{jsxref("Math.max()")}}
