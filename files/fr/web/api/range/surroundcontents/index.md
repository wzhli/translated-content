---
title: Range.surroundContents()
slug: Web/API/Range/surroundContents
translation_of: Web/API/Range/surroundContents
---
{{ApiRef("DOM")}}

La méthode **`Range.surroundContents()`** déplace le contenu du {{ domxref("Range") }} dans un nouveau nœud, plaçant le nouveau nœud au début du `range` spécifié.

Cette méthode est à peu près équivalente à :

```js
newNode.appendChild(range.extractContents());
range.insertNode(newNode)
```

Après déplacement, les bornes du `range` incluent `newNode`.

Cependant, une exception sera levée si le {{ domxref("Range") }} découpe un nœud non-{{ domxref("Text") }} sur une seule de ses bornes. C’est-à-dire que, contrairement à l’alternative ci-dessus, s’il y a des nœuds partiellement sélectionnés, ils ne seront pas clonés ; à la place, l’opération échouera.

## Syntaxe

    range.surroundContents(newNode);

### Paramètres

- _newNode_
  - : Un {{ domxref("Node") }} à insérer à l’emplacement du `range`.

## Exemple

```js
var range = document.createRange();
var newNode = document.createElement("p");

range.selectNode(document.getElementsByTagName("div").item(0));
range.surroundContents(newNode);
```

## Spécifications

| Spécification                                                                                                                                                | Statut                                       | Commentaire             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------- | ----------------------- |
| {{SpecName('DOM WHATWG', '#dom-range-surroundcontents', 'Range.surroundContents()')}}                                             | {{Spec2('DOM WHATWG')}}             | Pas de changement.      |
| {{SpecName('DOM2 Traversal_Range', 'ranges.html#Level2-Range-method-surroundContents', 'Range.surroundContents()')}} | {{Spec2('DOM2 Traversal_Range')}} | Spécification initiale. |

## Compatibilité des navigateurs

{{Compat("api.Range.surroundContents")}}

## Voir aussi

- [L’index des interfaces DOM](/fr/docs/DOM/DOM_Reference)
