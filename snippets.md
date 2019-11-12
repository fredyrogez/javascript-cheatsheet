### Fonction wait()
```js
function wait (ms)
{
  const t1 = performance.now()
  let t2 = null
  do {
    t2 = performance.now()
  }
  while(t2-t1 < ms)
}
```

### Game Loop
```js
let limitFps = 1000/60 // 60 fps
function gameLoop() {
  let timestamp = performance.now()

  // updates, draw..

  wait(limitFps - (performance.now() - timestamp) )
  requestAnimationFrame(gameLoop)
}
gameLoop()
```
    
### Tracer une forme sur un canvas avec rotation centrée sur l'élément
```js
const ctx = canvas.getContext("2d")    
ctx.translate(x + w / 2, y + h / 2)         // translation au centre de l'objet
ctx.rotate(a * Math.PI / 180)           // rotation : 'a' en degrés -> radians
ctx.translate(0 - (x + w / 2), 0 - (y + h / 2))  // translation retour à l'origine
ctx.strokeRect(x, y, w, h)
```
    
### Charger une image
```js
let img = new Image()
img.src = 'fichier_image.png'
img.onload = function () { } // image chargée, on peut l'utiliser
```
        
    
