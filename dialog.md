## 모달? \<dialog\> 요소가 답!

모달 대화 상자에 \<dialog\> 요소를 사용하면 개발 효율과 접근성 품질 문제를 한 번에 해결해 준다.

첫째, 내장되어 있는 ::backdrop 요소 사용 가능.<br>
둘째, 접근성 있는 키보드 문맥 형성.<br>
셋째, ESC 키 자동 맵핑.

키보드 문맥을 자세히 설명하면; 모달이 열렸을 때 모달 안으로 초점을 옮겨주고, 모달이 열려있는 동안 모달 안에 초점을 가두고, 모달을 닫을 때 모달 이전 요소로 초점을 돌려 놓는다.

[모달 \<dialog\> 예제 보기](dialog-example.html)

### 사용 예: HTML

```
<button>Just</button>
<a id="login-anchor" href="#login">Login</a>
<button>button</button>

<dialog id="login-dialog">
    <h2>Login</h2>
    <fieldset>
        <input type="text" aria-label="ID">
        <input type="password" aria-label="Password">
        <button>Login</button>
    </fieldset>
    <button id="close-btn">Close</button>
</dialog>
```

### 사용 예: CSS
```
#login-dialog::backdrop {
    background: rgb(0 0 0 / 32%);
}
```

### 사용 예: JavaScript
```
const anchorEl = document.querySelector('#login-anchor');
const dialogEl = document.querySelector('#login-dialog');
const closeEl = document.querySelector('#close-btn');

anchorEl.addEventListener('click', () => {
  dialogEl.showModal();
});

closeEl.addEventListener('click', () => {
  dialogEl.close();
});
```

### 참고
* [The dialog element](https://html.spec.whatwg.org/multipage/interactive-elements.html#the-dialog-element)
* [\<dialog\>: 대화 상자 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/dialog)
* [HTMLDialogElement: showModal() method](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/showModal)
* [HTMLDialogElement: close() method](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/close)
