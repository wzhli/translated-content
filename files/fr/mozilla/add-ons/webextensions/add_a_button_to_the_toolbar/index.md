---
title: Ajouter un bouton à la barre d'outils
slug: Mozilla/Add-ons/WebExtensions/Add_a_button_to_the_toolbar
tags:
  - WebExtensions
translation_of: Mozilla/Add-ons/WebExtensions/Add_a_button_to_the_toolbar
original_slug: Mozilla/Add-ons/WebExtensions/Ajouter_un_bouton_a_la_barre_d_outils
---
{{AddonSidebar}}

Les boutons de la barre d’outils sont l’un des principaux composants UI disponibles aux WebExtensions. Les boutons de la barre d’outils sont présents dans la barre d’outils principale du navigateur et contiennent une icône. Lorsque l’utilisateur clique sur l’icône, une des deux choses peut arriver :

- Si vous avez spécifié une fenêtre contextuelle pour l’icône, la fenêtre contextuelle s’affiche. Les fenêtres contextuelles sont des boîtes de dialogue spécifiées à l’aide de HTML, CSS et JavaScript.
- Si vous n’avez pas spécifié une fenêtre contextuelle, un événement de clic est généré, que vous pouvez écouter dans votre code et effectuer un autre type d’action en réponse

Dans WebExtensions, ces types de boutons s’appellent « actions du navigateur » et sont configurés de la manière suivante :

- La clé de manifest.json [`browser_action`](/fr/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action) permet de définir le bouton.
- L’API JavaScript [`browserAction`](/fr/docs/Mozilla/Add-ons/WebExtensions/API/browserAction) est utilisé pour écouter les clics modifier le bouton ou effectuer des actions via votre code.

## Un bouton simple

Dans cette section, nous créerons une WebExtension qui ajoute un bouton à la barre d’outils. Lorsque l’utilisateur clique sur le bouton, nous ouvrirons [https ://developer.mozilla.org](https://developer.mozilla.org) dans un nouveau onglet.

Tout d’abord, créez un nouveau dossier, « bouton », et créez un fichier appelé « manifest.json » à l’intérieur avec le contenu suivant :

```json
{

  "description": "Demonstrating toolbar buttons",
  "manifest_version": 2,
  "name": "button-demo",
  "version": "1.0",

  "background": {
    "scripts": ["background.js"]
  },

  "browser_action": {
    "default_icon": {
      "16": "icons/page-16.png",
      "32": "icons/page-32.png"
    }
  }

}
```

Cela spécifie que nous aurons un script en [arrière‐plan](/fr/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts) nommé « background.js », et une action du navigateur (bouton) et une action du navigateur (bouton) dont les icônes vont vivre dans le répertoire « icônes ».

Ces icônes proviennent des [bits !](https://www.iconfinder.com/iconsets/bitsies) icônes créées parRecep Kütük.

Ensuite, créez un dossier « icons » dans le dossier « buttons » et enregistrez les deux icônes ci‐dessous :

- « page‐16.png » (![](page-16.png))
- « page‐32.png » (![](page-32.png)).

Nous avons deux icônes que nous pouvons utiliser, la plus grande dans les écrans haute densité. Le navigateur prend en charge la sélection de la meilleure icône pour l’affichage courrant.

Ensuite, créez « background.js » dans le répertoire racine de l’add‐on, et donnez‐lui le contenu suivant :

```js
function openPage() {
  browser.tabs.create({
    url: "https://developer.mozilla.org"
  });
}

browser.browserAction.onClicked.addListener(openPage);
```

Cela écoute l’événement de clic de l’action du navigateur ; Lorsque l’événement se déclenche, la fonction `openPage()` est exécuté, ce qui ouvre la page spécifiée à l’aide de l’API des [`onglets`](/fr/docs/Mozilla/Add-ons/WebExtensions/API/tabs).

A ce point, l’extension complète devrait ressembler à ceci :

```html
button/
    icons/
        page-16.png
        page-32.png
    background.js
    manifest.json
```

Maintenant [installer la WebExtension](/fr/Add-ons/WebExtensions/Temporary_Installation_in_Firefox) et cliquez sur le bouton :

{{EmbedYouTube("kwwTowgT‐Ys")}}

## Ajout d’une fenêtre contextuelle

Essayons d’ajouter une fenêtre contextuelle au bouton. Remplacez manifest.json par ceci :

```json
{

  "description": "Demonstrating toolbar buttons",
  "manifest_version": 2,
  "name": "button-demo",
  "version": "1.0",

  "browser_action": {
    "browser_style": true,
    "default_popup": "popup/choose_page.html",
    "default_icon": {
      "16": "icons/page-16.png",
      "32": "icons/page-32.png"
    }
  }

}
```

Nous avons fait trois changements par rapport à l’original :

- Nous ne parlons plus de « background.js », car maintenant nous allons gérer la logique de l’extension dans le script de la fenêtre contextuelle (vous êtes autorisé à utiliser background.js ainsi qu’un popup, c’est juste que nous n’en avons pas besoin dans ce cas).
- Nous avons ajouté `"browser_style":true`, ce qui aidera le style de notre popup à ressembler davantage à une partie du navigateur.
- Enfin, nous avons ajouté `"default_popup": "popup/choose_page.html"`, qui indique au navigateur que l’action du navigateur va maintenant afficher une fenêtre contextuelle lorsqu’elle est cliquée, dont le document se trouve dans  « popup / choose_page.html ».

Donc maintenant nous devons créer cette fenêtre contextuelle. Créez un répertoire appelé « popup » puis créez un fichier appelé « choose_page.html » à l’intérieur. Donnez‐lui les contenus suivants :

```html
<!DOCTYPE html>

<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="choose_page.css"/>
  </head>

<body>
  <div class="page-choice">developer.mozilla.org</div>
  <div class="page-choice">support.mozilla.org</div>
  <div class="page-choice">addons.mozilla.org</div>
  <script src="choose_page.js"></script>
</body>

</html>
```

Vous pouvez voir qu’il s’agit d’une page HTML normale contenant trois éléments {{htmlelement ("div")}}, chacun avec le nom d’un site Mozilla à l’intérieur. Il comprend également un fichier CSS et un fichier JavaScript, que nous ajouterons ensuite.

Créez un fichier appelé « choose_page.css » dans le répertoire « popup » et donnez‐lui ce contenu :

```css
html, body {
  width: 300px;
}

.page-choice {
  width: 100%;
  padding: 4px;
  font-size: 1.5em;
  text-align: center;
  cursor: pointer;
}

.page-choice:hover {
  background-color: #CFF2F2;
}
```

C'est juste un peu d’habillage pour notre popup.

Ensuite, créez un fichier « choose_page.js » dans le répertoire « popup » et donnez‐le à ces contenus :

```js
document.addEventListener("click", function(e) {
  if (!e.target.classList.contains("page-choice")) {
    return;
  }

  var chosenPage = "https://" + e.target.textContent;
  browser.tabs.create({
    url: chosenPage
  });

});
```

Dans notre JavaScript, nous écoutons les clics sur les choix contextuels. Nous vérifions d’abord si le clic a atterri sur l’un des choix de la page ; Sinon, nous ne faisons rien d’autre. Si le clic atterrit sur un choix de page, nous construisons une URL à partir de celui‐ci, et ouvrons un nouvel onglet contenant la page correspondante. Notez que nous pouvons utiliser les API WebExtension dans les scripts contextuels, tout comme nous le pouvons dans les scripts en arrière‐plan.

La structure finale de l’add‐on devrait ressembler à ceci :

    button/
        icons/
            page-16.png
            page-32.png
        popup/
            choose_page.css
            choose_page.html
            choose_page.js
        manifest.json

Maintenant, rechargez l’extension, cliquez de nouveau sur le bouton et essayez de cliquer sur les choix dans la fenêtre contextuelle :

{{EmbedYouTube("QPEh1L1xq0Y")}}

## Actions de page

Les [actions de page](/fr/docs/Mozilla/Add-ons/WebExtensions/Page_actions) sont comme les actions du navigateur, mais qui ne sont pertinentes que pour les pages particulières, plutôt que sur le navigateur dans son ensemble.

Alors que les actions du navigateur sont toujours affichées, les actions de la page ne sont affichées que dans les onglets où elles sont pertinentes. Les boutons d’action de la page sont affichés dans la barre d’URL, plutôt que dans la barre d’outils du navigateur.

## Pour en savoir plus

- `Clé de manifest browser_action`
- `API browserAction`
- Exemples d’actions du navigateur :

  - [beastify](https://github.com/mdn/webextensions-examples/tree/master/beastify)
  - [Bookmark it !](https://github.com/mdn/webextensions-examples/tree/master/bookmark-it)
  - [favourite‐colour](https://github.com/mdn/webextensions-examples/tree/master/favourite-colour)
  - [inpage‐toolbar‐ui](https://github.com/mdn/webextensions-examples/tree/master/inpage-toolbar-ui)
  - [open‐my‐page‐button](https://github.com/mdn/webextensions-examples/tree/master/open-my-page-button)

- `Clé de manifest page_action`
- `API pageAction`
- Exemple d’action de page

  - [chill‐out](https://github.com/mdn/webextensions-examples/tree/master/chill-out)
