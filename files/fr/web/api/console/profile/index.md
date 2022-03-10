---
title: Console.profile()
slug: Web/API/Console/profile
tags:
  - API
  - DOM
  - Méthodes
  - Profils
  - débogage
translation_of: Web/API/Console/profile
---
{{APIRef("Console API")}}{{Non-standard_header}}

Commence l'enregistrement d'un profil de performance (par exemple, l'outil [performance de Firefox](/fr/docs/Outils/Performance)).

Vous pouvez éventuellement fournir un argument pour nommer le profil, ce qui vous permet d'arrêter uniquement ce profil si plusieurs profils sont enregistrés. Voir {{domxref("Console.profileEnd()")}} pour voir comment cet argument est interprété.

Pour arrêter l'enregistrement, appeler {{domxref("Console.profileEnd()")}}.

{{AvailableInWorkers}}

## Syntaxe

    console.profile(profileName);

## Paramètres

- `profileName`
  - : Le nom à donner au profil. Facultatif.

## Compatibilité des navigateurs

{{Compat("api.Console.profile")}}

## Voir aussi

- {{domxref("Console.profileEnd()")}}
