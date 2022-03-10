---
title: Math.LN10
slug: Web/JavaScript/Reference/Global_Objects/Math/LN10
tags:
  - JavaScript
  - Math
  - Propriété
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Math/LN10
original_slug: Web/JavaScript/Reference/Objets_globaux/Math/LN10
---
{{JSRef}}

La propriété **`Math.LN10`** représente la valeur du logarithme naturel de 10, environ 2.302 :

<math display="block"><semantics><mrow><mstyle mathvariant="monospace"><mi>Math.LN10</mi></mstyle><mo>=</mo><mo lspace="0em" rspace="0em">ln</mo><mo stretchy="false">(</mo><mn>10</mn><mo stretchy="false">)</mo><mo>≈</mo><mn>2.302</mn></mrow><annotation encoding="TeX">\mathtt{\mi{Math.LN10}} = \ln(10) \approx 2.302</annotation></semantics></math>

{{EmbedInteractiveExample("pages/js/math-ln10.html")}}{{js_property_attributes(0,0,0)}}

## Description

`LN10` est une propriété statique de `Math`, elle doit toujours être utilisée avec la syntaxe `Math.LN10`, et ne pas être appelée comme propriété d'un autre objet qui aurait été créé (`Math` n'est pas un constructeur).

## Exemples

### Utiliser `Math.LN10`

La fonction suivante renvoie le logarithme naturel de 10 :

```js
function getNatLog10() {
   return Math.LN10;
}

getNatLog10(); // 2.302585092994046
```

## Spécifications

| Spécification                                                            | Statut                       | Commentaires                                          |
| ------------------------------------------------------------------------ | ---------------------------- | ----------------------------------------------------- |
| {{SpecName('ES1')}}                                                 | {{Spec2('ES1')}}         | Définition initiale. Implémentée avec JavaScript 1.0. |
| {{SpecName('ES5.1', '#sec-15.8.1.2', 'Math.LN10')}}     | {{Spec2('ES5.1')}}     |                                                       |
| {{SpecName('ES6', '#sec-math.ln10', 'Math.LN10')}}     | {{Spec2('ES6')}}         |                                                       |
| {{SpecName('ESDraft', '#sec-math.ln10', 'Math.LN10')}} | {{Spec2('ESDraft')}} |                                                       |

## Compatibilité des navigateurs

{{Compat("javascript.builtins.Math.LN10")}}

## Voir aussi

- {{jsxref("Math.exp()")}}
- {{jsxref("Math.log()")}}
- {{jsxref("Math.log10()")}}
