---
title: text
slug: Web/XSLT/Element/text
tags:
  - Référence_XSLT
translation_of: Web/XSLT/Element/text
original_slug: Web/XSLT/text
---
{{ XsltRef() }}

L'élément `<xsl:text>` écrit un texte littéral dans l'arbre de sortie. Il peut contenir des `#PCDATA`, du texte littéral, et des références aux entités.

### Syntaxe

    <xsl:text disable-output-escaping="yes" | "no">
    	TEXTE
    </xsl:text>

### Attributs obligatoires

Aucun.

### Attribut optionnel

- `disable-output-escaping` (Netscape ne sérialise pas le résultat de la transformation - la « sortie » ci-dessous - aussi cet attribut importe peu dans ce contexte. Pour écrire des entités HTML, utilisez les valeurs numériques correspondantes à leur place, par exemple `&#160` pour `&nbsp`).
  - : Définit si les caractères spéciaux sont échappés lors de l'écriture vers la sortie. Les valeurs autorisées sont `yes` ou `no`. Si il est définit à `yes`, par exemple, le caractère \<tt>>\</tt> est envoyé tel quel ( `>` )et non comme `&gt`.

### Type

Instruction, apparaît dans un modèle.

### Définition

[XSLT 1.0, section 7.2](http://www.w3.org/TR/xslt#section-Creating-Text).

### Support Gecko

Supporté comme indiqué plus haut.
