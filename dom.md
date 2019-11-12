### DOM [[MDN](https://developer.mozilla.org/fr/docs/Web/API/Document_Object_Model)]
```js
getElementById('id')                  // sélection par id, retourne un unique élément    
getElementsByTagName('tagName')       // sélection par nom de balise html, retourne un HTMLCollection
getElementsByClassName('className')   // sélecteur par class, retourne une NodeList
querySelector('div')                  // sélecteur CSS unique, retourne le premier élément (plus lent que getElement...)
querySelectorAll('div')               // sélecteurs CSS multiple, retourne une NodeList statique (plus lent que getElement...)

elem.getAttribute("href")             // contenu de l'attribut href de l'élément elem
elem.setAttribute("title", "coucou")  // ajoute l'attribut title avec le contenu "coucou"

elem.offsetHeight                     // hauteur totale de l'élément (+bord...)
elem.clientHeight                     // surface interne de l'élément (-bord...)
elem.offsetTop                        // distance en pixel de l'élément par rapport au début de page
elem.syle.color = "#ff0000"           // modification du paramètre color du style de l'élément.
elem.style.fontFamily = "Arial"       // attention : - remplacé par camelCase (font-family -> fontFamily)

elem.classList.add("maClasse")        // ajoute la classe maClasse à l'élément
elem.classList.remove("maClasse")     // supprime la classe maClasse à l'élément
elem.classList.toggle("maClasse")     // "on/off" la classe maClasse à l'élément
```
