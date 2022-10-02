# listen-on
non-minified :
```js
;(function() {
  window.listenOn = function(selector, eventName, callbacks) {
    for (let element of document.querySelectorAll(selector)) {
      element.addEventListener(eventName, callbacks[element.dataset.callback]);
    }
  };
})();
```
minified :
```js
window.listenOn=function(e,t,l){for(let n of document.querySelectorAll(e))n.addEventListener(t,l[n.dataset.callback])};
```

## Usage Example
```html
<button class="clickable" data-callback='foot'> Click Me </button>


<script>
  window.listenOn=function(e,t,l){for(let n of document.querySelectorAll(e))n.addEventListener(t,l[n.dataset.callback])};
  
  let DOMEvents = {
  	clickable: {
  		'foo': () => bar(),
  	},
  };
  
  function bar() {
    alert('It works!');
  }
  
  window.listenOn('.clickable', 'click', DOMEvents.clickable);
  
</script>
```
