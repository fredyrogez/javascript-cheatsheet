# JavaScript

### DOM [[MDN](https://developer.mozilla.org/fr/docs/Web/API/Document_Object_Model)]
    getElementById(id);                   // sélection par id, retourne un unique élément    
    getElementsByTagName(tagname);        // sélection par nom de balise html, retourne un HTMLCollection
    getElementsByClassName(class);        // sélecteur par class, retourne une NodeListu
    querySelector();                      // sélecteur CSS unique, retourne le premier élément (plus lent que getElement...)
    querySelectorAll();                   // sélecteurs CSS multiple, retourne une NodeList statique (plus lent que getElement...)
    
    elem.getAttribute("href");            // contenu de l'attribut href de l'élément elem
    elem.setAttribute("title", "coucou"); // ajoute l'attribut title avec le contenu "coucou"
    
    elem.offsetHeight;                    // hauteur totale de l'élément (+bord...)
    elem.clientHeight;                    // surface interne de l'élément (-bord...)
    elem.offsetTop;                       // distance en pixel de l'élément par rapport au début de page
    elem.syle.color = "#ff0000";          // modification du paramètre color du style de l'élément.
    elem.style.fontFamily = "Arial"       // attention : - remplacé par camelCase (font-family -> fontFamily)
    
    elem.classList.add("maClasse");       // ajoute la classe maClasse à l'élément
    elem.classList.remove("maClasse");    // supprime la classe maClasse à l'élément
    elem.classList.toggle("maClasse");    // "on/off" la classe maClasse à l'élément


### Strings [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)]
    var str = "abcdefghijk";
    str.length;                     // longueur d'une string
    
    str.concat(str1, str2, ...);    // concaténation de strings : str + str1 + str1 + ...
    
    str.indexOf(str1);              // recherche l'index de la première occurrence de str1 dans str, -1 si non trouvé
    str.lastIndexOf(str1);          // recherche l'index de la dernière occurrence de str1 dans str, -1 si non trouvé
    str.search(regex);              // recherche l'expression régulière regex dans str, si trouvé retourne l'index, sinon -1
    
    str.charAt(index);              // retourne le caractère à l'index
    str[index];                     // retourne le caractère à l'index
    str.charCodeAt(index);          // retourne le code du caractère à l'index
    str.slice(début, fin)           // retourne une sous-string de début à fin (index négatif possible, de la fin)
    str.slice(index)                // retourne une sous-string de index à la fin
    
    str.replace(str1, str2);        // retourne une string ou la première occurrence de str1 dans str et la remplace par str2
    str.replace(regex, str2);       // retourne une string ou toutes les occurrences de l'expression régulière regex et les remplaces par str2
     
    str.toUpperCase();              // retourne un string avec conversion en majuscules, "abc" -> "ABC"
    str.toLowerCase();              // retourne un string avec conversion en minuscules, "ABC -> "abc"
    123.toString(base);             // retourne une string en base hex=16, oct=8, bin=2
    
    str.split(",");                 // divise une string, retourne un tableau, caractère de séparation : ","
    str.split("");                  // divise une string, retourne un tableau, chaque caractère isolé       
    
### Arrays [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)]
    var tab = ["abc", "def", "ghi"];
    
    tab.toString();                 // retourne une string : "abc,def,ghi,jkl"
    tab.join("-");                  // retourne une string avec séparateur personnalisé : "abc-def-ghi-jkl"
    
    tab.pop();                      // retourne et supprime le dernier élément
    tab.push("jkl");                // ajoute un élément de contenu "jkl" à la fin, retourne la nouvelle taille du tableau
    tab.shift();                    // supprime et retourne le premier élément
    tab.unshift("aaa");             // ajoute un nouvel élément au début du tableau, retourne la nouvelle taille du tableau
    
    tab.slice(début, fin);          // retourne une portion de tableau entres les index debut et fin 
    tab.splice(index, nb_sup, add1, ...);  // ajoute et supprime des éléments (index, supprimer nb_sup éléments, ajouter add1...) retourne un tableau des éléments supprimés ou un seul élément
    tab.concat(tab1, tab2, ...);    // fusionne des tableaux (retourne un tableau tab+tab1+tab2+...)
    
    tab.sort();                     // tri alphabétique d'un tableau. Tableau d'origine modifié
    tab.sort((a,b) => a - b)        // tri numérique d'un tableau. Tableau d'origine modifié
    tab.reverse();                  // tri inverse alphabétique
    
    (ES7) tab.includes("abc")       // recherche la présence d'un élément de contenu "abc". Retourne true    
