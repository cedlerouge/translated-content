---
title: DOMTokenList.forEach()
slug: Web/API/DOMTokenList/forEach
translation_of: Web/API/DOMTokenList/forEach
---
{{APIRef("DOM")}}

La méthode **`forEach()`** de l'interface {{domxref("DOMTokenList")}} appelle le retour donné en paramètre, un pour chaque paire de valeurs dans la liste, dans l'ordre d'insertion.

## Syntaxe

    tokenList.forEach(callback);
    tokenList.forEach(callback, argument);

### Paramètres

- `callback`

  - : Fonction à exécuter pour chaque élément, prenant éventuellement 3 arguments :

    - _`currentValue`_
      - : L'élément en cours de traitement dans le tableau.
    - `currentIndex`
      - : L'index de l'élément en cours de traitement dans le tableau.
    - _`listObj`_
      - : Le tableau que `forEach()` est en train d'appliquer.

- _`argument`_` {{Optional_inline}}`
  - : Valeur à utiliser comme {{jsxref("this")}} lors de l'exécution du `callback` (_rappel_).

### Valeur renvoyée

{{jsxref('undefined')}} (_indéfinie_).

## Exemple

Dans l'exemple suivant, nous récupérons la liste des classes définies dans un élément {{htmlelement("span")}} en tant que `DOMTokenList` en utilisant {{domxref("Element.classList")}}. Nous récupérons un itérateur contenant les valeurs avec `forEach()` et écrivons chacune d'elles dans le  {{domxref("Node.textContent")}} du `<span>` pendant l'exécution de la fonction interne `forEach()`.

### HTML

```html
<span class="a b c"></span>
```

### JavaScript

```js
var span = document.querySelector("span");
var classes = span.classList;
var iterator = classes.values();

classes.forEach(
  function(value, key, listObj) {
    span.textContent += value + ' ' + key + "/" + this + '  ++  ';
  },
  "arg"
);
```

### Résultat

{{ EmbedLiveSample('Exemple', '100%', 60) }}

## Spécifications

| Spécification                                                                                                            | Statut                           | Commentaire          |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------- | -------------------- |
| {{SpecName('DOM WHATWG','#interface-domtokenlist','forEach() (as iterable&lt;Node&gt;)')}} | {{Spec2('DOM WHATWG')}} | Définition initiale. |

## Compatibilité des navigateurs

{{Compat("api.DOMTokenList.forEach")}}

## Voir aussi

- {{domxref("DOMSettableTokenList")}} (objet qui étend DOMTokenList avec la propriété définissable _.value_)
