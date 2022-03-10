---
title: Document.title
slug: Web/API/Document/title
translation_of: Web/API/Document/title
---
{{APIRef("DOM")}}

Obtient ou défini le titre de la page.

## Syntaxe

    var docTitle = document.title;

`title` est la chaîne contenant le titre de la page. Si le titre a déjà été modifié par `document.title`, cela retournera cette valeur. Sinon cela retournera le titre par défaut de la page (voir les {{Anch("Notes")}} ci-dessous).

    document.title = newTitle;

`newTitle` sera le nouveau titre de la page. Le changement de titre affectera également la valeur de retour de `document.title`, le titre de la page dans le navigateur (généralement le nom de l'onglet dans votre navigateur), et affectera également le DOM de la page (le contenu de la balise HTML `<title>`).

## Exemple

```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
</head>
<body>

<script>
alert(document.title); // Affiche "Hello World!"
document.title = "Goodbye World!";
alert(document.title); // Affiche "Goodbye World!"
</script>

</body>
</html>
```

## Notes

Cette propriété s'applique à HTML, SVG, XUL, et aux autres documents Gecko.

Pour les documents HTML, la valeur initiale de `document.title` est le texte de la balise `<title>`. Pour les documents XUL, c'est la valeur de l'attribut {{XULAttr("title")}} de {{XULElem("window")}} ou d'autres éléments parents de l'élément XUL.

En XUL, accéder à `document.title` avant que le document soit complètement chargé a des conséquences variables (`document.title` peut retourner une chaîne vide et définir `document.title` peut n'avoir aucun effet).

## Spécification

- [DOM Level 2 HTML: document.title](http://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-18446827)
- [HTML5](http://www.whatwg.org/html/#document.title)
