# Front-end Study day03๐คนโโ๏ธ

# `JavaScript`

## ์ด๋ฒคํธ

### DOM, ๋ฌธ์ ๊ฐ์ฒด ๋ชจ๋ธ(Document Object Model)

- DOM์ XML์ด๋ HTML๋ฌธ์์ ์ ๊ทผํ๊ธฐ ์ํ ์ผ์ข์ ์ธํฐํ์ด์ค์ด๋ค.
- ์ด ๊ฐ์ฒด ๋ชจ๋ธ์ ๋ฌธ์ ๋ด์ ๋ชจ๋  ์์๋ฅผ ์ ์ํ๊ณ  ๊ฐ๊ฐ์ ์์์ ์ ๊ทผํ๋ ๋ฐฉ๋ฒ์ ์ ๊ณตํ๋ค
- ๋์ ์๋ฏธ๋ก ์น ๋ธ๋ผ์ฐ์ ๊ฐ HTML ํ์ด์ง๋ฅผ ์ธ์ํ๋ ๋ฐฉ์์ ์๋ฏธ, ์ข์ ์๋ฏธ๋ก ๋ณธ๋ค๋ฉด document ๊ฐ์ฒด์ ๊ด๋ จ๋ ๊ฐ์ฒด์ ์งํฉ์ ์๋ฏธ

![Untitled](./day03_data/Untitled.png)

<br>

<br>

### DOM์ ์ข๋ฅ

- Core DOM : ๋ชจ๋  ๋ฌธ์ ํ์์ ์ํ DOM ๋ชจ๋ธ
- HTML DOM : HTML ๋ฌธ์๋ฅผ ์ํ DOM ๋ชจ๋ธ
    - HTML๋ฌธ์๋ฅผ ์กฐ์ํ๊ณ  ์ ๊ทผํ๋ ํ์คํ๋ ๋ฐฉ๋ฒ์ ์ ์ํ๋ค
- XML DOM : XML ๋ฌธ์๋ฅผ ์ํ DOM ๋ชจ๋ธ
    - XML ๋ฌธ์์ ์ ๊ทผํ์ฌ ๊ทธ ๋ฌธ์๋ฅผ ๋ค๋ฃจ๋ ํ์คํ๋ ๋ฐฉ๋ฒ์ ์ ์ํ๋ค

<br>

<br>

<br>

## HTML element

### ์ ํ

### `getElementById()`

- ํ๋ผ๋ฏธํฐ๋ก ์ฐพ์ผ๋ ค๋ id๋ฅผ ์ ๋ฌํ์ฌ, ํด๋น element๋ฅผ ์ฐพ์ ์ ์๋ค
- id๋ ์ ์ผํ ๊ฐ์ด๋ฏ๋ก, ํ๋์ element๋ง ๋ฆฌํดํ๋ค

```jsx
// HTML
<div id='div_1'>
  Div1์๋๋ค.
</div>
<div id='div_2'>
  Div2์๋๋ค.
</div>
<input type='button'
       value='getElementById() - id๋ก ์ฐพ๊ธฐ'
       onclick='getDiv1()'/>

// JS
function getDiv1() {
  const div1 = document.getElementById('div_1');
  alert(div1.innerText);
}
```

<br>

<br>

### `getElementsByClassName()`

- ํด๋์ค ์ด๋ฆ์ผ๋ก element๋ฅผ ์ฐพ์์, ์ด ํด๋์ค ์ด๋ฆ์ ๊ฐ์ง๋ ๋ชจ๋  element ๋ชฉ๋ก์ ๋ฆฌํด
- ํจ์์ ์ด๋ฆ์ ์์ธํ ๋ณด๋ฉด getElementsByClassName์ผ๋ก Elements๊ฐ ๋ณต์์ ํํ์ธ ๊ฒ์ ์ด ํจ์๊ฐ ๋ชฉ๋ก์ ๋ฆฌํดํ๊ธฐ ๋๋ฌธ์ด๋ค

```jsx
// HTML
<div id='div_1' class='my_class'>
  Div1์๋๋ค.
</div>
<div id='div_2' class='my_class'>
  Div2์๋๋ค.
</div>
<div id='div_3' class='your_class'>
  Div3์๋๋ค.
</div>
<input type='button'
       value='getElementsByClassName() - class์ด๋ฆ์ผ๋ก ์ฐพ๊ธฐ'
       onclick='getMyClass()'/>

// JS
function getMyClass() {
  const div_list 
    = document.getElementsByClassName('my_class');
  
  // class๊ฐ 'my_class'์ธ element ๊ฐ์ ์ถ๋ ฅ
  const div_list_length = div_list.length;
  alert(div_list_length);
  
  // class๊ฐ 'my_class'์ธ element ๋ชฉ๋ก ์ถ๋ ฅ
  for(let i = 0; i < div_list_length; i++)  {
    alert(div_list[i].innerText);
  }
}
```

- ๋ค์์ ํด๋์ค ์ด๋ฆ์ ๋ชจ๋ ํฌํจํ๊ณ  ์๋ element๋ฅผ ์ฐพ์ ๋๋ ํ๋ผ๋ฏธํฐ๋ก ํด๋์ค ์ด๋ฆ์ ์คํ์ด์ค๋ก ๊ตฌ๋ถํ์ฌ ๋๊ฒจ์ค๋ค.
- ์๋ ์ฝ๋๋ ํด๋์ค ์ด๋ฆ์ โredโ ์ โblueโ ๋ชจ๋๋ฅผ ํฌํจํ๋ element๋ฅผ ์ฐพ์์ค๋ค

```jsx
// document.getElementsByClassName('red blue');

// HTML
<div id='div_1' class='red blue yellow'>
  red blue yellow
</div>
<div id='div_2' class='green blue red'>
  green blue red
</div>
<div id='div_3' class='yellow green red'>
  yellow green red
</div>
<input type='button'
       value='getElementsByClassName() - class์ด๋ฆ์ผ๋ก ์ฐพ๊ธฐ'
       onclick='getMyClass()'/>

// JS
function getMyClass() {
  const div_list 
    = document.getElementsByClassName('red blue');
  
  // class๊ฐ 'my_class'์ธ element ๊ฐ์ ์ถ๋ ฅ
  const div_list_length = div_list.length;
  alert(div_list_length);
  
  // class๊ฐ 'my_class'์ธ element ๋ชฉ๋ก ์ถ๋ ฅ
  for(let i = 0; i < div_list_length; i++)  {
    alert(div_list[i].innerText);
  }
}
```

<br>

<br>

### `getElementsByTagName()`

- โ โ ํ๊ทธ๋ฅผ ๊ฐ์ง ๋ชจ๋  element ๋ชฉ๋ก์ ์ฐพ์์ค๋ค

```jsx
// HTML
<div id='div_1' class='my_class'>
  Div1์๋๋ค.
</div>
<div id='div_2' class='my_class'>
  Div2์๋๋ค.
</div>
<div id='div_3' class='your_class'>
  Div3์๋๋ค.
</div>
<input type='button'
       value='getElementsByTagName() - Tag Name์ผ๋ก ์ฐพ๊ธฐ'
       onclick='getElementsByTagNameDiv()'/>

// JS
function getElementsByTagNameDiv() {
  const div_list 
    = document.getElementsByTagName('div');
  
  // tag name์ด 'div'์ธ element ๊ฐ์ ์ถ๋ ฅ
  const div_list_length = div_list.length;
  alert(div_list_length);
  
  // tag name์ด 'div'์ธ element ๋ชฉ๋ก ์ถ๋ ฅ
  for(let i = 0; i < div_list_length; i++)  {
    alert(div_list[i].innerText);
  }
}
```

<br>

<br>

### `querySelector()`

- ์ด ํจ์๋ ํ๋ผ๋ฏธํฐ๋ก ์๋ ฅ๋ฐ์ CSS ์ ํ์๋ฅผ ์ฌ์ฉํด์, element๋ฅผ ์ฐพ์์ค๋ค
- ํ๋ผ๋ฏธํฐ๋ก ์๋ ฅ๋ฐ์ CSS ์ ํ์๋ก ์ฐพ์ ์ฌ๋ฌ๊ฐ์ element ์ค ์ฒซ๋ฒ์งธ element๋ฅผ ๋ฆฌํด

```jsx
// HTML
<div id='div_1' class='my_class'>
  Div1์๋๋ค.
</div>
<div id='div_2' class='my_class'>
  Div2์๋๋ค.
</div>
<div id='div_3' class='your_class'>
  Div3์๋๋ค.
</div>
<input type='button'
       value='querySelector() - Class๋ก ์ฐพ๊ธฐ'
       onclick='querySelectorByClassName()'/>

// JS
function querySelectorByClassName() {
  const div
    = document.querySelector('.my_class');
  
  alert(div.innerText);
}
```

<br>

<br>

### `querySelectorAll()`

- ์ฌ์ฉ๋ฒ์ `querySelector()`๊ณผ ๊ฐ๋ค
- ๋ค๋ง, ์ด๋ฆ์์ ์ ์ ์๋ฏ CSS์ ํ์(ํ๋ผ๋ฏธํฐ๋ก ๋๊ฒจ์ค)๋ก ์ฐพ์ ๋ชจ๋  element ๋ชฉ๋ก์ ๋ฆฌํดํ๋ค

```jsx
// HTML
<div id='div_1' class='my_class'>
  Div1์๋๋ค.
</div>
<div id='div_2' class='my_class'>
  Div2์๋๋ค.
</div>
<div id='div_3' class='your_class'>
  Div3์๋๋ค.
</div>
<input type='button'
       value='querySelectorAll() - Id ์ ์ฒด ์ฐพ๊ธฐ'
       onclick='querySelectorAllById()'/>

// JS
function querySelectorAllById() {
  const div_list 
    = document.querySelectorAll('#div_1');
  
  // id๊ฐ 'div_1'์ธ element ๊ฐ์ ์ถ๋ ฅ
  const div_list_length = div_list.length;
  alert(div_list_length);
  
  // id๊ฐ 'div_1'์ธ element ๋ชฉ๋ก ์ถ๋ ฅ
  for(let i = 0; i < div_list_length; i++)  {
    alert(div_list[i].innerText);
  }
}
```

<br>

<br>

### ์์ฑ

### `createElement()`

- ํ๋ผ๋ฏธํฐ๋ก ์๋ ฅ๋ฐ์ tagName์ element๋ฅผ ์์ฑํ์ฌ ๋ฆฌํด

```jsx
let element = document.createElement(tagName);
```

<br>

<br>

### `createTextNode()`

- text node๋ฅผ ์์ฑํ๋ ํจ์์ด๋ค
- ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌ๋ฐ์ ํ์คํธ ๋ฐ์ดํฐ๋ฅผ ํ์คํธ ๋ธ๋๋ก ๋ณํํ์ฌ Text๋ธ๋๋ฅผ ๋ฆฌํด

```jsx
let textNode = document.createTextNode(data);
```

<br>

<br>

### ์ถ๊ฐ

```jsx
<!-- before() -->
<div>
    <!-- prepend() -->
    ์๋?
    <!-- append() -->
</div>
<!-- after() -->

// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' onclick=' before()' value='before()' />
<input type='button' onclick=' after()' value='after()' />
<input type='button' onclick=' prepend()' value='prepend()' />
<input type='button' onclick=' append()' value='append()' />

// JS
const list = document.getElementById('list');
  
  // list(<ul>) ์์ 'before' ํ์คํธ ์ถ๊ฐ
  list.before('before');
}

function after() {
  const list = document.getElementById('list');
  
  // list(<ul>) ๋ค์ 'after' ํ์คํธ ์ถ๊ฐ
  list.after('after');
}

function prepend() {
  const list = document.getElementById('list');
  
  // list(<ul>)์ ์ฒซ๋ฒ์งธ ์์ ๋ธ๋ ๋ค์ <li> ๋ธ๋ ์ถ๊ฐ
  const prepend = document.createElement('li');
  prepend.innerHTML = 'prepend';
  list.prepend(prepend);
}

function append() {
  const list = document.getElementById('list');
  
  // list(<ul>)์ ๋ง์ง๋ง ์์ ๋ธ๋ ๋ค์ <li> ๋ธ๋ ์ถ๊ฐ
  const append = document.createElement('li');
  append.innerHTML = 'append';
  list.append(append);
}
```

### `before()`

- ๋ธ๋ ๋๋ ๋ฌธ์์ด์ ์ ํ๋ ๋ธ๋์ ์์ ์ถ๊ฐ

<br>

<br>

### `after()`

- ๋ธ๋ ๋๋ ๋ฌธ์์ด์ ์ ํ๋ ๋ธ๋์ ๋ค์ ์ถ๊ฐ

<br>

<br>

### `prepend()`

- ๋ธ๋ ๋๋ ๋ฌธ์์ด์ ์ ํ๋ ๋ธ๋์ ์ฒซ ๋ฒ์งธ ์์ element ์์ ์ถ๊ฐ

<br>

<br>

### `append()`

- ๋ธ๋ ๋๋ ๋ฌธ์์ด์ ์ ํ๋ ๋ธ๋์ ๋ง์ง๋ง ์์ element ๋ค์ ์ถ๊ฐ

<br>

<br>

### `insertAdjacentHTML()`

- ํ๋ผ๋ฏธํฐ๋ก ์๋ ฅ๋ฐ์ htmlText(HTML ๋๋ XML)์ ํ์ฑํ์ฌ ๋ธ๋๋ก ๋ณํํ๊ณ  ์ด ๋ธ๋๋ฅผ position์ผ๋ก ์๋ ฅ๋ฐ์ ์์น์ ์ฝ์

```jsx
insertAdjacentHTML(position, htmlText);
```

<br>

<br>

### `insertAdjacentElement()`

- ํ๋ผ๋ฏธํฐ๋ก ์๋ ฅ๋ฐ์ ์์๋ฅผ position์ผ๋ก ์๋ ฅ๋ฐ์ ์์น์ ์ฝ์

```jsx
insertAdjacentElement(position, element);
```

<br>

<br>

### `insertAdjacentText()`

- ํ๋ผ๋ฏธํฐ๋ก ์๋ ฅ๋ฐ์ text๋ฅผ position์ผ๋ก ์๋ ฅ๋ฐ์ ์์น์ ์ฝ์

```jsx
insertAdjacentText(position, text);
```

<br>

<br>

๐ ์ ์ธ๊ฐ์ง ๊ฒฝ์ฐ์ position ๊ฐ์๋ ์ด๋ค ๊ฐ์ ๋ฃ์ด์ฃผ์ด์ผ ํ ๊น?

- beforebegin - ์ ํ๋ ๋ธ๋์ ์
- afterend - ์ ํ๋ ๋ธ๋์ ๋ค
- afterbegin - ์ ํ๋ ๋ธ๋์ ์ฒซ ๋ฒ์งธ ์์ ๋ธ๋ ์
- beforeend - ์ ํ๋ ๋ธ๋์ ๋ง์ง๋ง ์์ ๋ธ๋

```jsx
<!-- beforebegin -->
<div>
   <!-- afterbegin -->
   ์๋?
   <!-- beforeend -->
</div>
<!-- afterend -->

// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' 
       onclick=' beforebegin()' 
       value='beforebegin()' />
<input type='button' 
       onclick='afterend()' 
       value='afterend()' />
<input type='button'
       onclick='afterbegin()' 
       value='afterbegin()' />
<input type='button'
       onclick=' beforeend()' 
       value='beforeend()' />

// JS
// list(<ul>) ์์ '<div>beforebegin</div>' HTML ์ถ๊ฐ
function beforebegin() {
  const list = document.getElementById('list');
  
  const htmlText = '<div>beforebegin</div>';
  list.insertAdjacentHTML('beforebegin', htmlText);
}

// list(<ul>) ๋ค์ '<div>afterend</div>' HTML ์ถ๊ฐ
function afterend() {
  const list = document.getElementById('list');
  
  const htmlText = '<div>afterend</div>';
  list.insertAdjacentHTML('afterend', htmlText);
}

// list(<ul>)์ ์ฒซ๋ฒ์งธ ์์ ๋ธ๋ ๋ค์ <li> ๋ธ๋ ์ถ๊ฐ
function afterbegin() {
  const list = document.getElementById('list');
  
  const htmlText = '<li>afterbegin</li>';
  list.insertAdjacentHTML('afterbegin', htmlText);
}

// list(<ul>)์ ๋ง์ง๋ง ์์ ๋ธ๋ ๋ค์ <li> ๋ธ๋ ์ถ๊ฐ
function beforeend() {
  const list = document.getElementById('list');
  
  const htmlText = '<li>beforeend</li>';
  list.insertAdjacentHTML('beforeend', htmlText);
}
```

<br>

<br>

### `appendChild()`

- ์ ํํ ๋ธ๋์ ๋ง์ง๋ง ์์ ๋ธ๋ ๋ค์ ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌ๋ฐ์ ๋ธ๋๋ฅผ ๋ถ์ธ๋ค.
- `append()` ํจ์์ ๋น์ทํ๊ฒ ๋์ํ๋ค

```jsx
let child = element.appendChild(child);
```

๐ `appendChild()` vs `append()` ๋น๊ต

|  | appendChild() | append() |
| --- | --- | --- |
| ํ๋ผ๋ฏธํฐ | node ๊ฐ์ฒด๋ง | node ๊ฐ์ฒด, text |
| ๋ฆฌํด ๊ฐ | ์ถ๊ฐํ ์์ ๋ธ๋ ๋ฆฌํด | X |
| ๋ธ๋ ์ถ๊ฐ | ํ๋์ ๋ธ๋๋ง ์ถ๊ฐ | ์ฌ๋ฌ ๋ธ๋ ์ถ๊ฐ |

<br>

<br>

### `insertBefore()`

- newNode๋ฅผ parentNode์ ์์ ๋ธ๋ ์ค ํ๋์ธ referenceNode ์์ ์ถ๊ฐํ๋ค

```jsx
let insertedNode = parentNode.insertBefore(newNode, referenceNode);
```

- ํ๋ผ๋ฏธํฐ
    - newNode : ์ถ๊ฐํ  ๋ธ๋
    - referenceNode
        - parentNode์ ์์๋ธ๋์ด๋ฉฐ newNode๋ referenceNode์ ์์ ์ถ๊ฐ๋๋ค
        - referenceNode๊ฐ null์ด๋ฉด, newNode๋ ์์ ๋ธ๋์ ๋์ ์ถ๊ฐ๋๋ค

```jsx
// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' onclick='insertBefore2()' value='insertBefore(node, refNode)' />
<input type='button' onclick='insertEnd()' value='insertBefore(node, null)' />

// JS
// <li>2</li> ์์ ๋ธ๋ ์ถ๊ฐ
function insertBefore2() {
  const list = document.getElementById('list');
  
  // newNode
  const newNode = document.createElement('li');
  newNode.innerHTML = '1.5';
  
  // referenceNode
  const referenceNode = document.getElementById('second');
  
  // insertBefore
  list.insertBefore(newNode, referenceNode);
}

// <ul>์ ์์ ๋ธ๋ ๋งจ ๋ค์ ์ถ๊ฐ
function insertEnd() {
  const list = document.getElementById('list');
  
  // newNode
  const newNode = document.createElement('li');
  newNode.innerHTML = '4';
  
  // insertBefore
  list.insertBefore(newNode, null);
}
```

<br>

<br>

### ๋ณ๊ฒฝ

### `replaceWith()`

- node๋ฅผ ์๋ก์ด ๋ธ๋๋ ๋ฌธ์์ด(param1, โฆ , paramN) ๋ก ๋์ฒดํ๋ค

```jsx
node.replaceWith(param1);
node.replaceWith(param1,....,paramN);

// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' onclick='replaceWithEx()' value='replaceWith()' />

// JS
// <li>2</li> ๋ธ๋ ๊ต์ฒด
function replaceWithEx() {
  // ๊ต์ฒดํ  ๊ธฐ์กด ๋ธ๋, <li>2</li>
  const oldNode = document.getElementById('second');
  
  // ๊ต์ฒดํ  ์ ๋ธ๋, <li>2(new)</li>
  const newNode = document.createElement('li');
  newNode.id='second';
  newNode.innerHTML = '2(new)';
  
  // replaceWith()
  oldNode.replaceWith(newNode);

}
```

<br>

<br>

### `replaceChild()`

- parentNode์ ์์ ๋ธ๋ ์ค oldChild๋ฅผ newChild๋ก ๊ต์ฒด
- ์ด ํจ์๋ ๊ต์ฒด๋ ๋ธ๋, ์ฆ oldChild ๋ธ๋์ ๋์ผํ ๋ธ๋๋ฅผ ๋ฆฌํดํ๋ค
- parentNode๊ฐ oldChild์ ๋ถ๋ชจ ๋ธ๋๊ฐ ์๋ ๊ฒฝ์ฐ exception(NotFoundError)์ด ๋ฐ์

```jsx
let replaceNode = parentNode.replaceChild(newChild, oldChild);

// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' onclick='replaceChildEx()' value='replaceChild()' />

// JS
// <li>2</li> ๋ธ๋ ๊ต์ฒด
function replaceChildEx() {
  // ๊ต์ฒดํ  ๊ธฐ์กด ๋ธ๋, <li>2</li>
  const oldNode = document.getElementById('second');
  
  // ๊ต์ฒดํ  ๊ธฐ์กด ๋ธ๋์ parent ๋ธ๋
  const parent = oldNode.parentNode;
  
  // ๊ต์ฒดํ  ์ ๋ธ๋, <li>2(new)</li>
  const newNode = document.createElement('li');
  newNode.id='second';
  newNode.innerHTML = '2(new)';
  
  // replaceChild()
  parent.replaceChild(newNode, oldNode);

}
```

<br>

<br>

### ์ญ์ 

### `remove()`

- ์ ํ๋ ๋ธ๋ ์ญ์ 

```jsx
node.remove()

// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' onclick='removeEx()' value='remove()' />

// JS
// <li>2</li> ๋ธ๋ ์ญ์ 
function removeEx() {
  
  // ์ญ์ ํ  ๊ธฐ์กด ๋ธ๋, <li>2</li>
  const child = document.getElementById('second');
  
  // ์ญ์  : remove()
  child.remove();

}
```

<br>

<br>

### `removeChild()`

- ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌ๋ฐ์ child ๋ธ๋ ์ญ์ 
- ์ด๋, ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌํ child ๋ธ๋๋ parentNode์ ์์ ๋ธ๋์ฌ์ผํ๋ค.

```jsx
parentNode.removeChild(child);

// HTML
<div>๋ชฉ๋ก</div>
<ul id='list'>
  <li id='first'>1</li>
  <li id='second'>2</li>
  <li id='third'>3</li>
</ul>
<div>๋ชฉ๋ก ๋</div>

<input type='button' onclick='removeChildEx()' value='removeChild()' />

// JS
// <li>2</li> ๋ธ๋ ์ญ์ 
function removeChildEx() {
  // ์ญ์ ํ  ๊ธฐ์กด ๋ธ๋, <li>2</li>
  const child = document.getElementById('second');
  
  // ์ญ์ ํ  ๊ธฐ์กด ๋ธ๋์ parent ๋ธ๋
  const parent = child.parentNode;
  
  // ์ญ์  : removeChild()
  parent.removeChild(child);

}
```

<br>

<br>

### ๋ณต์ฌ

### `clondNode()`

- ํธ์ถํ node์ ๋ณต์ฌ๋ณธ์ ๋ฆฌํด

```jsx
let dupNode = node.cloneNode(deep);
```

- ํ๋ผ๋ฏธํฐ deep
    - true : node์ children๊น์ง ๋ณต์ฌ
    - false : ํด๋น ๋ธ๋๋ง ๋ณต์ฌ
    - default ๊ฐ์ ๋ธ๋ผ์ฐ์ ์ ๋ฒ์ ์ ๋ฐ๋ผ ๋ค๋ฅด๋ฏ๋ก ,deep ๊ฐ์ ๋ฐ๋์ ์จ ์ฃผ๋ ๊ฒ์ด ์ข๋ค

```jsx
// HTML
<div id='hello'>
  <p style='color: red'>์๋ํ์ธ์</p>
</div>

<input type='button' value='๋ณต์ฌ/๋ถ์ฌ๋ฃ๊ธฐ' onclick='cloneNodeEx()' />

// JS
// 'hello' ๋ธ๋ ๋ณต์ฌํ์ฌ ๋ถ์ฌ๋ฃ๊ธฐ
function cloneNodeEx() {
  
  // ๋ณต์ฌํ  ๋ธ๋ ์ ํ
  const hello = document.getElementById('hello');
  
  // ๋ณต์ฌ
  const helloCopy = hello.cloneNode(true);
  
  // id ๋ณ๊ฒฝ
  helloCopy.id = 'hello2';
  
  // ๋ถ์ฌ๋ฃ๊ธฐ
  document.body.append(helloCopy);
}
```

<br>

<br>

## `attribute`

- ์์์ ์์ฑ์ ์ ๊ทผํ์ฌ ๊ฐ์ ๋ณ๊ฒฝ, ์ถ๊ฐํ  ์ ์๋ค
- element.attribute = โ๊ฐโ ์ ํํ๋ก ์ฌ์ฉ๋๋ค

```jsx
const img = document.getElementById("img");
img.src = "./์๋ฌด์ฌ์ง1.png";

var el = document.getElementById('menu');
// - ์์ฑ์ ์ถ๊ฐ : ์๋ฆฌ๋จผํธ์ ์๋ก์ด ์์ฑ๊ณผ ์์ฑ๊ฐ์ ์ถ๊ฐํ๋ค.
el.setAttribute(์์ฑ๋ช, ์์ฑ๊ฐ);
// - ์์ฑ์ ๋ณ๊ฒฝ : ์๋ฆฌ๋จผํธ์ ์ง์ ๋ ์์ฑ๋ช์ ์๋ก์ด ์์ฑ๊ฐ์ผ๋ก ๋ฐ๊พผ๋ค.
el.setAttribute(์์ฑ๋ช, ์์ฑ๊ฐ);
// - ์์ฑ์ ์ญ์  : ์๋ฆฌ๋จผํธ์์ ์ง์ ๋ ์์ฑ๋ช๊ณผ ์ผ์นํ๋ ์์ฑ์ ์ญ์ ํ๋ค.
el.removeAttribute(์์ฑ๋ช);
// - ์์ฑ๊ฐ ์กฐํ : ์๋ฆฌ๋จผํธ์์ ์ง์ ๋ ์์ฑ๋ช์ ์์ฑ๊ฐ์ ๊ฐ์ ธ๊ฐ๋ค.
el.getAttribute(์์ฑ๋ช);
```

- ์์ ์ฝ๋๋ฅผ ์ฌ์ฉํ๋ฉด `<img src="" id="img">` ์ธ ํ๊ทธ๋ฅผ `<img src="./์๋ฌด์ฌ์ง1.png" id="img">`๋ก ๋ณ๊ฒฝ ํ๋ค.

<br>

<br>

### `setAttribute()`

- ์์์ ์์ฑ์ ์ ๊ทผํ์ฌ ๊ฐ์ ๋ณ๊ฒฝ, ์ถ๊ฐํ  ์ ์๋ค
- `element.setAttribute('์์ฑ', '๊ฐ')` ์ ํํ๋ก ์ฌ์ฉํ๋ค

```jsx
const img = document.getElementById("img");
 img.setAttribute('src', '์๋ฌด์ฌ์ง1.png');
```

<br>

<br>

<br>

## DOM์ CSS Style ๋ณ๊ฒฝ

### Style ์์ฑ๊ฐ ๋ณ๊ฒฝ

1. `style` ์์ฑ ์ฌ์ฉํ๊ธฐ - CSS ์์ฑ ํ๋์ฉ ์ถ๊ฐํ๊ธฐ

```jsx
// HTML
<div id='greeting'> ์๋ํ์ธ์ </div>
<input type='button' 
       value='ํ์คํธ ์์ ๋ณ๊ฒฝ(Blue)' 
       onclick='changeTextColor()'
/>
<input type='button' 
       value='๋ฐฐ๊ฒฝ ์์ ๋ณ๊ฒฝ(Yellow)' 
       onclick='changeBgColor()'
/>

// JS
function changeTextColor() {
  
  // 1. ๋์ element ์ ํ
  const element = document.getElementById('greeting');
  
  // 2. style ๋ณ๊ฒฝ
  element.style.color = 'blue';
}

function changeBgColor() {
  
  // 1. ๋์ element ์ ํ
  const element = document.getElementById('greeting');
  
  // 2. style ๋ณ๊ฒฝ
  element.style.backgroundColor = 'yellow';
}
```

- ์ ์์ ๋ style ์์ฑ์ ์ด์ฉํ์ฌ ๊ธ์ ์์๊ณผ ๋ฐฐ๊ฒฝ ์์ ๋ณ๊ฒฝํ๋ ์์ 

โ๏ธ ์ฃผ์ํ  ์ ์ style ์์ฑ์ ์ง์ ํ๋ css ์์ฑ ์ด๋ฆ์ carmel case, โbackground-colorโ ๋ โbackgroundcolorโ ๋ก ์์ฑํ๋ค. โ-โ๊ฐ ๋ค์ด๊ฐ์๋ ์๋จ 

1. `style.cssText` ์ฌ์ฉํ๊ธฐ - css ์์ฑ ํ๋ฒ์ ์ฌ๋ฌ๊ฐ ์ถ๊ฐํ๊ธฐ

```jsx
// HTML
<div id='greeting'> ์๋ํ์ธ์ </div>
<input type='button' 
       value='ํ์คํธ/๋ฐฐ๊ฒฝ ์์ ๋ณ๊ฒฝ(Blue/Yellow)' 
       onclick='changeColor()'
/>

// JS
function changeColor() {
  
  // 1. ๋์ element ์ ํ
  const element = document.getElementById('greeting');
  
  // 2. style ๋ณ๊ฒฝ
  element.style.cssText  = 'color: blue; background-color: yellow';
}
```

- ์ ์์ ๋ ํ๊บผ๋ฒ์ ๊ธ์์ ์์๊ณผ ๋ฐฐ๊ฒฝ์์ ์ง์ ํด์ฃผ๊ธฐ ์ํด์ style์ cssText ์์ฑ์ ์ฌ์ฉ

โ๏ธ cssText ์์ฑ์ ์ง์ ํ  ๋๋, โ-โ๋ฅผ ์ฌ์ฉํ css ์์ฑ๋ช์ ์ฌ์ฉํ๋ค

<br>

<br>

๐ `style`, `style.cssText` ์ฌ์ฉ ์ ์ฃผ์ํ  ์ 

- `style.css ์์ฑ๋ช` - ๊ธฐ์กด์ ์ ์๋ style์ ์๋ก์ด ์์ฑ์ ์ถ๊ฐ
- `style.cssText` - ๊ธฐ์กด์ ์ ์๋ style์ ์ง์ฐ๊ณ , cssText๋ก ๋ฎ์ด ์ด๋ค

```jsx
// HTML
<div id='greeting'> ์๋ํ์ธ์ </div>
<input type='button' 
       value='ํ์คํธ/๋ฐฐ๊ฒฝ ์์ ๋ณ๊ฒฝ(Blue/Yellow)' 
       onclick='change()'
/>

// JS
function change() {
  
  // 1. ๋์ element ์ ํ
  const element = document.getElementById('greeting');
  
  // 2. Style ์์ฑ ์ง์  
  element.style.fontWeight='bold';
  
  // 3. cssText ์ง์ (๋ฎ์ด์ด๋ค)
  element.style.cssText  = 'color: blue; background-color: yellow';
}
```

โ๏ธ ์ ์์ ์์๋ `style.fontWeight='bold'` ๋ฅผ ์ง์ ํ์์ง๋ง `element.style.cssText` ๊ตฌ๋ฌธ์ด ์์์ ์ง์ ํ โfontWeightโ ์์ฑ์ ๋ชจ๋ ๋ฎ์ด์ด ๊ฒ์ ํ์ธํ  ์ ์๋ค.

```jsx
// HTML
<div id='greeting'> ์๋ํ์ธ์ </div>
<input type='button' 
       value='ํ์คํธ/๋ฐฐ๊ฒฝ ์์ ๋ณ๊ฒฝ(Blue/Yellow)' 
       onclick='change()'
/>

// JS
function change() {
  
  // 1. ๋์ element ์ ํ
  const element = document.getElementById('greeting');

  // 2. cssText ์ง์ (๋ฎ์ด์ด๋ค)
  element.style.cssText  = 'color: blue; background-color: yellow';
  
  // 3. Style ์์ฑ ์ง์ (์ถ๊ฐ๋๋ค)
  element.style.fontWeight='bold';
}
```

โ๏ธ ์ด๋ฒ ์์ ์์๋ cssText ์์ฑ์ ๋จผ์  ์ง์ ํ๊ณ  element.style.fontWeight ์์ฑ์ ๋์ค์ ์ ์, cssText ์์ฑ์ ์ ์๋ style์ fontWeight๊ฐ ์ถ๊ฐ๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค. 

<br>

<br>

<br>

## throttling๊ณผ debouncing

> ๋ ๊ฐ์ง ๋ฐฉ๋ฒ ๋ชจ๋ DOM ์ด๋ฒคํธ๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ์คํํ๋ ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ์ฑ๋ฅ์์ ์ด์ ๋ก JS์ ์์ ์ธ ์ธก๋ฉด, ์ฆ ์ด๋ฒคํธ(event)๋ฅผ ์ ์ด(์ ํ)ํ๋ ํ๋ก๊ทธ๋๋ฐ ๊ธฐ๋ฒ์ด๋ค.
> 

```
โพย setTimeout() - ํจ์์ ์คํ์ ์์ฝํ๋ ํ์ด๋จธ ๊ธฐ๋ฅ
โพย clearTimeout() - ํ์ด๋จธ์ ์คํ์ ์ทจ์ํ๋ ๊ธฐ๋ฅ
โพย ๋๋ฐ์ด์ฑ - ๋น๋ฒํ๊ฒ ๋ฐ์ํ๋ ์ด๋ฒคํธ๋ฅผ 'ํน์  ์๊ฐ ์ดํ์ ํ๋ฒ๋ง' ์คํ ์ํค๋ ์ต์ ํ ๊ธฐ๋ฒ
โพย ์ฐ๋กํ๋ง - ๋น๋ฒํ๊ฒ ๋ฐ์ํ๋ ์ด๋ฒคํธ๋ฅผ '์ผ์ ํ ๊ฐ๊ฒฉ์ผ๋ก ํ๋ฒ๋ง' ์คํ ์ํค๋ ์ต์ ํ ๊ธฐ๋ฒ
```

์๋ฅผ ๋ค์ด, ์น/์ฑ ์ฌ์ฉ์๊ฐ ์คํฌ๋กค(scroll wheel), ํธ๋ํจ๋, ์คํฌ๋กค ๋ง๋๋ฅผ ๋๋๊น ํ๋ค๊ณ  ๊ฐ์ ํด๋ณด์.

์ฌ์ฉ์๋ ํฌ๊ฒ ๋๋ผ์ง ๋ชปํ  ์ ์์ผ๋ ์ด ํ์๋ก ์ธํด ์๋ง์ ์คํฌ๋กค ์ด๋ฒคํธ๊ฐ ๋ฐ์ํ๊ฒ ๋๋ค.

์ด ๋ ๋งค๋ฒ ์คํฌ๋กค ์ด๋ฒคํธ์ ๋ํ ์ฝ๋ฐฑ(callback)์ด ๋ฐ์ํ๊ณ  ๊ทธ ์ฝ๋ฐฑ์ด ์ํํ๋ ์ผ์ ๋งค์ฐ ํฐ ๋ฆฌ์์ค๋ฅผ ์ก์๋จน๊ฒ ๋  ๊ฒ์ด๋ค.

โ๏ธ Throttle ๊ณผ Debounce ๋ ์ด๋ฒคํธ๊ฐ ๊ณผ๋ํ ํ์๋ก ๋ฐ์ํ์ฌ ์ด๋ฒคํธ ํธ๋ค๋ฌ๊ฐ ๋ฌด๊ฑฐ์ด ์ฐ์ฐ์ ์ ์์ด ๋ง์ด ์ํํ๋ ๊ฒฝ์ฐ์ ์ ์ฝ์ ๊ฑธ์ด ์ ์ดํ  ์ ์๋ ์์ค์ผ๋ก ์ด๋ฒคํธ๋ฅผ ๋ฐ์์ํค๋ ๊ฒ์ ๋ชฉํ๋กํ๋ ๊ธฐ์ 

โ๏ธ `underscore` ๋ `lodash` ์ ๋ฉ์๋๋ฅผ ์ฌ์ฉํ๋ฉด ํธ๋ฆฌ

<br>

<br>

### ๋๋ฐ์ด์ฑ(debouncing)

- ์ฐ์ด์ด ํธ์ถ๋๋ ํจ์๋ค ์ค ๋ง์ง๋ง ํจ์(๋๋ ์ ์ผ ์ฒ์)๋ง ํธ์ถํ๋๋ก ํ๋ ๊ฒ

```jsx
<input id="input" />
document.querySelector('#input').addEventListener('input', function(e) {
  console.log(`api ์์ฒญ : ${e.target.value}`);
});
```

- ๋ง์ฝ โ์๊ทธ๋โ ์ ์ํฐ ์์ด๋ ๊ฒ์ ๊ฒฐ๊ณผ๊ฐ ๋ฐ๋ก ๋์ค๋ ๊ฒ์์ฐฝ์ ์น๋ค๊ณ  ํด๋ณด์. ์ํฐ ์์ด๋ ๊ฒฐ๊ณผ๋ฅผ ์ฆ์ ๋ณด์ฌ์ฃผ๋ ค๋ฉด ํญ์ input ์ด๋ฒคํธ์ ๋๊ธฐํ๊ณ  ์์ด์ผ ํ๋ค.
    - ๋ฌธ์ ๋ ํ ๊ธ์ ์น  ๋๋ง๋ค api ์์ฒญ์ด ์คํ๋จ
    - ์์ ๋ก ๋ณธ๋ค๋ฉด 7๋ฒ์ด๋ ์์ฒญ ํจ.
    - ํ๊ธ๊ฐ์ ์กฐํฉํ ์ธ์ด๋ ์ฌ์ง์ฒ๋ผ 7๋ฒ๋ณด๋ค ๋ ๋ง์ด ์ด๋ฒคํธ๊ฐ ๋ฐ์ํ  ์๋ ์์

![Untitled](./day03_data/Untitled%201.png)

- ์ด์ ๊ฐ์ ๋ญ๋น๋ ์ ๋ฃ API ๋ฅผ ์ฌ์ฉํ์ ๋ ํฐ ๋ฌธ์  ๋ฐ์(๋น์ฉ์ ์ธ ๋ฌธ์ )
    - ๋ง์ฝ ๊ตฌ๊ธ์ง๋ API ๊ฐ์ ๊ฒ์ ์ฌ์ฉํ  ๋ ์์ ๊ฐ์ด ์ฟผ๋ฆฌ๋ฅผ 10๋ฒ ๋ ๋ฆฌ๋ฉด ํฐ ์ํด๋ฅผ ์๊ฒ ๋จ

๐ ์ด๋ป๊ฒ ํด๊ฒฐํด์ผํ ๊น?

- ๋ณดํต ์ฌ๋๋ค์ ํ์๋ฅผ ์ฐ๋ฌ์์น๋ค. ์ค๊ฐ์ ์ ์ ์๊ฐํ๋๋ผ ๋ช ์ด ์ด ์๋ ์๊ฒ ์ง๋ง ๋๋ถ๋ถ ํ ๋ฒ์ ๊ฒ์์ด๋ฅผ ์๋ ฅํ๋ค. ๋ฐ๋ผ์ ์๋ ฅ์ด ๋ค ๋๋ ํ์ ์์ฒญ์ ๋ณด๋ด๊ณ  ์ถ๋ค. ์ฆ, ํ์๋ฅผ ์น  ๋ (input ์ด๋ฒคํธ ๋ฐ์)๋ง๋ค ํ์ด๋จธ๋ฅผ ์ค์ ํ๊ณ , 200ms๋์ ์๋ ฅ์ด ์์ผ๋ฉด ์๋ ฅ์ด ๋๋ ๊ฒ์ผ๋ก ์น๋ค.(์๊ฐ์ ์ ๋นํ ์ค์ ) ๊ทธ๋ฆฌ๊ณ  *200ms ์ด์ ์ ํ์ ์๋ ฅ์ด ๋ฐ์ํ๋ฉด ์ด์  ํ์ด๋จธ๋ ์ทจ์ํ๊ณ  ์๋ก์ด ํ์ด๋จธ๋ฅผ ๋ค์ ์ค์ *ํ๋ ๊ฒ

```jsx
var timer;
document.querySelector('#input').addEventListener('input', function(e) {
  // ์์ง ํ์ด๋จธ ์ํ๋์ง ์์์ผ๋ฉด(์ง์  ์๋ ฅ์ผ๋ก๋ถํฐ 200ms๊ฐ ์ง๋์ง ์์๋ค๋ฉด) ํ์ด๋จธ ์ทจ์
  // (ํ์ด๋จธ๊ฐ ์กด์ฌํ๋ฉด, ์ฆ ์ง์  ์๋ ฅ์์ ํ์ด๋จธ๋ฅผ ์์ฑํ๋ค๋ฉด)
  if (timer) {
    clearTimeout(timer);
  }
  // ํ์ด๋จธ ์ค์ 
  timer = setTimeout(function() {
    console.log(`api ์์ฒญ : ${e.target.value}`);
  }, 200);
});
```

![Untitled](./day03_data/Untitled%202.png)

<br>

<br>

### ์ฐ๋กํ๋ง(throttling)

- ๋ง์ง๋ง ํจ์๊ฐ ํธ์ถ๋ ํ ์ผ์  ์๊ฐ์ด ์ง๋๊ธฐ ์ ์ ๋ค์ ํธ์ถ๋์ง ์๋๋ก ํ๋ ๊ฒ
- ์ฐ๋กํ๋ง์ ๋ณดํต ์ฑ๋ฅ ๋ฌธ์  ๋๋ฌธ์ ๋ง์ด ์ฌ์ฉํ๋ค. ํน์ฑ ์์ฒด๊ฐ ์คํ ํ์์ ์ ํ์ ๊ฑฐ๋ ๊ฒ์ด๊ธฐ๋ ํจ
- ์คํฌ๋กค์ ์ฌ๋ฆฌ๊ฑฐ๋ ๋ด๋ฆด ๋ scroll ์ด๋ฒคํธ๊ฐ ๋งค์ฐ ๋ง์ด ๋ฐ์, scroll ์ด๋ฒคํธ๊ฐ ๋ฐ์ํ  ๋ ๋ญ๊ฐ ๋ณต์กํ ์์์ ํ๋๋ก ์ค์ ํ๋ค๋ฉด ๋งค์ฐ ๋น๋ฒํ๊ฒ ์คํ๋๊ธฐ ๋๋ฌธ์ ๋ ์ด ๊ฑธ๋ฆด ๊ฒ.
- ๊ทธ๋ด ๋ ์ฐ๋กํ๋ง์ ๊ฑธ์ด์ ๋ช ์ด์ ํ ๋ฒ, ๋๋ ๋ช ๋ฐ๋ฆฌ์ด์ ํ ๋ฒ์ฉ๋ง ์คํ๋๋๋ก ์ ํ์ ๋๋ฉด ๋๋ค.

๐ ์ด๋ป๊ฒ ํด๊ฒฐํด์ผ ํ ๊น?

- ๋๋ฐ์ด์ฑ์ผ๋ก ๊ตฌํํ๋ ๊ฒ์์ ์ฐ๋กํ๋ง์ผ๋ก ๋์ฒดํด๋ ๋จ. ๋๊ฐ์ด 200ms์ด ์ ํ ๊ฑธ์ด๋์๋ค.
- ํ์ด๋จธ๊ฐ ์ค์ ๋์ด ์์ผ๋ฉด ์๋ฌด ๋์๋ ํ์ง ์๊ณ  ํ์ด๋จธ๊ฐ ์๋ค๋ฉด ํ์ด๋จธ๋ฅผ ์ค์ ํ๋ค
- ํ์ด๋จธ๋ ์ผ์  ์๊ฐ ํ์ ์ค์ค๋ก๋ฅผ ํด์ ํ๊ณ  api ์์ฒญ์ ๋ ๋ฆฐ๋ค
- ์ด์  ์ต์ 200๋ฐ๋ฆฌ์ด๋ง๋ค ํ ๋ฒ์ฉ๋ง ์์ฒญ์ ๋ณด๋ด๊ฒ๋ค

```jsx
var timer;
document.querySelector('#input').addEventListener('input', function (e) {
   // ํ์ด๋จธ๊ฐ ์์ ๋๋ง ํ์ด๋จธ ์ค์ .
   // ๋ง์ฝ 200ms๊ฐ ์ง๋์ ํด๋น ํจ์๋ฅผ ์คํํ๋ฉด ํ์ด๋จธ๋ ์ฌ๋ผ์ง๋ค. (timer = null)
   // ๋ง์ฝ ํ์ด๋จธ ์ค์  ํ 200ms๊ฐ ์ง๋์ง ์์๋ค๋ฉด ์๋ฌด ์ผ๋ ์ผ์ด๋์ง ์๋๋ค.
   // ๋ฐ๋ผ์ ์ต์ 200ms ๋ง๋ค ํ๋ฒ์ฉ๋ง ์๋์ ์ฝ๋๊ฐ ์คํ๋๋ค.
   if (!timer) {
      timer = setTimeout(function() {
          timer = null;
          console.log(`api ์์ฒญ : ${e.target.value}`);
      }, 200);
   }
});
```

![Untitled](./day03_data/Untitled%203.png)

โ๏ธ `underscore` ์ `*.debounce` ์* `.throttle` ์ ์ด๋ค๊ณ  ํจ! 

<br>

<br>

<br>

## ์ด๋ฒคํธ ๋ฒ๋ธ๋ง & ์บก์ณ๋ง & ์์

### HTML ์ด๋ฒคํธ์ ํ๋ฆ

- HTML ๋ฌธ์์ ๊ฐ ์๋ฆฌ๋จผํธ๋ค์ ์๋์ ๊ฐ์ด ํ๊ทธ ์์ ํ๊ทธ๊ฐ ์์นํ๋ ์์ผ๋ก ๊ณ์ธต์ ์ผ๋ก ์ด๋ฃจ์ด์ ธ์๋ค. ์ด๋ฌํ ํน์ง ๋๋ฌธ์ ๋ง์ฝ HTML ์์์ ์ด๋ฒคํธ๊ฐ ๋ฐ์ํ  ๊ฒฝ์ฐ ์ฐ์์  ์ด๋ฒคํธ ํ๋ฆ์ด ์ผ์ด๋๊ฒ๋๋ค.

```html
<form onclick="alert('form')">FORM
    <div onclick="alert('div')">DIV
    	<p onclick="alert('p')">P</p>
    </div>
</form>
```

- ์๋ฅผ๋ค์ด ์๋ 3๊ฐ๊ฐ ์ค์ฒฉ๋ ๋ฐ์ค ์์ญ์์ ๊ฐ์ฅ ์์  ์๋ฆฌ๋จผํธ์ธ p ๋ฐ์ค๋ฅผ ํด๋ฆญํ๋ฉด onclick ์ด๋ฒคํธ ์คํฌ๋ฆฝํธ๊ฐ p ๋ฟ๋ง ์๋๋ผ ๊ทธ์ ๋ถ๋ชจ์ธ div์ form ์๋ฆฌ๋จผํธ๋ ๋ฐ์
- ์ด๋ฌํ ํ์์ ์ด๋ฒคํธ ์ ํ(Event Propagation)์ด๋ผ๊ณ  ๋ถ๋ฅด๋ฉฐ, ์ ํ ๋ฐฉํฅ์ ๋ฐ๋ผ ๋ฒ๋ธ๋ง๊ณผ ์บก์ณ๋ง์ผ๋ก ๊ตฌ๋ถ

![Untitled](./day03_data/Untitled%204.png)

 

<br>

<br>

### ๋ฒ๋ธ๋ง(Bubbling)

- ์์ ์์์์ ๋ฐ์ํ ์ด๋ฒคํธ๊ฐ ๋ฐ๊นฅ ๋ถ๋ชจ ์์๋ก ์ ํ(๊ธฐ๋ณธ๊ฐ)
- ์ด๋ฒคํธ๊ฐ ์ ์ผ ๊น์ ๊ณณ์ ์๋ ์์์์ ์์ํด ๋ถ๋ชจ ์์๋ฅผ ๊ฑฐ์ฌ๋ฌ ์ฌ๋ผ๊ฐ๋ฉฐ ๋ฐ์ํ๋ ๋ชจ์์ด ๋ง์น ๋ฌผ์ ๊ฑฐํ(bubble)๊ณผ ๋ฎ์๊ธฐ ๋๋ฌธ์ ์ง์ด์ง ์ด๋ฆ

![Untitled](./day03_data/Untitled%205.png)

<br>

<br>

### ๋ฒ๋ธ๋ง ๋ฑ๋ก

- ๋ธ๋ผ์ฐ์ ์ ์ด๋ฒคํธ๋ ๊ธฐ๋ณธ์ ์ผ๋ก ๋ฒ๋ธ๋ง ๋ฐฉ์์ผ๋ก ์ด๋ฒคํธ๊ฐ ์ ํ๋๋ค
- ์๋ฐ์คํฌ๋ฆฝํธย `addEventListener()`
ย ํจ์๋ก ์์์ ์ด๋ฒคํธ๋ฅผ ๋ฑ๋กํ๋ฉด ๊ธฐ๋ณธ์ ์ผ๋ก ๋ฒ๋ธ๋ง ์ ํ ๋ฐฉ์์ผ๋ก ์ด๋ฒคํธ๊ฐ ํ๋ฅด๊ฒ ๋์ด, ๋ง์ผ ์์ ์์์ ์ด๋ฒคํธ๊ฐ ๋ฐ์ํ๋ฉด ๋ถ๋ชจ ์์๋ ๋ฒ๋ธ๋ง ํตํด ์ด๋ฒคํธ๊ฐ ์ ํ๋์ด ๋ฆฌ์ค๋๊ฐ ํธ์ถ

![Untitled](./day03_data/Untitled%206.png)

```jsx
// ๋ฒ๋ธ๋ง ๋์ (false ์๋ต ํด๋๋จ)
element.addEventListener('click', (e) => { ... }, false);
```

โ๏ธ ๊ฑฐ์ ๋ชจ๋  ์ด๋ฒคํธ๋ ๋ฒ๋ธ๋ง์ด ๋๋ค๊ณ  ๋ณด๋ฉด ๋๋ค. ๋ค๋ง `focus` ์ด๋ฒคํธ์ ๊ฐ์ด ๋ฒ๋ธ๋ง์ด ๋์ง ์๋ ์ด๋ฒคํธ๋ ์กด์ฌํ๊ธฐ๋ ํ๋ค.

<br>

<br>

### ์บก์ณ๋ง(Capturing)

- ํ ์์์ ์ด๋ฒคํธ๊ฐ ๋ฐ์๋๋ฉด, ๊ทธ ์์์ ์์ ์์์ ์ด๋ฒคํธ๋ ๊ฐ์ด ๋ฐ์๋๋ ์ด๋ฒคํธ ์ ํ

![Untitled](./day03_data/Untitled%207.png)

<br>

<br>

### ์บก์ณ๋ง ๋ฑ๋ก

- ๋ธ๋ผ์ฐ์ ์ ์ด๋ฒคํธ ์ ํ ๋ฐฉ์์ ๋ฒ๋ธ๋ง์ด ๊ธฐ๋ณธ๊ฐ์ด๊ธฐ ๋๋ฌธ์ ์บก์ฒ๋ง์ผ๋ก ์ค์ ํ๊ธฐ ์ํด์  ๋ณ๋์ ์ต์์ ํจ์์ ์ฃผ์ด์ผ ํ๋ค. ์๋ฐ์คํฌ๋ฆฝํธย `addEventListener()`
ย ํจ์์ 3๋ฒ์งธ ๋งค๊ฐ๋ณ์๋ก true ๊ฐ์ ์ฃผ๋ฉด ์ด ์ด๋ฒคํธ ํ๊ฒ์ ์บก์ฒ๋ง์ ํตํด ์ด๋ฒคํธ๋ฅผ ์ ํ๋ฐ์ ํธ์ถํ๊ฒ ๋๋ค.

![Untitled](./day03_data/Untitled%208.png)

```jsx
// ์บก์ฒ๋ง ๋์
element.addEventListener('click', (e) => { ... }, true);
element.addEventListener('click', (e) => { ... }, {capture: true});
```

<aside>
๐ก ์ด๋ ๊ฒ ์ต์ ์ค์ ์ ํตํด ๋ฒ๋ธ๋ง or ์บก์ฒ๋ง ์ด๋ฒคํธ ์ ํ ๋์์ผ๋ก ๋ฑ๋กํ๋ ์ด์ ๋, ๋ธ๋ผ์ฐ์ ๋ ์บก์ณ๋ง์ผ๋ก ํ์ํ๊ณ  ๋ฒ๋ธ๋ง์ผ๋ก ๋์์ค๋๋ฐ ๊ฐ๋ค๊ฐ ๋์์ค๋ ๊ณผ์ ์์ ์ด๋ฒคํธ๊ฐ ๋๊ฐ์ด ๋๋ฒ ์คํํ๊ธฐ ๋๋ฌธ

</aside>

<br>

<br>

### **๐ ๋ฒ๋ธ๋ง & ์บก์ณ๋ง ๋ฌธ์ ์ **

- ๋ง์ฝ ๋ถ๋ชจ์ ์์ ๋ ๋ค ์ด๋ฒคํธ๋ฅผ ๋ฑ๋กํ ์ํ์์, ์์ ์์๋ง ํด๋ฆญํ์ ๋ ์ด๋ฒคํธ๋ฅผ ๋ฐ์ํ๊ณ  ๋ถ๋ชจ ์์๋ ์ด๋ฒคํธ๋ฅผ ๋ฐ์์ํค๊ณ  ์ถ์ง ์์ ์ํฉ์์๋ ?
- ์ด๋ฒคํธ ์ ํ๋ฅผ ๋ฐฉ์ง ์ฒ๋ฆฌํ๋ ์์ผ๋ก ํด๊ฒฐํด์ผํจ.
- `stopPropagation()` ๋ฉ์๋ ํธ์ถํ๋ฉด ๋ฒ๋ธ๋ง ๋๋ ์บก์ฒ๋ง ์ค์ ์ ๋ฐ๋ผ ์์, ํ์๋ก ๊ฐ๋ ์ด๋ฒคํธ ์ ํ๋ฅผ ๋ง์ ์ ์๋ค.
- `stopImmediatePropagation()` ๋ฉ์๋๋ฅผ ํธ์ถํ๋ฉด, ์ด๋ฒคํธ ์ ํ์ ๋๋ถ์ด ํ์  ์ด๋ฒคํธ ์คํ์ ์ค์งํ๋ค. ๊ฐ์ด ๋์ผํ child ์์์ ์ด๋ฒคํธ ๋ฆฌ์ค๋๊ฐ 2๊ฐ ๋ฑ๋ก ๋์ด ์์๋, ์ด๋ ํ ์กฐ๊ฑด์์ ํด๋ฆญ ์ด๋ฒคํธ๋ฅผ ๋๋ฒ ์คํํ์ง ์๊ณ  ํ๋ฒ๋ง ์คํํ ๋ก ํ๊ธธ ์ํ๋ค๋ฉด ์ ์ฉ

<br>

<br>

### ์ด๋ฒคํธ ์์ (Event Delegation)

- ํ์ ์์์ ๊ฐ๊ฐ ์ด๋ฒคํธ๋ฅผ ๋ถ์ด์ง ์๊ณ  ์์ ์์์์ ํ์ ์์์ ์ด๋ฒคํธ๋ค์ ์ ์ดํ๋ ๋ฐฉ์
- ๋ฆฌ์คํธ ์์ดํ์ด ๋ง์์ง๋ฉด ๋ง์์ง์๋ก ์ด๋ฒคํธ ๋ฆฌ์ค๋๋ฅผ ๋ค๋ ์์ ์์ฒด๊ฐ ๋งค์ฐ ๋ฒ๊ฑฐ๋กญ๋ค. ์ด๋ฒคํธ ์์์ ์ด ๋ฒ๊ฑฐ๋ก์ด ์์์ ํด๊ฒฐํ  ์ ์๋ ๋ฐฉ๋ฒ์ด๋ค.

```jsx
var itemList = document.querySelector('.itemList');
itemList.addEventListener('click', function(event) {
	alert('clicked');
});
```

- ํ๋ฉด์ ๋ชจ๋  ์ธํ ๋ฐ์ค์ ์ผ์ผ์ด ์ด๋ฒคํธ ๋ฆฌ์ค๋๋ฅผ ์ถ๊ฐํ๋ ๋์  ์ด์ ๋ ์ธํ ๋ฐ์ค์ ์์ ์์์ธ ul ํ๊ทธ,ย `.itemList`์ ์ด๋ฒคํธ ๋ฆฌ์ค๋๋ฅผ ๋ฌ์๋๊ณ  ํ์์์ ๋ฐ์ํ ํด๋ฆญ ์ด๋ฒคํธ๋ฅผ ๊ฐ์งํ๋ค. ์ด ๋ถ๋ถ์ด ์ด๋ฒคํธ ๋ฒ๋ธ๋ง.

<br>

<br>

<br>

## ํต์  ๋ฐ ๋น๋๊ธฐ

### XMLHttpRequest ๊ฐ์ฒด

- Ajax์ ๊ฐ์ฅ ํต์ฌ์ ์ธ ๊ตฌ์ฑ ์์๋ XMLHttpRequest ๊ฐ์ฒด์ด๊ณ , ์น ๋ธ๋ผ์ฐ์ ๊ฐ ์๋ฒ์ ๋ฐ์ดํฐ๋ฅผ ๊ตํํ  ๋ ์ฌ์ฉ๋๋ค.
- ์น ๋ธ๋ผ์ฐ์ ๊ฐ ๋ฐฑ๊ทธ๋ผ์ด๋์์ ๊ณ์ํด์ ์๋ฒ์ ํต์ ํ  ์ ์๋ ๊ฒ์ ๋ฐ๋ก ์ด ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ๊ธฐ ๋๋ฌธ.

<br>

<br>

### XMLHttpRequest ๊ฐ์ฒด์ ์์ฑ

- ํ์ฌ ๋๋ถ๋ถ์ ์ฃผ์ ์น ๋ธ๋ผ์ฐ์ ๋ XMLHttpRequest ๊ฐ์ฒด๋ฅผ ๋ด์ฅํ๊ณ  ์๋ค.
- ๋ธ๋ผ์ฐ์ ์ ์ข๋ฅ์ ๋ฐ๋ผ ๊ฐ์ฒด ์์ฑ ๋ฐฉ๋ฒ์ด 2๊ฐ์ง๋ก ๋๋๋ค.
    - XMLHttpRequest ๊ฐ์ฒด๋ฅผ ์ด์ฉํ ๋ฐฉ๋ฒ
        - ์ต์คํ๋ก๋ฌ7, ๊ทธ ์ด์, ํฌ๋กฌ, ํ์ด์ดํญ์ค, ์ฌํ๋ฆฌ, ์คํ๋ผ
    - ActiveXObject ๊ฐ์ฒด๋ฅผ ์ด์ฉํ ๋ฐฉ๋ฒ
        - ์ต์คํ๋ก๋ฌ 5, 6

```jsx
var httpRequest;
function createRequest() {
    if (window.XMLHttpRequest) { // ์ต์คํ๋ก๋ฌ 7๊ณผ ๊ทธ ์ด์์ ๋ฒ์ , ํฌ๋กฌ, ํ์ด์ดํญ์ค, ์ฌํ๋ฆฌ, ์คํ๋ผ ๋ฑ
        return new XMLHttpRequest();
    } else {                     // ์ต์คํ๋ก๋ฌ 6๊ณผ ๊ทธ ์ดํ์ ๋ฒ์ 
        return new ActiveXObject("Microsoft.XMLHTTP");
    }
}

// ํ์ง๋ง ํ์ฌ ์ต์คํ๋ก๋ฌ 6๊ณผ ๊ทธ ์ดํ ๋ฒ์ ์ ์ฌ์ฉํ๋ ์ฌ์ฉ์๋ ๊ฑฐ์ ์์ผ๋ฏ๋ก
// XMLHttpRequest ๊ฐ์ฒด๋ฅผ ์ผ๋ฐ์ ์ผ๋ก ์ฌ์ฉํ๋ค
var httpRequest = new XMLHttpRequest(); 
```

<br>

<br>

### ์๋ฒ์ ์์ฒญ(request)ํ๊ธฐ

- Ajax์์๋ XMLHttpRequest ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ์ฌ ์๋ฒ์ ๋ฐ์ดํฐ๋ฅผ ๊ตํ
- ๋ฐ๋ผ์ ์๋ฒ ์์ฒญ์ ๋ณด๋ด๊ธฐ ์ํด์๋ ์ฐ์  XMLHttpRequest ์ธ์คํด์ค ์์ฑ
    - `open()` ๋ฉ์๋ : ์๋ฒ๋ก ๋ณด๋ผ Ajax ์์ฒญ์ ํ์ ์ค์ 
        - ์ ๋ฌ ๋ฐฉ์์ ์์ฒญ์ ์ ๋ฌํ  ๋ฐฉ์์ผ๋ก `GET` ๋ฐฉ์๊ณผ `POST` ๋ฐฉ์ ์ค ์ ํ
        - URL ์ฃผ์๋ ์์ฒญ์ ์ฒ๋ฆฌํ  ์๋ฒ์ ํ์ผ ์ฃผ์ ์ ๋ฌ
        - ๋๊ธฐ ์ฌ๋ถ๋ ์์ฒญ์ ๋๊ธฐ์์ผ๋ก ์ ๋ฌํ ์ง ๋น๋๊ธฐ์์ผ๋ก ์ ๋ฌํ ์ง๋ฌ
    
    ```jsx
    open(์ ๋ฌ๋ฐฉ์, URL์ฃผ์, ๋๊ธฐ์ฌ๋ถ);
    ```
    
    - `send()` ๋ฉ์๋ : ์์ฑ๋ AJax ์์ฒญ์ ์๋ฒ๋ก ์ ๋ฌ
        - ์ ๋ฌ ๋ฐฉ์์ ๋ฐ๋ผ ์ธ์๋ฅผ ๊ฐ์ง ์๋ ์๊ฐ์ง ์๋ ์๋ค
    
    ```jsx
    send();       // GET ๋ฐฉ์
    send(๋ฌธ์์ด); // POST ๋ฐฉ์
    ```
    

<br>

<br>

๐ **`GET` ๋ฐฉ์๊ณผ `POST` ๋ฐฉ์**

`GET`

- ์ฃผ์์ ๋ฐ์ดํฐ๋ฅผ ์ถ๊ฐํ์ฌ ์ ๋ฌ
- GET๋ฐฉ์์ HTTP ์์ฒญ์ ๋ธ๋ผ์ฐ์ ์ ์ํด ์บ์๋์ด(cached) ์ ์ฅ๋จ
- GET ๋ฐฉ์์ ๋ณดํต ์ฟผ๋ฆฌ ๋ฌธ์์ด(query string)์ ํฌํจ๋์ด ์ ์ก๋๋ฏ๋ก ๊ธธ์ด์ ์ ํ์ด ์์

`POST`

- ๋ฐ์ดํฐ๋ฅผ ๋ณ๋๋ก ์ฒจ๋ถํ์ฌ ์ ๋ฌ
- ๋ธ๋ผ์ฐ์ ์ ์ํด ์บ์๋์ง ์์ผ๋ฏ๋ก ๋ธ๋ผ์ฐ์  ํ์คํ ๋ฆฌ์ ๋จ์ง ์๋๋ค
- ์ฟผ๋ฆฌ ๋ฌธ์์ด๊ณผ๋ ๋ณ๋๋ก ์ ์ก
- ๋ฐ์ดํฐ ๊ธธ์ด ์ ํ ์๊ณ  GET๋ฐฉ์๋ณด๋ค ๋ณด์์ฑ์ด ๋๋ค

<aside>
๐ก Ajax์์๋ ์ฃผ๋ก GET๋ฐฉ์๋ณด๋ค๋ POST๋ฐฉ์์ ์ฌ์ฉํ์ฌ ์์ฒญ์ ์ ์ก๋ค

</aside>

<br>

<br>

๐ **URI ์ URL ์ ์ฐจ์ด**

![Untitled](./day03_data/Untitled%209.png)

`URL` (Uniform Resource Identifier) : ์ธํฐ๋ท์ ์๋ ์์์ ๋ํ๋ด๋ ์ ์ผํ ์ฃผ์

<br>

<br>

### `GET` ๋ฐฉ์์ผ๋ก ์์ฒญ

- ์๋ฒ๋ก ์ ์กํ๊ณ ์ ํ๋ ๋ฐ์ดํฐ๋ URI์ ํฌํจ๋์ด ์ ์ก

```jsx
// GET ๋ฐฉ์์ผ๋ก ์์ฒญ์ ๋ณด๋ด๋ฉด์ ๋ฐ์ดํฐ๋ฅผ ๋์์ ์ ๋ฌํจ.
httpRequest.open("GET", "/examples/media/request_ajax.php?city=Seoul&zipcode=06141", true);
httpRequest.send();

if (httpRequest.readyState == XMLHttpRequest.DONE && httpRequest.status == 200 ) {
    ...
}
```

- eadyState ํ๋กํผํฐ์ ๊ฐ์ด XMLHttpRequest.DONE์ด๋ฉด, ์๋ฒ์ ์์ฒญํ ๋ฐ์ดํฐ์ ์ฒ๋ฆฌ๊ฐ ์๋ฃ๋์ด ์๋ตํ  ์ค๋น๊ฐ ์๋ฃ๋์๋ค๋ ์๋ฏธ
- status ํ๋กํผํฐ์ ๊ฐ์ด 200์ด๋ฉด, ์์ฒญํ ๋ฌธ์๊ฐ ์๋ฒ ์์ ์กด์ฌํ๋ค๋ ์๋ฏธ

<br>

<br>

### `POST` ๋ฐฉ์์ผ๋ก ์์ฒญ

- ์๋ฒ๋ก ์ ์กํ๊ณ ์ ํ๋ ๋ฐ์ดํฐ๋ HTTP ํค๋์ ํฌํจ๋์ด ์ ์ก
- ๋ฐ๋ผ์ `setRequestHeader()` ๋ฉ์๋๋ฅผ ์ด์ฉํ์ฌ ๋จผ์  ํค๋ ์์ฑํ ํ `send()` ๋ฉ์๋๋ก ๋ฐ์ดํฐ ์ ์ก

```jsx
// POST ๋ฐฉ์์ ์์ฒญ์ ๋ฐ์ดํฐ๋ฅผ Http ํค๋์ ํฌํจ์์ผ ์ ์กํจ.
httpRequest.open("POST", "/examples/media/request_ajax.php", true);
httpRequest.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
httpRequest.send("city=Seoul&zipcode=06141");
```

<br>

<br>

### ์๋ฒ๋ก๋ถํฐ์ ์๋ต(response)

- Ajax์์ ์๋ฒ๋ก๋ถํฐ์ ์๋ต์ ํ์ธํ๊ธฐ ์ํด ์ฌ์ฉํ๋ XMLHttpRequest ๊ฐ์ฒด์ ํ๋กํผํฐ๋ ๋ค์๊ณผ ๊ฐ๋ค
    - `readyState` ํ๋กํผํฐ : XMLHttpRequest ๊ฐ์ฒด์ ํ์ฌ ์ํ๋ฅผ ๋ํ๋
        - UNSENT (์ซ์ 0) : XMLHttpRequest ๊ฐ์ฒด๊ฐ ์์ฑ๋จ.
        - OPENED (์ซ์ 1) : open() ๋ฉ์๋๊ฐ ์ฑ๊ณต์ ์ผ๋ก ์คํ
        - HEADERS_RECEIVED (์ซ์ 2) : ๋ชจ๋  ์์ฒญ์ ๋ํ ์๋ต์ด ๋์ฐฉ
        - LOADING (์ซ์ 3) : ์์ฒญํ ๋ฐ์ดํฐ๋ฅผ ์ฒ๋ฆฌ ์ค
        - DONE (์ซ์ 4) : ์์ฒญํ ๋ฐ์ดํฐ์ ์ฒ๋ฆฌ๊ฐ ์๋ฃ๋์ด ์๋ตํ  ์ค๋น ์๋ฃ
    - `status` ํ๋กํผํฐ : ์๋ฒ์ ๋ฌธ์ ์ํ๋ฅผ ๋ํ๋
        - 200 : ์๋ฒ์ ๋ฌธ์๊ฐ ์กด์ฌ
        - 404 : ์๋ฒ์ ๋ฌธ์๊ฐ ์กด์ฌํ์ง ์์
    - `onreadystatechange` ํ๋กํผํฐ : XMLHttpRequest ๊ฐ์ฒด์ readyState ํ๋กํผํฐ ๊ฐ์ด ๋ณํ  ๋๋ง๋ค ์๋์ผ๋ก ํธ์ถ๋๋ ํจ์๋ฅผ ์ค์ 
        - ์ด ํจ์๋ ์๋ฒ์์ ์๋ต์ด ๋์ฐฉํ  ๋๊น์ง readyState ํ๋กํผํฐ ๊ฐ์ ๋ณํ์ ๋ฐ๋ผ ์ด 5๋ฒ ํธ์ถ
        - ์ด ํ๋กํผํฐ๋ฅผ ์ด์ฉํ๋ฉด ์๋ฒ์ ์์ฒญํ ๋ฐ์ดํฐ๊ฐ ์กด์ฌํ๊ณ , ์๋ฒ๋ก๋ถํฐ ์๋ต์ด ๋์ฐฉํ๋ ์๊ฐ์ ํน์ ํ  ์ ์๋ค.

```jsx

switch (httpRequest.readyState) {
    case XMLHttpRequest.UNSET:
        currentState += "ํ์ฌ XMLHttpRequest ๊ฐ์ฒด์ ์ํ๋ UNSET ์๋๋ค.<br>";
        break;
    case XMLHttpRequest.OPENED:
        currentState += "ํ์ฌ XMLHttpRequest ๊ฐ์ฒด์ ์ํ๋ OPENED ์๋๋ค.<br>";
        break;
    case XMLHttpRequest.HEADERS_RECIEVED:
        currentState += "ํ์ฌ XMLHttpRequest ๊ฐ์ฒด์ ์ํ๋ HEADERS_RECEIVED ์๋๋ค.<br>";
        break;
    case XMLHttpRequest.LOADING:
        currentState += "ํ์ฌ XMLHttpRequest ๊ฐ์ฒด์ ์ํ๋ LOADING ์๋๋ค.<br>";
        break;
    case XMLHttpRequest.DONE:
        currentState += "ํ์ฌ XMLHttpRequest ๊ฐ์ฒด์ ์ํ๋ DONE ์๋๋ค.<br>";
        break;
}
document.getElementById("status").innerHTML = currentState;
if (httpRequest.readyState == XMLHttpRequest.DONE && httpRequest.status == 200 ) {
document.getElementById("text").innerHTML = httpRequest.responseText;
}
```

<br>

<br>

### HTTP ํค๋

- ํด๋ผ์ด์ธํธ์ ์๋ฒ ์ฌ์ด์ ์ด๋ฃจ์ด์ง๋ HTTP ์์ฒญ๊ณผ ์๋ต์ HTTP ํค๋๋ฅผ ์ฌ์ฉํ์ฌ ์ํ
- HTTP ํค๋๋ ํด๋ผ์ด์ธํธ์ ์๋ฒ๊ฐ ์๋ก์๊ฒ ์ ๋ฌํด์ผ ํ  ๋ค์ํ ์ข๋ฅ์ ๋ฐ์ดํฐ๋ฅผ ํฌํจํ  ์ ์๋ค.

<br>

<br>

### HTTP ์์ฒญ ํค๋

- Ajax์์๋ ์์ฒญ์ ๋ณด๋ด๊ธฐ ์ ์ `setRequestHeader()` ๋ฉ์๋๋ฅผ ์ฌ์ฉํ์ฌ HTTP ์์ฒญ ํค๋๋ฅผ ์์ฑํ  ์ ์๋ค.

```jsx
XMLHttpRequest์ธ์คํด์ค.setRequestHeader(ํค๋์ด๋ฆ, ํค๋๊ฐ);

// ์์ 
var httpRequest = new XMLHttpRequest();
httpRequest.onreadystatechange = function() {
    if (httpRequest.readyState == XMLHttpRequest.DONE && httpRequest.status == 200 ) {
        document.getElementById("text").innerHTML = httpRequest.responseText;
    }
};
httpRequest.open("GET", "/examples/media/ajax_request_header.php", true)
httpRequest.setRequestHeader("testheader", "123");
httpRequest.send();
```

โ๏ธ HTTP ๊ท์ฝ์์ ์ฌ์ฉํ๋ ํค๋ ์ด๋ฆ์ ๋ชจ๋ ์ฒซ ๊ธ์๊ฐ ์๋ฌธ ๋๋ฌธ์์ด๋ค. 

<br>

<br>

### HTTP ์๋ต ํค๋

- `getAllResponseHeaders()` ๋ฉ์๋ : HTTP ์๋ต ํค๋์ ๋ชจ๋  ํค๋๋ฅผ *๋ฌธ์์ด๋ก* ๋ฐํ
- `getResponseHeader()` ๋ฉ์๋ : HTTP ์๋ต ํค๋ ์ค ์ธ์๋ก ์ ๋ฌ๋ฐ์ ์ด๋ฆ๊ณผ *์ผ์นํ๋* ํค๋์ ๊ฐ์ ๋ฌธ์์ด๋ก ๋ฐํ

```jsx
var httpRequest = new XMLHttpRequest();
httpRequest.onreadystatechange = function() {
    if (httpRequest.readyState == XMLHttpRequest.DONE && httpRequest.status == 200 ) {
        document.getElementById("text").innerHTML = httpRequest.responseText;
				document.getElementById("header").innerHTML = httpRequest.getAllResponseHeaders();
        document.getElementById("user").innerHTML =
            "testheader: " + httpRequest.getResponseHeader("testheader");
    }
};
httpRequest.open("GET", "/examples/media/ajax_response_header.php", true);
httpRequest.send();
```

<br>

<br>

<br>

### CORS(Cross-Origin Resource Sharing) ๊ต์ฐจ ์ถ์ฒ ๋ฆฌ์์ค ๊ณต์  ์ ์ฑ

- ๋ค๋ฅธ ์ถ์ฒ์ ๋ฆฌ์์ค ๊ณต์ ์ ๋ํ ํ์ฉ / ๋นํ์ฉ ์ ์ฑ
- ์๋ฌด๋ฆฌ ๋ณด์์ด ์ค์ํ์ง๋ง, ๊ฐ๋ฐ์ ํ๋ค ๋ณด๋ฉด ๊ธฐ๋ฅ์ ์ด์ฉ ์ ์์ด ๋ค๋ฅธ ์ถ์ฒ ๊ฐ์ ์ํธ์์ฉ์ ํด์ผํ๋ ์ผ์ด์ค๋ ์์ผ๋ฉฐ, ์ค๋ฌด์ ์ผ๋ก ๋ค๋ฅธ ํ์ฌ์ ์๋ฒ API๋ฅผ ์ด์ฉํด์ผ ํ๋ ์ํฉ ์กด์ฌ
- ๋ฐ๋ผ์ ์ด์ ๊ฐ์ ์์ธ ์ฌํญ์ ๋๊ธฐ ์ํด CORS ์ ์ฑ์ ํ์ฉํ๋ ๋ฆฌ์์ค์ ํํด ๋ค๋ฅธ ์ถ์ฒ๋ผ๋ ๋ฐ์๋ค์ธ๋ค๋ ๊ฒ

๐ **CORS๋ฅผ ํด๊ฒฐํ๋ ๋ฐฉ๋ฒ**

- Chrome ํ์ฅ ํ๋ก๊ทธ๋จ ์ด์ฉ
    - ํฌ๋กฌ์์๋ CORS ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํ ํ์ฅ ํ๋ก๊ทธ๋จ์ ์ ๊ณตํด์ค๋ค.
    - ์๋ฒ ํ์คํธ ํ๊ฒฝ์์ ๊ณ ๋ฏผํ์ง ์๊ณ  ๋น ๋ฅด๊ฒ CORS๋ฅผ ํด๊ฒฐํ๋๋ฐ ์ข์ ์ ํ์ง์ผ ๊ฒ.
- ํ๋ก์ ์ฌ์ดํธ ์ด์ฉํ๊ธฐ
    - ํ๋ก์(Proxy)๋ ํด๋ผ์ด์ธํธ์ ์๋ฒ ์ฌ์ด์ ์ค๊ณ ๋๋ฆฌ์ ์ด๋ผ๊ณ  ๋ณด๋ฉด ๋๋ค.
    - ์ฆ, ํ๋ก ํธ์์ ์ง์  ์๋ฒ์ ๋ฆฌ์์ค๋ฅผ ์์ฒญ ํ๋๋ ์๋ฒ์์ ๋ฐ๋ก ์ค์ ์ ์ํด์ค์ CORS์๋ฌ๊ฐ ๋ฌ๋ค๋ฉด, ๋ชจ๋  ์ถ์ฒ๋ฅผ ํ์ฉํ ์๋ฒ ๋๋ฆฌ์ ์ ํตํด ์์ฒญํ๋ฉด ๋๋ ๊ฒ.
    - ๋ค๋ง ํ์ฌ ๋ฌด๋ฃ ํ๋ก์ ์๋ฒ ๋์ฌ ์๋น์ค๋ค์ ๋ชจ๋ ์์ฉ ์ฌ๋ก ๋๋ฌธ์ api ์์ฒญ ํ์ ์ ํ์ ๋์ด ์ค์ ์์๋ ์ฌ์ฉํ๊ธฐ ๋ฌด๋ฆฌ. ๋ฐ๋ผ์ ํ์คํธ์ฉ์ด๋ ๋ง๋ณด๊ธฐ์ฉ์ผ๋ก ์ฌ์ฉํ๋, ์ค์ ์์๋ ์ง์  ํ๋ก์ ์๋ฒ๋ฅผ ๊ตฌ์ถํ์ฌ ์ฌ์ฉํด์ผ ํ๋ค.
- ์๋ฒ์์ Access-Control-Allow-Origin ํค๋ ์ธํํ๊ธฐ
    - ์ง์  ์๋ฒ์์ HTTP ํค๋ ์ค์ ์ ํตํด ์ถ์ฒ๋ฅผ ํ์ฉํ๊ฒ ์ค์ ํ๋ ๊ฐ์ฅ ์ ์์ ์ธ ํด๊ฒฐ์ฑ

<br>

<br>

<br>

## `Promise`

### promise๋?

- ๋น๋๊ธฐ ์ฒ๋ฆฌ์ ์ฌ์ฉ๋๋ ๊ฐ์ฒด.
    - ํน์  ์ฝ๋์ ์คํ์ด ์๋ฃ๋  ๋๊น์ง ๊ธฐ๋ค๋ฆฌ์ง ์๊ณ  ๋ค์ ์ฝ๋๋ฅผ ๋จผ์  ์ํํ๋ ์๋ฐ์คํฌ๋ฆฝํธ์ ํน์ฑ

<br>

<br>

### promise๊ฐ ์ ํ์ํ๊ฐ?

- ํ๋ก๋ฏธ์ค๋ ์ฃผ๋ก ์๋ฒ์์ ๋ฐ์์จ ๋ฐ์ดํฐ๋ฅผ ํ๋ฉด์ ํ์ํ  ๋ ์ฌ์ฉํ๋ค
- ์ผ๋ฐ์ ์ผ๋ก ์น ์ ํ๋ฆฌ์ผ์ด์์ ๊ตฌํํ  ๋ ์๋ฒ์์ ๋ฐ์ดํฐ๋ฅผ ์์ฒญํ๊ณ  ๋ฐ์์ค๊ธฐ ์ํด ์๋์ ๊ฐ์ API๋ฅผ ์ฌ์ฉ

```jsx
$.get('url ์ฃผ์/products/1', function(response) {
  // ...
});
```

```jsx
function getData() {
  return new Promise(function(resolve, reject) {
    $.get('url ์ฃผ์/products/1', function(response) {
      if (response) {
        resolve(response);
      }
      reject(new Error("Request is failed"));
    });
  });
}

// ์ $.get() ํธ์ถ ๊ฒฐ๊ณผ์ ๋ฐ๋ผ 'response' ๋๋ 'Error' ์ถ๋ ฅ
getData().then(function(data) {
  console.log(data); // response ๊ฐ ์ถ๋ ฅ
}).catch(function(err) {
  console.error(err); // Error ์ถ๋ ฅ
});
```

- ์ ์ฝ๋๋ ์๋ฒ์์ ์ ๋๋ก ์๋ต์ ๋ฐ์์ค๋ฉด `resolve()` ๋ฉ์๋ ํธ์ถ
- ์๋ต ์์ผ๋ฉด `reject()` ํธ์ถ, ํธ์ถ๋ ๋ฉ์๋์ ๋ฐ๋ผ `then()` ์ด๋ `catch()` ๋ก ๋ถ๊ธฐํ์ฌ ์๋ต ๊ฒฐ๊ณผ ๋๋ ์ค๋ฅ ์ถ๋ ฅ

<br>

<br>

### `fetch` `then` ๋ฐ์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ๊บผ๋ด๋ ค๋ฉด?!

> JS ์์๋ `fetch()` ํจ์๋ฅผ ์ด์ฉํด์ resource๋ฅผ ๋น๋๊ธฐ ์์ฒญํ  ์ ์๋ค
์ฃผ๋ก API๋ฅผ ํธ์ถํ๊ณ  ์๋ต ๋ฐ์ดํฐ๋ฅผ ๋ฐ์์ค๋๋ฐ ์ฌ์ฉํ๋ค
> 

```jsx
fetch('https://jsonplaceholder.typicode.com/posts/1')
.then(response => response.json())
.then(json => console.log(json))

// ์ถ๋ ฅ
{
  "userId": 1,
  "id": 1,
  "title": '.....',
  "body": '....'
}
```

1. `fetch()` ์์๋ ๊ธฐ๋ณธ์ ์ผ๋ก ์์ฒญํ  url์ ๋ฃ๋๋ค.
2. get,post,put,delete์ค default๊ฐ์ผ๋ก๋ get์ผ๋ก ๋์ํ๋ค.
3. ํด๋น ์ฃผ์์ ์์ฒญ์ ํ๊ณ  ์๋ต๊ฐ์ฒด(object response)๋ฅผ ๋ฐ๋๋ค.
4. ์ฒซ๋ฒ์งธ `.then()`์์ ์๋ต์ ๋ฐ๊ณ  `.json()` ๋ฉ์๋๋ก ํ์ฑํ `json()`๊ฐ์ ๋ฆฌํด
5. ๋๋ฒ์งธ `.then()`์์ ๋ฆฌํด๋ฐ์ json๊ฐ์ ๋ฐ๊ณ , ์ํ๋๋๋ก ์ฒ๋ฆฌ๊ฐ ๊ฐ๋ฅ!

<br>

<br>

<br>

## API

### API๋?

- Application Programming Interface
- ์ ํ๋ฆฌ์ผ์ด์์ด๋ ๋๋ฐ์ด์ค๊ฐ ์๋ก ๊ฐ์ ์ฐ๊ฒฐํ์ฌ ํต์ ํ  ์ ์๋ ๋ฐฉ๋ฒ์ ์ ์ํ๋ ๊ท์น

<br>

<br>

### REST API๋?

- REST๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ์๋น์ค API๋ฅผ ๊ตฌํํ ๊ฒ
    - REST๋? Representational State Transfer : HTTP๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ํด๋ผ์ด์ธํธ๊ฐ ์๋ฒ์ ๋ฆฌ์์ค์ ์ ๊ทผํ๋ ๋ฐฉ์์ ๊ท์ ํ ์ํคํํฐ
- ์๋ ๋ฐฉ์

![Untitled](./day03_data/Untitled%2010.png)
