# JsAndjQuery
jquery v3.3.1
## get element
```html
<div id="me"></div>
```
```js
const js = document.querySelectorAll("#me");
console.log(js);
// NodeList [div#me]

const jquery = $("#me");
console.log(jquery);
// jQuery.fn.init [div#me]
```
```html
<div class="me"></div>
<div class="me"></div>
```
```js
const js = document.querySelectorAll(".me");
console.log(js);
// NodeList(2) [div.me, div.me]

const jquery = $(".me");
console.log(jquery);
// jQuery.fn.init(2) [div.me, div.me, prevObject: jQuery.fn.init(1)]
```