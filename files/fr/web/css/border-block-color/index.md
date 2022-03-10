---
title: border-block-color
slug: Web/CSS/border-block-color
tags:
  - CSS
  - Experimental
  - Propriété
  - Propriété logique
  - Reference
translation_of: Web/CSS/border-block-color
---
{{CSSRef}}{{SeeCompatTable}}

La propriété **`border-block-color`** définit la couleur de la bordure d'un élément sur les côtés de l'axe de bloc. Cette propriété correspondra à différentes propriétés physiques pour les couleurs de la bordure selon le mode d'écriture de l'élément, sa direction et l'orientation du texte. Autrement dit, cette propriété logique peut correspondre à {{cssxref("border-top-color")}} et {{cssxref("border-bottom-color")}} ou à {{cssxref("border-right-color")}} et {{cssxref("border-left-color")}} selon les valeurs des propriétés {{cssxref("writing-mode")}}, {{cssxref("direction")}} et {{cssxref("text-orientation")}}.

```css
border-block-color: yellow;
border-block-color: #F5F6F7;
```

Pour définir la couleur de la bordure sur l'autre dimension, on pourra utiliser la propriété logique {{cssxref("border-inline-color")}} qui définit {{cssxref("border-inline-start-color")}} et {{cssxref("border-inline-end-color")}}.

## Syntaxe

### Valeurs

- `<'color'>`
  - : La couleur de la bordure. Voir {{cssxref("color")}}.

### Syntaxe formelle

{{csssyntax}}

## Exemples

### CSS

```css
div {
  background-color: yellow;
  width: 120px;
  height: 120px;
}

.texteExemple {
  writing-mode: vertical-lr;
  border: 10px solid blue;
  border-block-color: red;
}
```

### HTML

```html
<div>
  <p class="texteExemple">Texte d'exemple</p>
</div>
```

### Résultat

{{EmbedLiveSample("Exemples", 140, 140)}}

## Spécifications

| Spécification                                                                                                            | État                                             | Commentaires         |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------ | -------------------- |
| {{SpecName("CSS Logical Properties", "#propdef-border-block-color", "border-block-color")}} | {{Spec2("CSS Logical Properties")}} | Définition initiale. |

{{cssinfo}}

## Compatibilité des navigateurs

{{Compat("css.properties.border-block-color")}}

## Voir aussi

- Les propriétés physiques qui peuvent correspondre à cette propriété :

  - {{cssxref("border-top-color")}},
  - {{cssxref("border-right-color")}},
  - {{cssxref("border-bottom-color")}},
  - {{cssxref("border-left-color")}}.

- Les propriétés relatives aux propriétés logiques : {{cssxref("writing-mode")}}, {{cssxref("direction")}}, {{cssxref("text-orientation")}}
- {{bug("1297097")}}
