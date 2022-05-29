# jsPlayGround
js의 여러기능을 구현을 통해 공부

# wysiwyg
wysiwyg 구현을 통해 에디터 관련 코드를 사용해보자.

## 1. `<태그 contenteditable="true"></태그>`
태그에 `contenteditable="true"`를 넣어주면 해당 태그를 수정할 수 있게 된다.

```html
<!-- index.html-->
<div class="editor" contenteditable="true">
    <h1>나만의 wysiwyg</h1>
    <p>heloooo</p>
</div>
```

## 2. `<태그 data-이름 = 값 ></태그>`

`data-데이터이름 = 값`을 지정해 주면 해당 태그의 데이터를 js에서 가져올 수 있다. 

```html
<!-- index.html-->
<li>
    <button type="button" data-command="h1">H1</button>
</li>
```
```js
//index.html
const command = item.dataset.command;
if(command === 'h1'){...}
```

## 3. `document.execCommand();`

```js
//index.html

if(...){
    document.execCommand('formatBlock', false, command);
}else{
    document.execCommand(command);
}    
```

## 4. `window.getSelection();`
```js
//hell.html
const selectedTxt = window.getSelection();
```

## 5. `Selection개체.anchorNode();`
```js
//hell.html
const parentEl = selectedTxt.anchorNode.parentElement;
```


## 6. `Selection개체.replaceChild();`
```js
//hell.html
editor.replaceChild(createdEl, parentEl)

```


## 7. `Selection개체.getRangeAt();`
```js
//hell.html
const selectedTxtRange = selectedTxt.getRangeAt(0);
```


## 8. `Selection개체.surroundContents();`
```js
//hell.html
selectedTxtRange.surroundContents(createdEl)
```

