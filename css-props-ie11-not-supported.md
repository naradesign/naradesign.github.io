## IE11을 버리면 사용할 수 있는 CSS 명세.

### background-clip

`background-clip` 속성은 배경 영역을 설정한다.

```
background-clip: border-box;
background-clip: padding-box;
background-clip: content-box;
background-clip: text; // ⚠️-webkit-background-clip: text; 필요(2021-03).
```

`border-box`, `padding-box`, `content-box`, `⚠️text` 중 하나의 값을 설정할 수 있다. 초기값은 `border-box`이다. `text` 값은 실험중이기 때문에 속성 이름에 `-webkit-` 접두어를 붙여야 한다.

[caniuse - background-clip](https://caniuse.com/background-clip-text) | [MDN - background-clip](https://developer.mozilla.org/ko/docs/Web/CSS/background-clip)



### calc()

`calc()` 함수로 길이 단위에 계산식을 사용할 수 있다. 예를 들면 `width: calc(100% - 3em)`

```
width: calc(10px + 100px);
width: calc(100% - 30px);
width: calc(2em * 5); // 적어도 하나의 인자는 반드시 <number>.
width: calc(100% / 4); // 오른쪽 인자는 반드시 <number>.
width: calc(var(--variable-width) + 20px);
```

`+`, `-` 연산자는 좌우에 공백이 필수다. `*`, `/` 연산자는 좌우 공백이 필요하지 않지만 일관성을 위해 띄우는 편이 좋다.

[caniuse - calc()](https://caniuse.com/calc) | [MDN - calc()](https://developer.mozilla.org/ko/docs/Web/CSS/calc()).



### ch

현재 글꼴에서 문자 '0'의 폭을 나타내는 단위로 주로 고정폭 글꼴에서 사용.

```
width: 80ch;
```

[caniuse - ch](https://caniuse.com/ch-unit) | [MDN - \<length\>](https://developer.mozilla.org/ko/docs/Web/CSS/length)



### all

`all` 속성은 모든 CSS 속성을 재설정하기 위한 단축 속성이다.

```
all: initial; // 모든 속성을 initial 값으로 재설정.
all: inherit; // 상속 가능한 모든 속성을 inherit.
all: unset; // 상속 속성은 inherit, 비상속 속성은 initial.
all: revert; // unset과 같지만 ua 스타일이 있으면 따른다.
```

[caniuse - all](https://caniuse.com/css-all) | [MDN - all](https://developer.mozilla.org/ko/docs/Web/CSS/all)



### :any-link

`:any-link` 가상 클래스 선택자는 하이퍼링크 자원을 연결하는 역할을 하는 요소를 선택한다. 결과적으로 `[href]` 속성 선택자와 같다.

```
:any-link { color: red; }

<a href="https://ex.com/"> // :any-link 선택
<a href="#"> // :any-link 선택
<a> // :any-link 선택 안 함
```

[caniuse - :any-link](https://caniuse.com/css-any-link) | [MDN - :any-link](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)



### appearance ⚠️

주로 폼 콘트롤 요소의 기본 스타일을 제어하는 속성. 값을 `none`으로 설정하면 UA 스타일을 사용자 정의 스타일로 덮어 쓸 수 있다.

```
-webkit-appearance: none; // ⚠️실험중(2021-03)
appearance: none;
```

`none` 외에도 다양한 값이 있다. 자세한 내용은 w3c 명세 참고.

[caniuse - appearance](https://caniuse.com/css-appearance) | [w3c - appearance](https://www.w3.org/TR/css-ui-4/#styling-widgets)



### background-blend-mode

배경에 쌓은 '이미지, 그라디언트, 색'을 혼합할 수 있다.

```
background-image:
    linear-gradient(#f00, #f00), /* Red */
    linear-gradient(#0f0, #0f0), /* Green */
    linear-gradient(#00f, #00f); /* Blue */

background-blend-mode: normal; /* 초기 값; 혼합 X ➡️ Red */
background-blend-mode: multiply; /* 감산 혼합 ➡️ Black */
background-blend-mode: screen; /* 가산 혼합 ➡️ White */
```

다양한 [\<blend-mode\>](https://www.w3.org/TR/compositing-1/#ltblendmodegt) 값이 있다.

[caniuse - background-blend-mode](https://caniuse.com/css-backgroundblendmode) | [w3c - background-blend-mode](https://www.w3.org/TR/compositing-1/#propdef-background-blend-mode)



### box-decoration-break ⚠️

줄바꿈, 컬럼 나누기 등으로 박스가 분리되었을 때 절단된 가장자리를 처리하는 방식을 결정한다.

```
-webkit-box-decoration-break: slice; // ⚠️실험중(2021-03)
box-decoration-break: slice;

-webkit-box-decoration-break: clone; // ⚠️실험중(2021-03)
box-decoration-break: clone;
```

`background`, `border`, `box-shadow` 등의 속성에 영향을 준다. 초기값은 `slice`이다.

[caniuse - box-decoration-break](https://caniuse.com/css-boxdecorationbreak) | [MDN - box-decoration-break](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break)



### caret-color

텍스트 입력이 가능한 곳에 표시하는 입력 커서의 색상을 설정할 수 있다.

```
caret-color: red;
```

초기값은 `auto`이며 보통 검은색이다. 대비를 보장하기 위해 다른 색을 표시할 수 있다.


[caniuse - caret-color](https://caniuse.com/css-caret-color) | [MDN - caret-color](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)



### case-insensitive attribute selector

속성 선택자를 기술할 때 대괄호 `]` 종료 전 `i`를 포함하면 속성 값의 대소문자를 구별하지 않고 선택할 수 있다.

```
[data-case='a' i] // 아래 두 요소를 모두 선택한다.

<p data-case="a">
<p data-case="A">
```

`i` 대신 `s` 문자를 사용하면 대소문자를 구별해서 선택할 수 있다. 그러나 CSS 속성 선택자에서 속성 값은 기본적으로 대소문자를 구별하기 때문에 `s` 구문을 사용하는 경우는 드물다.

[caniuse - case-insensitive attribute selector](https://caniuse.com/css-case-insensitive) | [w3c - case-sensitive](https://www.w3.org/TR/selectors-4/#attribute-case)



### clip-path

`clip-path` 속성은 모양을 지정하여 표시 영역을 정의하는 속성이다. 다양한 도형으로 잘라낸 표현을 할 수 있다.

```
clip-path: none; // 초기값; 적용 X
clip-path: inset(25% 35%); // 사각형
clip-path: circle(48px at center); // 원형
clip-path: polygon(50% 20%, 30% 80%, 70% 80%); // 다각형
clip-path: url(#clipPath); // <svg> 요소의 <clipPath> 참조
```

⚠️ 사파리, 삼성 인터넷 브라우저는 속성 이름에 `-webkit-` 접두어를 표시해야 한다.

[Test clip-path](https://lab.iamvdo.me/css-svg-masks/) | [w3c - clip-path](https://www.w3.org/TR/css-masking-1/#propdef-clip-path)



### conic-gradient()

`conic-gradient()` 함수는 원뿔형 색상 그라데이션을 생성할 수 있다.

```
background-image: conic-gradient(black, white); // 중심 축 우회전
background-image: conic-gradient(from 45deg, black, white); // 시작 각
background-image: conic-gradient(at 25% 75%, black, white); // 회전 축
background-image: conic-gradient(from 45deg at 25% 75%, black, white); // from at 순서 필수
```

[caniuse - conic-gradient()](https://caniuse.com/css-conic-gradients) | [w3c - conic-gradient()](https://www.w3.org/TR/css-images-4/#conic-gradients)



### :default

`:default` 기본 옵션 가상 클래스 선택자는 `checked` 속성을 가진 체크박스 또는 라디오 버튼을 선택한다. 또는 `form` 요소에서 `submit` 타입을 가진 첫 번째 버튼을 선택한다. 초기값을 사용자에게 인지시켜야 하는 맥락에서 유용하다. 예를 들면 초기값을 권장값으로 두거나 반드시 선택해야 하는 경우.

```
:default + label { ... } // == [checked] + label
button:default { ... } // == form button[type='submit']
```

사용자의 선택은 이 선택자의 선택 결과에 영향을 주지 않는다. 오직 HTML에 속성으로 명시한 `checked` 속성 또는 `submit` 타입을 선택한다.

[caniuse - :default](https://caniuse.com/css-default-pseudo) | [w3c - :default](https://drafts.csswg.org/selectors-4/#the-default-pseudo)



### env()

UA가 정의하는 환경 변수(`safe-area-inset-*`)를 매개 변수로 취하는 함수다. 즉 UA 환경 변수 값을 CSS에서 사용할 수 있다. 사용자 속성(`--*`)을 매개 변수로 취하는 `var()` 함수와 용법이 비슷하다.

```
/* 이 코드는 body 요소를 안전한 영역에 배치한다 */
.container {
    background: blue;
    margin-top: env(safe-area-inset-top);
    margin-bottom: env(safe-area-inset-bottom);
}
```

CSS 값을 사용할 수 있는 다양한 위치에서(@ 규칙 포함) 사용할 수 있다. 매개 변수 작성 위치에 쉼표(`,`)를 사용하면 폴백 값을 추가할 수 있다.

[caniuse - env()](https://caniuse.com/css-env-function) | [MDN - env()](https://developer.mozilla.org/en-US/docs/Web/CSS/env())



### @supports

CSS 속성과 값 지원 여부를 테스트하는 조건 규칙이다.


[caniuse - @supports](https://caniuse.com/css-featurequeries) | []()



## 참고
* [caniuse.com](https://caniuse.com/?cats=CSS&statuses=all)
* [What To Expect When You're Expecting To Drop IE11](https://dev.to/samthor/what-to-expect-when-you-re-expecting-to-drop-ie11-ifg)
