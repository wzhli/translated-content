---
title: selection
slug: Web/API/Selection
translation_of: Web/API/Selection
---
{{ ApiRef() }}

### Résumé

La classe de l'objet retourné par [`window.getSelection()`](Window/getSelection), [`document.getSelection()`](/fr/docs/Web/API/Document/getSelection) et d'autres méthodes.

### Description

Un objet `selection` représente les [plages](range) sélectionnées par l'utilisateur. Habituellement, il ne contient qu'une seule plage accessible comme ceci :

    range = sel.getRangeAt(0);

L'appel de la méthode [`toString()`](Selection/toString) renvoie le texte contenu dans la sélection. Cet appel peut être automatique, par exemple lorsque l'objet est passé à la fonction alert() :

    selObj = window.getSelection();
    window.alert(selObj);

### Glossaire

Autres mots clés utilisés dans cette section.

- anchor (ancre)
  - : L'« ancre » d'une sélection est son point de départ. Pour une sélection avec la souris, l'« ancre » correspond à l'endroit initialement pressé par le bouton de la souris. Quand l'utilisateur modifie la sélection à la souris ou au clavier, l'« ancre » ne change pas.
- focus (focus)
  - : Le « focus » d'une sélection est son point d'arrivée. Pour une sélection avec la souris, le « focus » correspond à l'endroit où le bouton de la souris est relaché. Quand l'utilisateur modifie la sélection à la souris ou au clavier, le « focus » pointe la fin de la sélection modifiée.
- range (plage)
  - : Une « plage » est une partie contigüe d'un document. Une « plage » peut contenir aussi bien des nœuds entiers que des portions de nœuds, comme un extrait de nœud texte. Habituellement, un utilisateur n'effectuera qu'une seule sélection à la fois, mais il lui est possible de sélectionner plusieurs « plages » (par ex. en utilisant la touche Ctrl). Une « plage » est obtenue depuis une sélection par l'objet [range](range). Les objets `range` peuvent également être créés via le DOM et ajoutés ou supprimés d'une sélection par programmation.

### Propriétés

- [anchorNode](/fr/docs/Web/API/Selection/anchorNode)
  - : Renvoie le nœud d'où la sélection commence.
- [anchorOffset](/fr/docs/Web/API/Selection/anchorOffset)
  - : Renvoie un nombre correspondant au décalage de l'« ancre » de la sélection au sein de l'`anchorNode`. Si l'`anchorNode` est un noeud texte, il s'agit du nombre de caractères précédants l'« ancre » au sein de l'`anchorNode`. Si l'`anchorNode` est un élément, il s'agit du nombre de noeuds enfants de l'`anchorNode` précédant l'« ancre ».
- [focusNode](/fr/docs/Web/API/Selection/focusNode)
  - : Renvoie le nœud où la sélection se termine.
- [focusOffset](/fr/docs/Web/API/Selection/focusOffset)
  - : Renvoie un nombre correspondant au décalage du « focus » de la sélection au sein du focus`Node`. Si le focus`Node` est un noeud texte, il s'agit du nombre de caractères précédants le « focus » au sein du focus`Node`. Si le focusNode est un élément, il s'agit du nombre de noeuds enfants du focus`Node` précédant le « focus ».
- [isCollapsed](/fr/docs/Web/API/Selection/isCollapsed)
  - : Renvoie un booléen indiquant si le point de départ et d'arrivée sont à la même position.
- [rangeCount](/fr/docs/Web/API/Selection/rangeCount)
  - : Renvoie le nombre de « plages » dans la sélection.

### Méthodes

- [getRangeAt](/fr/docs/Web/API/Selection/getRangeAt)
  - : Renvoie un objet range représentant une des « plages » actuellement sélectionnée.
- [collapse](/fr/docs/Web/API/Selection/collapse)
  - : Réduit la sélection courante à un simple point.
- [extend](/fr/docs/Web/API/Selection/extend)
  - : Déplace le « focus » de la sélection à un endroit spécifié.
- [collapseToStart](/fr/docs/Web/API/Selection/collapseToStart)
  - : Déplace le « focus » de la sélection au même point que l'« ancre ».
- [collapseToEnd](/fr/docs/Web/API/Selection/collapseToEnd)
  - : Déplace l'« ancre » de la sélection au même point que le « focus ». Le « focus » ne bouge pas.
- [selectAllChildren](/fr/docs/Web/API/Selection/selectAllChildren)
  - : Ajoute tous les enfants d'un nœud spécifié à la sélection.
- [addRange](/fr/docs/Web/API/Selection/addRange)
  - : Un objet range devant être ajouté à la sélection.
- [removeRange](/fr/docs/Web/API/Selection/removeRange)
  - : Supprime une « plage » de la sélection.
- [removeAllRanges](/fr/docs/Web/API/Selection/removeAllRanges)
  - : Supprime toutes les « plages » de la sélection.
- [deleteFromDocument](/fr/docs/Web/API/Selection/deleteFromDocument)
  - : Efface le contenu de la sélection du document.
- [selectionLanguageChange](/fr/docs/Web/API/Selection/selectionLanguageChange)
  - :
- [toString](/fr/docs/Web/API/Selection/toString)
  - : Renvoie une chaîne de caractères représentant l'actuel objet `selection`, i.e. le texte sélectionné.
- [containsNode](/fr/docs/Web/API/Selection/containsNode)
  - : Indique si un nœud donné appartient à la sélection.

## Compatibilité des navigateurs

{{Compat("api.Selection")}}

### Voir aussi

[window.getSelection](Window/getSelection), [`document.getSelection()`](/fr/docs/Web/API/Document/getSelection),[Range](range)

### Liens externes

- [Définition IDL dans Mozilla cross-reference](http://lxr.mozilla.org/mozilla/source/content/base/public/nsISelection.idl)
