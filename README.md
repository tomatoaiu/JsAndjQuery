# JsAndjQuery
jquery v3.3.1
## get element
```html
<div id="me"></div>
```
```js
const js = document.getElementById("me");
console.log(js);
// <div id="me"></div>

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
const js = document.getElementsByClassName("me");
console.log(js);
// HTMLCollection(2) [div.me, div.me]

const js = document.querySelectorAll(".me");
console.log(js);
// NodeList(2) [div.me, div.me]

const jquery = $(".me");
console.log(jquery);
// jQuery.fn.init(2) [div.me, div.me, prevObject: jQuery.fn.init(1)]
```

## add class
### want to
```html
<div id="me"></div>
↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓
<div id="me" class="my mine"></div>
```
### test
```html
<div id="me"></div>
```
```js
const js = document.querySelectorAll("#me")[0];
js.className += "my mime";

const js = document.querySelectorAll("#me")[0];
js.classList.add("my");
js.classList.add("mine");

const js = document.querySelectorAll("#me")[0];
js.classList.add("my", "mine");

const jquery = $("#me");
jquery.addClass("my");
jquery.addClass("mine");

const jquery = $("#me");
jquery.addClass("my mine");
```

## append
### want to
```html
<div id="me"></div>
↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓
<div id="me">
    <b>Hello</b>
</div>
```
### test
```html
<div id="me"></div>
```
```js
const js = document.querySelectorAll("#me")[0];
const b = document.createElement("b");
var bContent = document.createTextNode("Hello");
b.appendChild(bContent);
js.appendChild(b);
/*
<div id="me">
    <b>Hello</b>
</div>
*/

const jquery = $("#me");
jquery.append("<b>Hello</b>");
/*
<div id="me">
    <b>Hello</b>
</div>
*/
```

## replace child html
### want to
```html
<div id="me">
    <b>Hello</b>
</div>
↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓
<div id="me">
    <p>replace</p>
</div>
```
### test
```html
<div id="me">
    <b>Hello</b>
</div>
```
```js
const js = document.querySelectorAll("#me")[0];
js.innerHTML = `<p>replace</p>`;
/*
<div id="me">
    <p>replace</p>
</div>
*/

const jquery = $("#me");
jquery.html(`<p>replace</p>`);
/*
<div id="me">
    <p>replace</p>
</div>
*/
```

## remove children
### want to
```html
<div id="me">
    <b>Hello</b>
    <b>Hello</b>
</div>
↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓
<div id="me"></div>
```
### test
```html
<div id="me">
    <b>Hello</b>
    <b>Hello</b>
</div>
```
```js
const js = document.querySelectorAll("#me")[0];
while(js.firstChild){
    js.removeChild(js.firstChild);
}

const jquery = $("#me");
jquery.empty();
```

## remove self
### want to
```html
<div id="me">
    <b>Hello</b>
</div>
↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓

```
### test
```html
<div id="me">
    <b>Hello</b>
</div>
```
```js
const js = document.querySelectorAll("#me")[0];
js.remove();

const jquery = $("#me");
jquery.remove();
```

## click
```html
<div id="me"></div>
```
```js
const js = document.querySelectorAll("#me")[0];
js.addEventListener('click', (() => {
    console.log("click");
}), false);
// click

const jquery = $("#me");
jquery.on('click', (() => {
    console.log("click");
}));
// click
```
