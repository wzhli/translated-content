---
title: Math.SQRT1_2
slug: Web/JavaScript/Reference/Global_Objects/Math/SQRT1_2
tags:
  - JavaScript
  - Math
  - Propriété
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Math/SQRT1_2
original_slug: Web/JavaScript/Reference/Objets_globaux/Math/SQRT1_2
---
{{JSRef}}

La propriété **`Math.SQRT1_2`** représente la racine carrée d'1/2 et vaut environ 0.707 :

<math display="block"><semantics><mrow><mstyle mathvariant="monospace"><mi>Math.SQRT1_2</mi></mstyle><mo>=</mo><msqrt><mfrac><mn>1</mn><mn>2</mn></mfrac></msqrt><mo>=</mo><mfrac><mn>1</mn><msqrt><mn>2</mn></msqrt></mfrac><mo>≈</mo><mn>0.707</mn></mrow><annotation encoding="TeX">\mathtt{\mi{Math.SQRT1_2}} = \sqrt{\frac{1}{2}} = \frac{1}{\sqrt{2}} \approx 0.707</annotation></semantics></math>

{{EmbedInteractiveExample("pages/js/math-sqrt1_2.html")}}{{js_property_attributes(0,0,0)}}

## Description

`SQRT1_2` est une propriété statique de `Math` et doit toujours être utilisée avec la syntaxe `Math.SQRT1_2`. Elle ne doit pas être obtenue à partir d'un autre objet qui aurait été créé (`Math` n'est pas un constructeur).

## Exemples

La fonction suivante renvoie la valeur de cette constante :

```js
function getRoot1_2() {
   return Math.SQRT1_2;
}

getRoot1_2(); // 0.7071067811865476
```

## Spécifications

| Spécification                                                                    | Statut                       | Commentaires                                          |
| -------------------------------------------------------------------------------- | ---------------------------- | ----------------------------------------------------- |
| {{SpecName('ES1')}}                                                         | {{Spec2('ES1')}}         | Définition initiale. Implémentée avec JavaScript 1.0. |
| {{SpecName('ES5.1', '#sec-15.8.1.7', 'Math.SQRT1_2')}}         | {{Spec2('ES5.1')}}     |                                                       |
| {{SpecName('ES6', '#sec-math.sqrt1_2', 'Math.SQRT1_2')}}     | {{Spec2('ES6')}}         |                                                       |
| {{SpecName('ESDraft', '#sec-math.sqrt1_2', 'Math.SQRT1_2')}} | {{Spec2('ESDraft')}} |                                                       |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Math.SQRT1_2")}}

## Voir aussi

- {{jsxref("Math.pow()")}}
- {{jsxref("Math.sqrt()")}}
