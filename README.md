# JavaScript Cheat Sheet

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


### String [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)]
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
    
### Array [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)]
    var tab = ["abc", "def", "ghi"];
    tab.length;                     // nombre d'éléments du tableau
    
    tab.fill(value);                // remplit tous les éléments d'un tableau avec value
    tab.fill(value, début);         
    tab.fill(value, début, fin);
    
    tab.toString();                 // retourne une string : "abc,def,ghi,jkl"
    tab.join("-");                  // retourne une string avec séparateur personnalisé : "abc-def-ghi-jkl"
    tab.map(function);              // retourne un nouveau tableau en exécutant 'fonction(val, index, tab)' sur chaques éléments
    tab.forEach(function);          // exécute 'fonction(val, index, tab)' sur chaques éléments
    
    tab.pop();                      // retourne et supprime le dernier élément
    tab.push("jkl");                // ajoute un élément de contenu "jkl" à la fin, retourne la nouvelle taille du tableau
    tab.shift();                    // supprime et retourne le premier élément
    tab.unshift("aaa");             // ajoute un nouvel élément au début du tableau, retourne la nouvelle taille du tableau
    
    tab.slice(début, fin);          // retourne une portion de tableau entre les index début et fin 
    tab.splice(index, nb_sup, add1, ...);  // ajoute et supprime des éléments (index, supprimer nb_sup éléments, ajouter add1...) retourne un tableau des éléments supprimés ou un seul élément
    tab.concat(tab1, tab2, ...);    // fusionne des tableaux (retourne un tableau tab+tab1+tab2+...)
    
    tab.copyWithin(cible);          // copie une zone du tableau sur lui-même.
    tab.copyWithin(cible, début);
    tab.copyWithin(cible, début, fin);
    
    tab.find(callback);             // recherche dans le tableau la première occurence qui valide le callback(element, index, tab)
    tab.filter(callback);           // retourne un tableau avec les éléments validés par le callback(element, index, tab)
    tab.every(callback);            // retourne true si tous les éléments sonts validés par le callback(element, index, tab)
    tab.some(callback);             // retourne true si au moins un élément est validé par le callback(element, index, tab)
    
    tab.sort();                     // tri alphabétique d'un tableau. Tableau d'origine modifié
    tab.sort((a,b) => a - b);       // tri numérique d'un tableau. Tableau d'origine modifié
    tab.sort((a,b) => b - a);       // tri numérique inverse d'un tableau. Tableau d'origine modifié
    tab.reverse();                  // tri inverse alphabétique
    
    tab.reduce(function, val1);     // traite chaque valeur de la gauche vers la droite en applicant function(som, valeur) -> som
    tab.reduceRight(function, val1); // idem de la droite vers la gauche
    
    tab.concat(tab2);               // retourne un tableau concaténé tab + tab2
    
    (ES7) tab.includes("abc")       // recherche la présence d'un élément de contenu "abc". Retourne true    
    
### Map [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Map)]
    var map1 = new Map();
    var map1 = new Map( [['key1', 'value1'], ['key2', 'value']] );
    
    map1.size;                      // retourne le nombre d'éléments
    
    map1.set('key', 'value');       // ajoute un élément 'value' de clé 'key'
    map1.set(1, 'value');           // ajoute un élément 'value' de clé 1
    map1.get('key');                // retourne l'élément de clé 'key'
    map1.has('key');                // test la présence d'une élément de clé 'key'
    
    map1.clear();                   // efface tous les éléments
    map1.delete('key');             // supprime l'élément de clé 'key'
    
    map1.keys();                    // retourne un objet Iterator des clés
    map1.values();                  // retourne un objet Iterator des valeurs
    map1.entries();                 // retourne un objet Iterator contenant des paires [clé, valeur]
        
    map1.forEach(fonction);   // exécute une fonction(value, key, map) sur chaque élément
    map1.forEach(fonction, thisArg);  // ... avec thisArg
    
### Set [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Set)]
    let set1 = new Set();
    let set1 = new Set([1, 2, 3, 4, 5]);
    
    set1.size;                      // retourne le nombre d'éléments
    
    set1.add(value);                // ajoute un élément value
    set1.has(value);                // test la présence d'une élément value
    
    set1.clear();                   // efface tous les éléments
    set1.delete(value);             // supprime l'élément value
    
    set1.values();                  // retourne un objet Iterator des valeurs (alias set1.keys)
    set1.entries();                 // retourne un objet Iterator contenant des paires [valeur, valeur]
    
    set1.forEach(fonction);         // exécute une fonction(value1, value2, map) sur chaque élément value1=value2
    set1.forEach(fonction, thisArg);  // ... avec thisArg
    
### Canvas    
    HTML : <canvas width="150" height="150"></canvas>
    JS : let canvas = document.getElementsByTagName('canvas');
    let ctx = canvas.getContext('2d');  // ctx : objet accessible en JS
    
    ctx.strokeStyle = '#ff0000';    // couleur de ligne
    ctx.lineWidth = 1;              // epaisseur du trait
    ctx.lineCap = 'square';         // terminaison des lignes : 'butt', 'round', 'square'
    ctx.lineJoin = 'round'          // style des jointures dans un path : 'round', 'bever', 'miter'
    ctx.fillStyle = '#00ff00';      // couleur de remplissage    
    
    ctx.fillRect(x, y, w, h);       // dessine un rectangle plein
    ctx.strokeRect(x, y, w, h);     // dessine un rectangle fillaire
    ctx.clearRect(x, y, w, h);      // efface une zone rectangulaire
    
    ctx.beginPath();                // commence à dessiner une forme
    ctx.closePath();                // termine la forme
    ctx.stroke();                   // dessine la forme en traçant le contour
    ctx.fill();                     // dessine la forme en traçant la zone de contenu
    
    ctx.moveTo(x, y);                   // déplace le stylo
    ctx.lineTo(x, y);                   // trace une ligne
    ctx.quadraticCurveTo(cp1x, cp1y, x, y);
    ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y);
    

### Objets
    obj.hasOwnProperty              // teste l'existence d'une propriété
    
### Fonctions
    id = setTimeout( nom_fonction, 2000, arg1, arg2...);   // exécute la fonction dans 2000ms avec les arguments
    clearTimeout(id);                                      // annule l'exécution de la fonction
    id = setInterval(nom_fonction, 2000, arg1, arg2...);   // exécute la fonction à intervalle de 2000 ms
    clearInterval(id);                                     // annulation de la programmation de l'intervalle 

### Fonctions flêchées (ES6)
    param => { }                    // function(param) { ... }
    () => { }                       // function() { ... }
    
### Spread Operator (ES6)
    tab1 = ["a", "b", "c"]; tab2 = ["d", "e", "f"];
    var tab3 = [...tab1]                // copie de tableau
    var tab2 = [...tab1, ...tab2]       // concaténation de tableau
    console.log(...tab1);               // console : a, b, c

### Destructuring (ES6)
    const client = { nom: "Rog", prenom: "Fred", age: 30 }
    const {nom, prenom, age} = client;                  // const nom="Rog"; const prenom="Fred"; const age=30;
    const {nom, prenom, surnom="toto"} = client;        // const nom="Rog"; const prenom="Fred"; const surnom="toto";
    const {nom:n, prenom:p, age} = client;              // const n="Rog"; const p="Fred"; const age=30;
    
    const monTab = [20, 56, 89];
    const [var1, var2, var3] = monTab;                  // const var1=20; const var2=56; const var3=89;
 
## Snippets

### ES6
    [var1, var2] = [var2, var1];     // swap des variables var2->var1, var1->var2

### Balises html
    HTML5 : <script src="javascript.js"></script>

### Créer une balise p à la fin du body
    const elem = document.createElement("p");
    elem.innerHTML = "Mon texte !";
    document.body.appendChild(elem);
    // Résultat : <p>Mon Texte !</p>
    
