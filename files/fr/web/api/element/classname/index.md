---
title: element.className
slug: Web/API/Element/className
tags:
  - API
  - Classe
  - DOM
  - Element
  - Propriétés
translation_of: Web/API/Element/className
---
{{APIRef("DOM")}}

La propriété **className** de l'interface {{domxref("Element")}} récupère et définit la valeur de l'[attribut `class`](/fr/docs/Web/HTML/Attributs_universels/class) de l'élément spécifié.

## Syntaxe

    var cName = elementNodeReference.className;
    elementNodeReference.className = cName;

- `cName` est une String (chaîne de caractères) représentant la classe (ou les classes séparées par des espaces) de l'élément courant.

## Exemple

```js
let elm = document.getElementById('item');

if(elm.className === 'active'){
    elm.className = 'inactive';
} else {
    elm.className = 'active';
}
```

## Notes

Le nom `className` est utilisé pour cette propriété au lieu de `class` à cause de conflits éventuels avec le mot-clé « class » dans beaucoup de langages utilisés pour manipuler le DOM.

`className` peut être une instance de {{domxref("SVGAnimatedString")}} si l'`element` est un {{domxref("SVGElement")}}. Dans ce cas là, l'usage de `className` ne fonctionnera pas, il sera donc préférable d'utiliser {{domxref("Element.getAttribute")}} et {{domxref("Element.setAttribute")}} si vous utilisez des élements SVG.

```js
elm.setAttribute('class', elm.getAttribute('class'))
```

## Spécifications

| Spécification                                                                                    | Statut                           | Commentaire          |
| ------------------------------------------------------------------------------------------------ | -------------------------------- | -------------------- |
| {{SpecName("DOM WHATWG", "#dom-element-classname", "element.className")}} | {{Spec2("DOM WHATWG")}} |                      |
| {{SpecName("DOM4", "#dom-element-classname", "element.className")}}         | {{Spec2("DOM4")}}         |                      |
| {{SpecName("DOM2 HTML", "html.html#ID-95362176", "element.className")}} | {{Spec2("DOM2 HTML")}}     | Définition initiale. |

## Compatibilité des navigateurs

{{Compat("api.Element.className")}}

## Voir aussi

- {{domxref("element.classList")}}
