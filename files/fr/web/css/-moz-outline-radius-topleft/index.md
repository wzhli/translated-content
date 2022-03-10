---
title: '-moz-outline-radius-topleft'
slug: Web/CSS/-moz-outline-radius-topleft
tags:
  - CSS
  - Non-standard
  - Propriété
  - Reference
translation_of: Web/CSS/-moz-outline-radius-topleft
---
{{Non-standard_header}}{{CSSRef}}

Dans les applications Mozilla, la propriété **`-moz-outline-radius-topleft`** définit l'arrondi du coin supérieur gauche du contour.

## Exemples

### HTML

```html
<p>Observez le coin supérieur gauche de ce paragraphe.</p>
```

### CSS

```css
p {
  margin: 5px;
  border: solid cyan;
  outline: dotted red;
  -moz-outline-radius-topleft: 2em;
}
```

### Résultat

{{EmbedLiveSample("Exemples")}}

> **Note :** Cette propriété étant spécifique à Firefox, l'exemple ci-avant ne fonctionnera pas dans un autre navigateur.

## Spécifications

Cette propriété est une propriété propriétaire liée à Mozilla/Gecko et ne fait partie d'aucune spécification.

{{cssinfo}}

## Voir aussi

- La propriété raccourcie {{cssxref("-moz-outline-radius")}}
- La propriété standard {{cssxref("outline")}}
