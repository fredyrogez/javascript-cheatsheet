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