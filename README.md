CSSUnifier
==========

Un utilitaire javascript pour simplifier la manipulation du css depuis javascript.


Initialisation
==============

- **properties**: doit contenir l'ensemble des propriétés css dont vous voulez disposer.

exemple: `	var properties = ['transform', 'transformOrigin', 'transition', 'animation', 'perspective', 'background'];`

Utilisation
===========
**setProperties**: modifie plusieurs propripétés css.
```javascript
div.style.setProperties({
  top    : "10px",
  left   : "50px",
  height : "150px",
  width  : "350px"
});
```

**getProperties**: récupére un ensemble de propriétés css.
```javascript
var properties = div.style.getProperties( ["top", "left", "height", "width", "right"] );
//properties = {top: "10px", left: "50px", height: "150px", width: "350px", right: ""}
```

**convert**: convertit le style présent dans une balise `<style>`.
```javascript
var list = document.head.getElementByTagName('style');
for(var i=0; i<list.length; i++)
  list[i].convert();
```

**cssValue**: récupére la valeur appropriée au navigateur (dans le cas ou celle-ci est présente dans properties).
```javascript
//sur chrome / safari
var value = cssValue('background');
//value = 'background'
value = cssValue('transform');
//value = '-webkit-transform'
```

**unification**:
```javascript
div.style.animation = 'all 1s'
/* chrome = div.style.webkitAnimation
 * firefox = div.style.MozAnimation
 * ect...
 */ 
```
