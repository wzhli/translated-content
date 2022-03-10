---
title: CSSMediaRule
slug: Web/API/CSSMediaRule
tags:
  - API
  - CSSOM
  - Interface
  - Reference
translation_of: Web/API/CSSMediaRule
---
{{APIRef("CSSOM")}}

L'interface **`CSSMediaRule`** représente une seule règle CSS {{cssxref("@media")}}. Elle met en œuvre l'interface {{domxref("CSSConditionRule")}}, et donc l'interface {{domxref("CSSGroupingRule")}} et l'interface {{domxref("CSSRule")}} avec une valeur de type `4` (`CSSRule.MEDIA_RULE`).

## Syntaxe

La syntaxe est décrite en utilisant le format [WebIDL](http://dev.w3.org/2006/webapi/WebIDL/).

    interface CSSMediaRule : CSSConditionRule {
        readonly attribute MediaList media;
    }

## Propriétés

En tant que {{domxref("CSSConditionRule")}}, et donc à la fois {{domxref("CSSGroupingRule")}} et {{domxref("CSSRule")}}, `CSSMediaRule` implémente également les propriétés de ces interfaces. Elle a la propriété spécifique suivante :

- {{domxref("CSSMediaRule.media")}} {{readonlyinline}}
  - : Spécifie un {{domxref("MediaList")}} représentant le support de destination prévu pour les informations de style.

## Méthodes

En tant que {{domxref("CSSConditionRule") }}, et donc à la fois {{domxref("CSSGroupingRule")}} et {{domxref("CSSRule")}}, `CSSMediaRule` met également en œuvre les méthodes de cette interface. Elle n'a pas de méthodes spécifiques.

## Specifications

| Specification                                                                                                | Status                                   | Comment                                                             |
| ------------------------------------------------------------------------------------------------------------ | ---------------------------------------- | ------------------------------------------------------------------- |
| {{ SpecName('CSS3 Conditional', '#the-cssmediarule-interface', 'CSSMediaRule') }} | {{ Spec2('CSS3 Conditional')}} | Dérivé de la règle  {{domxref("CSSConditionRule")}}.       |
| {{ SpecName('CSSOM', '#the-cssmediarule-interface', 'CSSMediaRule') }}                 | {{ Spec2('CSSOM') }}             | Aucun changement par rapport à {{SpecName('DOM2 Style')}} |
| {{SpecName('DOM2 Style', 'css.html#CSS-CSSMediaRule', 'CSSMediaRule') }}             | {{ Spec2('DOM2 Style') }}         |                                                                     |

## Compatibilité des navigateurs

{{Compat("api.CSSMediaRule")}}
