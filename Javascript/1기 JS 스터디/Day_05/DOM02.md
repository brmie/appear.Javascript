# DOM 탐색
전 시간에 DOM에 대한 기본적인 이론은 정리했으니 진도 쭉쭉 나가볼게요
DOM은 트리 구조이기 때문에 부모 자식 형제등 탐색할 수 있습니다.

## parentNode
선택된 요소의 부모 노드를 탐색합니다.
```html
<ul class="list_item">
    <li id="item">1</li>
    <li>2</li>
    <li>3</li>
</ul>

var li = document.getElementById('item'); // id 속성을 이용해서 선택
console.log(li.parentNode) // <ul class="list_item"></ul>
```

## Children
자식들을 반환해줍니다.
```html
<ul class="list_item">
    <li id="item_1">1</li>
    <li>2</li>
    <li>3</li>
</ul>

var ul = document.querySelector('ul'); // ul을 찾아서 캐싱
console.log(ul.children); // (3)[li#item_1, li, li, item_1: li#item_1]
```

## Child
firstChild : 첫번째 자식노드를 탐색 Text Node반환
lastChild : 마지막 자식노드를 탐색 Text Node반환
firstElementChild : 첫번째 자식노드를 탐색 Element Node반환
lastElementChild : 마지막 자식노드를 탐색 Element Node반환

```html
<ul class="list_item">
    <li id="item">1</li>
    <li>2</li>
    <li>3</li>
</ul>

var ul = document.querySelector('ul'); // ul을 찾아서 캐싱
var first = ul.firstChild;
var last = ul.lastChild;

var firstEl = ul.firstElementChild;
var lastEl = ul.lastElementChild;


console.log(ul);
console.log(first); // 첫번째 요소 #text
console.log(last); // 마지막 요소 #text
console.log(firstEl); // <li id="item">1</li>
console.log(lastEl); // <li>3</li>
```

## hasChildNodes
자식 노드를 가지고 있는지 알 수 있습니다.
```html
<ul class="list_item">
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>

var ul = document.querySelector('ul'); // ul을 찾아서 캐싱
console.log(ul.hasChildNodes()); // true
```

## childNodes
자식 노드들을 반환해준다. Text Node, Element Node 구분없다.
```html
<ul class="list_item">
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>

var ul = document.querySelector('ul'); // ul을 찾아서 캐싱
console.log(ul.childNodes()); // [text, li, text, li, text, li, text]
```

## Sibling
형제 노드를 탐색합니다. IE9 이상의 브라우저에서 동작합니다. Text Node로 반환됩니다.
```html
<ul class="list_item">
    <li id="item_1">1</li>
    <li>2</li>
    <li>3</li>
</ul>

var ul = document.querySelector('ul'); // ul을 찾아서 캐싱
var li = document.getElementById('item_1');

console.log(li.nextSibling);
console.log(li.previousSibling);
```