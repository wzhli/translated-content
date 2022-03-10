---
title: ':optional'
slug: Web/CSS/:optional
tags:
  - CSS
  - Pseudo-classe
  - Reference
translation_of: Web/CSS/:optional
---
{{CSSRef}}

La [pseudo-classe](/fr/docs/Web/CSS/Pseudo-classes) **`:optional`** permet de cibler les éléments {{HTMLElement("input")}} ou {{HTMLElement("textarea")}}  pour lesquels l'attribut {{htmlattrxref("required","input")}} n'est pas activé. Cela permet ainsi d'indiquer et de mettre en forme les champs facultatifs d'un formulaire.

```css
/* Cible les élméents <input> qui sont optionnels */
/* c'est-à-dire qui n'ont pas d'attribut required */
input:optional {
  border: 1px dashed black;
}
```

> **Note :** Afin de mettre en forme les champs obligatoires, on pourra utiliser la pseudo-classe {{cssxref(":required")}}.

## Syntaxe

{{csssyntax}}

## Exemples

### CSS

```css
input {
  border-width: 3px;
}
input:optional {
  border-color: #008000;
}
input:required {
  border-color: #800000;
}
```

### HTML

```html
<form>
  <label for="url-input">Tapez une URL :</label>
  <input type="url" id="url-input">
  <br>
  <br>
  <label for="email-input">Tapez une adresse électronique :</label>
  <input type="email" id="email-input" required>
</form>
```

### Résultat

{{EmbedLiveSample('Exemples','100%',150)}}

## Accessibilité

Si un formulaire ({{HTMLElement("form")}}) contient des champs ({{htmlelement("input")}}) optionnels, les champs obligatoires doivent être indiqués avec l'attribut {{htmlattrxref("input","required")}}. Ainsi, les personnes utilisant des outils d'assistance (par exemple un lecteur d'écran) pourront savoir que ces champs ont besoin d'un contenu valide afin de pouvoir envoyer le formulaire.

Les champs obligatoires devraient également être indiqués visuellement et cette indication ne doit pas uniquement être fournie avec une couleur. Généralement, un texte descriptif ou une icône est utilisé.

- [Explications des recommendation WCAG 1.4](/fr/docs/Web/Accessibility/Understanding_WCAG/Perceivable#Guideline_1.4_Make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Spécifications

| Spécification                                                                                | État                                 | Commentaires                                                                  |
| -------------------------------------------------------------------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------- |
| {{SpecName('HTML WHATWG', '#selector-optional', ':optional')}}         | {{Spec2('HTML WHATWG')}}     | Aucune modification.                                                          |
| {{SpecName('HTML5 W3C', '#selector-optional', ':optional')}}             | {{Spec2('HTML5 W3C')}}         | Définition de la sémantique relative à HTML et aux contraintes de validation. |
| {{SpecName('CSS4 Selectors', '#opt-pseudos', ':optional')}}             | {{Spec2('CSS4 Selectors')}} | Aucune modification.                                                          |
| {{SpecName('CSS3 Basic UI', '#pseudo-required-value', ':optional')}} | {{Spec2('CSS3 Basic UI')}} | Définition de la pseudo-classe mais sans la sémantique associée.              |

## Compatibilité des navigateurs

{{Compat("css.selectors.optional")}}

## Voir aussi

- {{cssxref(":required")}}
- {{cssxref(":invalid")}}
- {{cssxref(":valid")}}
- [La validation des données de formulaire](/fr/docs/Web/Guide/HTML/Formulaires/Validation_donnees_formulaire)
