# JavaScript Cheat Sheet

* [String](https://github.com/rogez/JavaScript#string) [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)]
* [Array](https://github.com/rogez/JavaScript#array) [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)]
* [Map](https://github.com/rogez/JavaScript#map) [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Map)]
* [Set](https://github.com/rogez/JavaScript#set) [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Set)]
* [DOM](https://github.com/rogez/JavaScript#dom) [[MDN](https://developer.mozilla.org/fr/docs/Web/API/Document_Object_Model)]
* [Canvas](https://github.com/rogez/JavaScript#canvas) [[MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Canvas)]
* [Snippets](https://github.com/rogez/JavaScript#snippets)

### String
```js
let str = "abcdefghijk"
str.length                      // longueur d'une string

str.concat(str1, str2, ...)     // concaténation de strings : str + str1 + str1 + ...

str.indexOf(str1)               // recherche l'index de la première occurrence de str1 dans str, -1 si non trouvé
str.lastIndexOf(str1)           // recherche l'index de la dernière occurrence de str1 dans str, -1 si non trouvé
str.search(regex)               // recherche l'expression régulière regex dans str, si trouvé retourne l'index, sinon -1

str.charAt(index)               // retourne le caractère à index
str[index]                      // retourne le caractère à index
str.charCodeAt(index)           // retourne le code du caractère à l'index
str.slice(début, fin)           // retourne une sous-string de début à fin (index négatif possible, de la fin)
str.slice(index)                // retourne une sous-string de index à la fin

str.replace(str1, str2)         // retourne une string ou la première occurrence de str1 dans str et la remplace par str2
str.replace(regex, str2)        // retourne une string ou toutes les occurrences de l'expression régulière regex et les remplaces par str2
  
str.toUpperCase()               // retourne un string avec conversion en majuscules, "abc" -> "ABC"
str.toLowerCase()               // retourne un string avec conversion en minuscules, "ABC -> "abc"
123.toString(base)              // retourne une string en base hex=16, oct=8, bin=2

str.split(",")                  // divise une string, retourne un tableau, caractère de séparation : ","
str.split("")                   // divise une string, retourne un tableau, chaque caractère isolé       

let pommes = 10;
const message = `J'ai ${pommes} pommes`;    // J'ai 10 pommes

```

### Array
```js
let tab = ["abc", "def", "ghi"] 
tab.length                      // nombre d'éléments du tableau

tab.fill(value)                 // rempli tous les éléments d'un tableau avec value
tab.fill(value, début)          
tab.fill(value, début, fin) 

tab.toString()                  // retourne une string : "abc,def,ghi,jkl"
tab.join("-")                   // retourne une string avec séparateur personnalisé : "abc-def-ghi-jkl"
tab.map(fonction)               // retourne un nouveau tableau en exécutant 'fonction(val, index, tab)' sur chaques éléments
tab.forEach(fonction)           // exécute 'fonction(val, index, tab)' sur chaques éléments

tab.pop()                       // retourne et supprime le dernier élément
tab.push("jkl")                 // ajoute un élément de contenu "jkl" à la fin, retourne la nouvelle taille du tableau
tab.shift()                     // supprime et retourne le premier élément
tab.unshift("aaa")              // ajoute un nouvel élément au début du tableau, retourne la nouvelle taille du tableau
tab.slice(début, fin)           // retourne une portion de tableau entre les index début et fin 
tab.splice(index, nb_sup, add1, ...)   // ajoute et supprime des éléments (index, supprimer nb_sup éléments, ajouter add1...) retourne un tableau des éléments supprimés ou un seul élément
tab.concat(tab1, tab2, ...)     // fusionne des tableaux (retourne un tableau tab+tab1+tab2+...)

tab.copyWithin(cible)           // copie une zone du tableau sur lui-même.
tab.copyWithin(cible, début) 
tab.copyWithin(cible, début, fin) 

tab.find(callback)              // recherche dans le tableau la première occurence qui valide le callback(element, index, tab)
tab.filter(callback)            // retourne un tableau avec les éléments validés par le callback(element, index, tab)
tab.every(callback)             // retourne true si tous les éléments sonts validés par le callback(element, index, tab)
tab.some(callback)              // retourne true si au moins un élément est validé par le callback(element, index, tab)

tab.sort()                      // tri alphabétique d'un tableau. Tableau d'origine modifié
tab.sort((a,b) => a - b)        // tri numérique d'un tableau. Tableau d'origine modifié
tab.sort((a,b) => b - a)        // tri numérique inverse d'un tableau. Tableau d'origine modifié
tab.reverse()                   // inverse les éléments d'un tableau

tab.reduce(fonction, val1)      // traite chaque valeur de la gauche vers la droite en applicant fonction(som, valeur) -> som
tab.reduceRight(fonction, val1) // idem de la droite vers la gauche

tab.concat(tab2)                // retourne un tableau concaténé tab + tab2

tab.includes("abc")             // ES7 : recherche la présence d'un élément de contenu "abc". Retourne true si trouvé

let newTab = Array.from(objectIterable, functionMap)
let newTab = Array.from('ABC')  // eq : let newTab = ['A', 'B', 'C']
let newTab = Array.from([1, 2, 3], x => x * 10))  // eq : let newTab = [10, 20, 30]
let list = Array.from(querySelectorAll('div'))    // nodeList -> array

```
    
### Map
```js
let map1 = new Map() 
let map1 = new Map( [['key1', 'value1'], ['key2', 'value']] ) 

map1.size                       // nombre d'éléments

map1.set('key', 'value')        // ajoute un élément 'value' de clé 'key'
map1.set(1, 'value')            // ajoute un élément 'value' de clé 1
map1.get('key')                 // retourne l'élément de clé 'key'
map1.has('key')                 // test la présence d'une élément de clé 'key'

map1.clear()                    // efface tous les éléments
map1.delete('key')              // supprime l'élément de clé 'key'

map1.keys()                     // retourne un objet Iterator des clés
map1.values()                   // retourne un objet Iterator des valeurs
map1.entries()                  // retourne un objet Iterator contenant des paires [clé, valeur]
    
map1.forEach(fonction)            // exécute une fonction(value, key, map) sur chaque élément
map1.forEach(fonction, thisArg)   // ... avec thisArg
```
    
### Set
```js
let set1 = new Set() 
let set1 = new Set([1, 2, 3, 4, 5]) 

set1.size                       // retourne le nombre d'éléments

set1.add(value)                 // ajoute un élément value
set1.has(value)                 // test la présence d'une élément value

set1.clear()                    // efface tous les éléments
set1.delete(value)              // supprime l'élément value

set1.values()                   // retourne un objet Iterator des valeurs (alias set1.keys)
set1.entries()                  // retourne un objet Iterator contenant des paires [valeur, valeur]

set1.forEach(fonction)          // exécute une fonction(value1, value2, map) sur chaque élément value1=value2
set1.forEach(fonction, thisArg) // ... avec thisArg
```

### DOM
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

### JSON
```js
const str = '{"val1" : 42, "val2" : "ABC"}'
const obj = JSON.parse(str)  // obj.val1 === 42 ... 
const str2 = JSON.stringify({ x: 5, y: 6 })
```

### Canvas
```html
<!-- HTML -->
<canvas width="150" height="150"></canvas>
```

```js
let canvas = document.getElementsByTagName('canvas') 
let ctx = canvas.getContext('2d')   // ctx : objet accessible en JS

ctx.strokeStyle = '#ff0000'     // couleur de ligne
ctx.lineWidth = 1               // epaisseur du trait
ctx.lineCap = 'square'          // terminaison des lignes : 'butt', 'round', 'square'
ctx.lineJoin = 'round'          // style des jointures dans un path : 'round', 'bever', 'miter'
ctx.fillStyle = '#00ff00'       // couleur de remplissage    

ctx.fillRect(x, y, w, h)        // dessine un rectangle plein
ctx.strokeRect(x, y, w, h)      // dessine un rectangle fillaire
ctx.clearRect(x, y, w, h)       // efface une zone rectangulaire

ctx.beginPath()                 // commence à dessiner une forme
ctx.closePath()                 // termine la forme
ctx.stroke()                    // dessine la forme en traçant le contour
ctx.fill()                      // dessine la forme en traçant la zone de contenu

ctx.moveTo(x, y)                    // déplace le stylo
ctx.lineTo(x, y)                    // trace une ligne
ctx.quadraticCurveTo(cp1x, cp1y, x, y) 
ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y) 

let pix = new Image()            // création d'un élément image
pix.src = 'image.png'            // fichier source de l'image
pix.onload = function () {...}
ctx.drawImage(pix, x, y)         // après 'onload'        
ctx.drawImage(pix, sx, sy, sw, sh, dx, dy, dw, dh)  // découpe du sprite : source -> destination
```    

### Objets
```js
obj.hasOwnProperty              // teste l'existence d'une propriété
```
    
### Fonctions
```js
id = setTimeout( nom_fonction, 2000, arg1, arg2...)    // exécute la fonction dans 2000ms avec les arguments
clearTimeout(id)                                       // annule l'exécution de la fonction
id = setInterval(nom_fonction, 2000, arg1, arg2...)    // exécute la fonction à intervalle de 2000 ms
clearInterval(id)                                      // annulation de la programmation de l'intervalle 
```

### Fonctions flêchées (ES6)
```js
param => { }                 // function avec un seul paramètre
(param1, param2) => { }      // function avec plusieurs paramètres
() => { }                    // function sans paramètre

```
    
### Spread Operator (ES6)
```js
tab1 = ["a", "b", "c"]
tab2 = ["d", "e", "f"] 
var tab3 = [...tab1]                // copie de tableau
var tab2 = [...tab1, ...tab2]       // concaténation de tableau
console.log(...tab1)                // console : a, b, c
fonction(...tab1)                   // fonction("a", "b", "c")
```

### Destructuring (ES6)
```js
const client = { nom: "Rog", prenom: "Fred", age: 30 }
const {nom, prenom, age} = client                   // const nom="Rog"  const prenom="Fred"  const age=30 
const {nom, prenom, surnom="toto"} = client         // const nom="Rog"  const prenom="Fred"  const surnom="toto" 
const {nom:n, prenom:p, age} = client               // const n="Rog"  const p="Fred"  const age=30 

const monTab = [20, 56, 89] 
const [var1, var2, var3] = monTab                   // const var1=20  const var2=56  const var3=89 
```

## Snippets

### Fonction wait()
```js
function wait (ms)
{
  const t1 = performance.now();
  let t2 = null;
  do {
    t2 = performance.now();
  }
  while(t2-t1 < ms);
}
```

### Game Loop
```js
let limitFps = 1000/60; // 60 fps
function gameLoop() {
  let timestamp = performance.now();

  // updates, draw..

  wait(limitFps - (performance.now() - timestamp) );
  requestAnimationFrame(gameLoop);
}
gameLoop();
```
    
### Tracer une forme sur un canvas avec rotation centrée sur l'élément
```js
const ctx = canvas.getContext('2d');
ctx.translate(x + w / 2, y + h / 2);    // translation au centre de l'objet
ctx.rotate(a * Math.PI / 180);          // rotation : 'a' en degrés -> radians
ctx.translate(0 - (x + w / 2), 0 - (y + h / 2));  // translation retour à l'origine
ctx.strokeRect(x, y, w, h);
```

### Distance entre deux points
```js
function distance (x0, y0, x1, y1) {
  return Math.hypot(x1 - x0, y1 - y0);
}
```
    
### Charger une image
```js
let img = new Image();
img.src = 'fichier_image.png';
img.onload = function () { } // image chargée, on peut l'utiliser
```

### Swap de variables (ES6)
```js
[var1, var2] = [var2, var1];   // var2->var1, var1->var2
```

### Créer une balise p à la fin du body
```js
const elem = document.createElement('p');
const text = document.createTextNode('Mon texte !');
elem.appendChild(text);
document.body.appendChild(elem);  // Création du code à la fin du body  : <p>Mon Texte !</p>
```
    
