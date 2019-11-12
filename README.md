# JavaScript Cheat Sheet

* [DOM](https://github.com/rogez/JavaScript/blob/master/dom.md)
* [Canvas](https://github.com/rogez/JavaScript/blob/master/canvas.md)
* [Snippets](https://github.com/rogez/JavaScript/blob/master/snippets.md)

### String [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)]
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
```

### Array [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array)]
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
tab.reverse()                   // tri inverse alphabétique

tab.reduce(fonction, val1)      // traite chaque valeur de la gauche vers la droite en applicant fonction(som, valeur) -> som
tab.reduceRight(fonction, val1) // idem de la droite vers la gauche

tab.concat(tab2)                // retourne un tableau concaténé tab + tab2

tab.includes("abc")             // ES7 : recherche la présence d'un élément de contenu "abc". Retourne true si trouvé

let newTab = Array.from(objectIterable, functionMap)
let newTab = Array.from('ABC')  // eq : let newTab = ['A', 'B', 'C']
let newTab = Array.from([1, 2, 3], x => x * 10))  // eq : let newTab = [10, 20, 30]
let list = Array.from(querySelectorAll('div'))    // nodeList -> array

```
    
### Map [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Map)]
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
    
### Set [[MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Set)]
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
