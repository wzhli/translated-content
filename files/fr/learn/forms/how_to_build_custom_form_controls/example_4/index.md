---
title: Exemple 4
slug: Learn/Forms/How_to_build_custom_form_controls/Example_4
tags:
  - Avancé
  - Exemple
  - Formulaires
  - Guide
  - HTML
  - Web
translation_of: Learn/Forms/How_to_build_custom_form_controls/Example_4
original_slug: >-
  Web/Guide/HTML/Formulaires/Comment_construire_des_widgets_de_formulaires_personnalisés/Example_4
---
Ceci est le quatrième exemple expliquant [comment construire des widgets de formulaire personnalisés](/fr/docs/Learn/HTML/Forms/How_to_build_custom_form_widgets).

## Changement d'état

### Contenu HTML

```html
<form class="no-widget">
  <select name="myFruit">
    <option>Cerise</option>
    <option>Citron</option>
    <option>Banane</option>
    <option>Fraise</option>
    <option>Pomme</option>
  </select>

  <div class="select">
    <span class="value">Cerise</span>
    <ul class="optList hidden">
      <li class="option">Cerise</li>
      <li class="option">Citron</li>
      <li class="option">Banane</li>
      <li class="option">Fraise</li>
      <li class="option">Pomme</li>
    </ul>
  </div>
</form>
```

### Contenu CSS

```css
.widget select,
.no-widget .select {
  position : absolute;
  left     : -5000em;
  height   : 0;
  overflow : hidden;
}

/* --------------- */
/* Styles Requis   */
/* --------------- */

.select {
  position: relative;
  display : inline-block;
}

.select.active,
.select:focus {
  box-shadow: 0 0 3px 1px #227755;
  outline: none;
}

.select .optList {
  position: absolute;
  top     : 100%;
  left    : 0;
}

.select .optList.hidden {
  max-height: 0;
  visibility: hidden;
}

/* ------------ */
/* Styles chic  */
/* ------------ */

.select {
  font-size   : 0.625em; /* 10px */
  font-family : Verdana, Arial, sans-serif;

  -moz-box-sizing : border-box;
  box-sizing : border-box;

  padding : 0.1em 2.5em 0.2em 0.5em; /* 1px 25px 2px 5px */
  width   : 10em; /* 100px */

  border        : 0.2em solid #000; /* 2px */
  border-radius : 0.4em; /* 4px */

  box-shadow : 0 0.1em 0.2em rgba(0,0,0,.45); /* 0 1px 2px */

  background : #F0F0F0;
  background : -webkit-linear-gradient(90deg, #E3E3E3, #fcfcfc 50%, #f0f0f0);
  background : linear-gradient(0deg, #E3E3E3, #fcfcfc 50%, #f0f0f0);
}

.select .value {
  display  : inline-block;
  width    : 100%;
  overflow : hidden;

  white-space   : nowrap;
  text-overflow : ellipsis;
  vertical-align: top;
}

.select:after {
  content : "▼";
  position: absolute;
  z-index : 1;
  height  : 100%;
  width   : 2em; /* 20px */
  top     : 0;
  right   : 0;

  padding-top : .1em;

  -moz-box-sizing : border-box;
  box-sizing : border-box;

  text-align : center;

  border-left  : .2em solid #000;
  border-radius: 0 .1em .1em 0;

  background-color : #000;
  color : #FFF;
}

.select .optList {
  z-index : 2;

  list-style: none;
  margin : 0;
  padding: 0;

  background: #f0f0f0;
  border: .2em solid #000;
  border-top-width : .1em;
  border-radius: 0 0 .4em .4em;

  box-shadow: 0 .2em .4em rgba(0,0,0,.4);

  -moz-box-sizing : border-box;
  box-sizing : border-box;

  min-width : 100%;
  max-height: 10em; /* 100px */
  overflow-y: auto;
  overflow-x: hidden;
}

.select .option {
  padding: .2em .3em;
}

.select .highlight {
  background: #000;
  color: #FFFFFF;
}
```

### Contenu JavaScript

```js
// ----------- //
// UTILITAIRES //
// ----------- //

NodeList.prototype.forEach = function (callback) {
  Array.prototype.forEach.call(this, callback);
}

// ------------------------- //
// Définitions des fonctions //
// ------------------------- //

function deactivateSelect(select) {
  if (!select.classList.contains('active')) return;

  var optList = select.querySelector('.optList');

  optList.classList.add('hidden');
  select.classList.remove('active');
}

function activeSelect(select, selectList) {
  if (select.classList.contains('active')) return;

  selectList.forEach(deactivateSelect);
  select.classList.add('active');
};

function toggleOptList(select, show) {
  var optList = select.querySelector('.optList');

  optList.classList.toggle('hidden');
}

function highlightOption(select, option) {
  var optionList = select.querySelectorAll('.option');

  optionList.forEach(function (other) {
    other.classList.remove('highlight');
  });

  option.classList.add('highlight');
};

function updateValue(select, index) {
  var nativeWidget = select.previousElementSibling;
  var value = select.querySelector('.value');
  var optionList = select.querySelectorAll('.option');

  nativeWidget.selectedIndex = index;
  value.innerHTML = optionList[index].innerHTML;
  highlightOption(select, optionList[index]);
};

function getIndex(select) {
  var nativeWidget = select.previousElementSibling;

  return nativeWidget.selectedIndex;
};

// -------------------- //
// Liens aux événements //
// -------------------- //

window.addEventListener("load", function () {
  var form = document.querySelector('form');

  form.classList.remove("no-widget");
  form.classList.add("widget");
});

window.addEventListener('load', function () {
  var selectList = document.querySelectorAll('.select');

  selectList.forEach(function (select) {
    var optionList = select.querySelectorAll('.option');

    optionList.forEach(function (option) {
      option.addEventListener('mouseover', function () {
        highlightOption(select, option);
      });
    });

    select.addEventListener('click', function (event) {
      toggleOptList(select);
    });

    select.addEventListener('focus', function (event) {
      activeSelect(select, selectList);
    });

    select.addEventListener('blur', function (event) {
      deactivateSelect(select);
    });
  });
});

window.addEventListener('load', function () {
  var selectList = document.querySelectorAll('.select');

  selectList.forEach(function (select) {
    var optionList = select.querySelectorAll('.option'),
        selectedIndex = getIndex(select);

    select.tabIndex = 0;
    select.previousElementSibling.tabIndex = -1;

    updateValue(select, selectedIndex);

    optionList.forEach(function (option, index) {
      option.addEventListener('click', function (event) {
        updateValue(select, index);
      });
    });

    select.addEventListener('keyup', function (event) {
      var length = optionList.length,
          index  = getIndex(select);

      if (event.keyCode === 40 && index < length - 1) { index++; }
      if (event.keyCode === 38 && index > 0) { index--; }

      updateValue(select, index);
    });
  });
});
```

### Résultat

{{ EmbedLiveSample('Changement_détat') }}
