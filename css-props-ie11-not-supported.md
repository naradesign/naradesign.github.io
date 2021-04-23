## IE11을 버리면 사용할 수 있는 CSS 명세.

### background-clip

`background-clip` 속성은 배경 영역을 설정한다.

```
background-clip: border-box;
background-clip: padding-box;
background-clip: content-box;
background-clip: text; // ⚠️-webkit-background-clip: text; 필요(2021-04).
```

`border-box`, `padding-box`, `content-box`, `⚠️text` 중 하나의 값을 설정할 수 있다. 초기값은 `border-box`이다. `text` 값은 실험중이기 때문에 속성 이름에 `-webkit-` 접두어를 붙여야 한다.

[caniuse](https://caniuse.com/background-clip-text) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/background-clip)



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

[caniuse](https://caniuse.com/calc) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/calc())



### ch

현재 글꼴에서 문자 '0'의 폭을 나타내는 단위로 주로 고정폭 글꼴에서 사용.

```
width: 80ch;
```

[caniuse](https://caniuse.com/ch-unit) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/length)



### all, initial, unset, revert

`all` 속성은 모든 CSS 속성을 재설정하기 위한 단축 속성이다.

```
all: initial; // 모든 속성을 initial 값으로 재설정.
all: inherit; // 상속 가능한 모든 속성을 inherit.
all: unset; // 상속 속성은 inherit, 비상속 속성은 initial.
all: revert; // unset과 같지만 ua 스타일이 있으면 따른다.
```

[caniuse](https://caniuse.com/css-all) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/all)



### :any-link

`:any-link` 가상 클래스 선택자는 하이퍼링크 자원을 연결하는 역할을 하는 요소를 선택한다. 결과적으로 `[href]` 속성 선택자와 같다.

```
:any-link { color: red; }

<a href="https://ex.com/"> // :any-link 선택
<a href="#"> // :any-link 선택
<a> // :any-link 선택 안 함
```

[caniuse](https://caniuse.com/css-any-link) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)



### appearance ⚠️

주로 폼 콘트롤 요소의 기본 스타일을 제어하는 속성. 값을 `none`으로 설정하면 UA 스타일을 사용자 정의 스타일로 덮어 쓸 수 있다.

```
-webkit-appearance: none; // ⚠️실험중(2021-04)
appearance: none;
```

`none` 외에도 다양한 값이 있다. 자세한 내용은 w3c 명세 참고.

[caniuse](https://caniuse.com/css-appearance) | [w3c](https://www.w3.org/TR/css-ui-4/#styling-widgets)



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

[caniuse](https://caniuse.com/css-backgroundblendmode) | [w3c](https://www.w3.org/TR/compositing-1/#propdef-background-blend-mode)



### box-decoration-break ⚠️

줄바꿈, 컬럼 나누기 등으로 박스가 분리되었을 때 절단된 가장자리를 처리하는 방식을 결정한다.

```
-webkit-box-decoration-break: slice; // ⚠️실험중(2021-04)
box-decoration-break: slice;

-webkit-box-decoration-break: clone; // ⚠️실험중(2021-04)
box-decoration-break: clone;
```

`background`, `border`, `box-shadow` 등의 속성에 영향을 준다. 초기값은 `slice`이다.

[caniuse](https://caniuse.com/css-boxdecorationbreak) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break)



### caret-color

텍스트 입력이 가능한 곳에 표시하는 입력 커서의 색상을 설정할 수 있다.

```
caret-color: red;
```

초기값은 `auto`이며 보통 검은색이다. 대비를 보장하기 위해 다른 색을 표시할 수 있다.


[caniuse](https://caniuse.com/css-caret-color) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)



### case-insensitive attribute selector

속성 선택자를 기술할 때 대괄호 `]` 종료 전 `i`를 포함하면 속성 값의 대소문자를 구별하지 않고 선택할 수 있다.

```
[data-case='a' i] // 아래 두 요소를 모두 선택한다.

<p data-case="a">
<p data-case="A">
```

`i` 대신 `s` 문자를 사용하면 대소문자를 구별해서 선택할 수 있다. 그러나 CSS 속성 선택자에서 속성 값은 기본적으로 대소문자를 구별하기 때문에 `s` 구문을 사용하는 경우는 드물다.

[caniuse](https://caniuse.com/css-case-insensitive) | [w3c](https://www.w3.org/TR/selectors-4/#attribute-case)



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

[demo](https://lab.iamvdo.me/css-svg-masks/) | [caniuse](https://caniuse.com/css-clip-path) | [w3c](https://www.w3.org/TR/css-masking-1/#propdef-clip-path)



### conic-gradient()

`conic-gradient()` 함수는 원뿔형 색상 그라데이션을 생성할 수 있다.

```
background-image: conic-gradient(black, white); // 중심 축 우회전
background-image: conic-gradient(from 45deg, black, white); // 시작 각
background-image: conic-gradient(at 25% 75%, black, white); // 회전 축
background-image: conic-gradient(from 45deg at 25% 75%, black, white); // from at 순서 필수
```

[caniuse](https://caniuse.com/css-conic-gradients) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient())



### :default

`:default` 기본 옵션 가상 클래스 선택자는 `checked` 속성을 가진 체크박스 또는 라디오 버튼을 선택한다. 또는 `form` 요소에서 `submit` 타입을 가진 첫 번째 버튼을 선택한다. 초기값을 사용자에게 인지시켜야 하는 맥락에서 유용하다. 예를 들면 초기값을 권장값으로 두거나 반드시 선택해야 하는 경우.

```
:default + label { ... } // == [checked] + label
button:default { ... } // == form button[type='submit']
```

사용자의 선택은 이 선택자의 선택 결과에 영향을 주지 않는다. 오직 HTML에 속성으로 명시한 `checked` 속성 또는 `submit` 타입을 선택한다.

[caniuse](https://caniuse.com/css-default-pseudo) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/:default)



### env()

UA가 정의하는 환경 변수(`safe-area-inset-*`) 인자를 CSS 코드에 전달하는 함수. 사용자 속성(`--*`)을 인자로 취하는 `var()` 함수와 용법이 비슷하다.

```
/* 이 코드는 iPhone X 이상 사파리 브라우저에서 .fixed 요소가 단말기 하단 UA 인터페이스와 겹치지 않도록 배치한다. */

.fixed {
    position: fixed;
    bottom: env(safe-area-inset-bottom);
    background: coral;
}
```

CSS 값을 사용할 수 있는 다양한 위치(예를 들면 `@` 규칙 또는 `calc()` 함수 인자)에서 사용할 수 있다. `env()` 인자 작성 위치에 쉼표(`,`)를 사용하면 폴백으로 사용할 수 있는 값을 추가할 수 있다.

[demo](https://naradesign.github.io/css/env-function.html) | [caniuse](https://caniuse.com/css-env-function) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/env())



### @supports

`@supports` 규칙은 기능 쿼리(feature queries)라고 부른다. CSS 속성과 값 지원 여부를 소괄호`()` 안에서 테스트하고 그 결과를 이용하여 중괄호`{}` 코드 블록의 적용 여부를 결정한다.

```
@supports (display: grid) {
    .column { display: grid; }
}
@supports not (display: grid) {
    .column { display: flex; }
}

@supports (*) and (*) or (*) {*} // 🚫
@supports (*) and ((*) or (*)) {*} // 👍

@supports (*) and not (*) {*} // 🚫
@supports (*) and (not (*)) {*} // 👍
```

미디어 쿼리 등 다른 규칙의 하위 규칙으로 사용할 수 있다. `and`, `or`, `not` 연산자를 사용할 수 있다. 종류가 다른 연산자를 함께 사용하는 경우 소괄호`()`로 우선 순위를 정의해야 한다.

[caniuse](https://caniuse.com/css-featurequeries) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/@supports)



### filter

필터 효과를 재현할 수 있다.

```
filter: blur(4px);
filter: grayscale(100%);
filter: brightness(50%);
```

취할 수 있는 값으로 `grayscale`, `sepia`, `saturate`, `hue-rotate`, `invert`, `opacity`, `brightness`, `contrast`, `blur`, `drop-shadow` 가 있다.

[caniuse](https://caniuse.com/css-filters) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/filter) | [w3c](https://www.w3.org/TR/filter-effects-1/#typedef-filter-function)



### :focus-within

자신이 직접 초점을 받았거나 초점 받은 요소를 포함하고 있을 때 선택한다.

```
fieldset:focus-within { background: silver; }
```

예제는 `fieldset` 요소 내부에 초점 받은 요소가 있는 경우 선택한다.

[caniuse](https://caniuse.com/css-focus-within) | [mdn](https://developer.mozilla.org/ko/docs/Web/CSS/:focus-within)



### font-display

웹 폰트를 완전히 로딩하기 전 글꼴을 어떻게 표시할지 결정한다. `@font-face` 규칙에 사용할 수 있다. 보통 대체 글꼴 표시 후 로딩한 글꼴로 바꿔 표시하는 `swap` 값을 권장한다.

```
@font-face {
    src: ...;
    font-family: ...;
    font-display: swap;
    ...
}
```

초기값은 `auto`로 UA가 결정하지만 대부분 `block`처럼 동작한다. `block`은 3초 동안 글꼴을 표시하지 않다가, 이후 대체 글꼴을 표시하고, 로딩 완료 후 웹 폰트를 표시한다. 3초 동안 FOIT(Flash Of Invisible Text) 현상을 유발하기 때문에 보통의 상황에서 권장하지 않는다. `swap`값은 먼저 대체 글꼴 표시 후, 로딩이 끝나면 웹 폰트를 표시한다. FOUT(Flash Of Unstyled Text) 방식이라고 부른다. `fallback`값은 먼저 대체 글꼴 표시 후, 웹 폰트 로딩이 3초(UA 권장) 안에 끝나면 웹 폰트를 로딩하고, 그렇지 않으면 영원히 대체 글꼴을 표기한다. `optional`값은 대체 글꼴 표시 후, 사용자의 회선 상태에 따라 웹 폰트 표시 여부를 웹 브라우저가 결정한다.

[caniuse](https://caniuse.com/css-font-rendering-controls) | [w3c](https://www.w3.org/TR/css-fonts-4/#font-display-desc)



### grid layout

격자를 이용하여 내용의 크기와 위치를 제어하고 배치하는 방법이다. `flex`가 하나의 축을 중심으로 내용을 배치하는데 반해 `grid`는 두 개의 축을 이용하여 내용을 배치한다. 특히 셀 병합과 같은 기능을 제공한다. 다른 수단에 비해 짧은 코드로 다양한 배치를 구현할 수 있다.

```
display: grid;
grid: auto / auto 1fr 25% 100px;
```

container, item, track, row, column, line, gutter, cell, area 개념을 사용한다. `grid` 키워드는 `display` 속성의 값이기도 하고 그리드 컨테이어에 적용하는 다양한 `grid-*-*` 속성의 단축 속성 이름이기도 하다.

[caniuse](https://caniuse.com/css-grid) | [w3c](https://www.w3.org/TR/css-grid-1/)



### image-set()
해상력과 이미지 타입으로 CSS 배경 이미지를 분기할 수 있다.

```
background-image: url('fallback.png');

/* Supports retina image */
background-image: image-set(
    'super.png' 2x,
    'normal.png' 1x
);

/* Supports avif format */
background-image: image-set(
    'super.avif' type('image/avif'),
    'normal.jpg' type('image/jpeg')
);
```

제조사 접두어를 붙여야 한다. `-webkit-image-set()` ⚠️실험중(2021-04)

[caniuse](https://caniuse.com/css-image-set) | [test](https://cloudfour.com/examples/image-set/)



### :in-range, :out-of-range

`input` 요소의 값을 `min`, `max` 속성으로 제한했을 때 `value` 값이 범위에 포함되는지 여부에 따라 선택한다. 값이 비어있는 경우에는 선택하지 않는다.

```
<label for="age">Age:</label>
<input id="age" type="number" min="1" max="99" placeholder="1~99">

#age:in-range { color: blue; }
#age:out-of-range { color: red; }
```

적절한 값을 입력했는지 시각적 단서를 제공하는 데 그쳐야 한다. 예를 들어 다음과 같이 가상 요소 선택자를 통해 메시지를 제공하는 코드는 보조 기기가 해석하지 않으므로 접근성이 없다.

```
<label for="age">DO NOT THIS:</label>
<input id="age" ... min ... max>
<p>Your value is </p>

#age:in-range + p::after { content: 'valid scope!'; } // 🚫
#age:out-of-range + p::after { content: 'out of scope!'; } // 🚫
```

[caniuse](https://caniuse.com/css-in-out-of-range) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)



### :indeterminate

상태가 정해지지 않은 폼 콘트롤 요소를 선택한다. `input` 요소 중 `checkbox` 타입, `radio` 타입, `progress` 요소의 미정(indeterminate) 상태를 선택할 수 있다.

```
input:indeterminate { ... }
progress:indeterminate { ... }
```

`checkbox` 요소의 `checked` 상태가 `true`도 아니고 `false`도 아닐 때 선택. `radio` 그룹에서 어떤 요소도 `checked` 상태가 아닐 때 선택. `progress` 요소에 `value` 값을 지정하지 않았을 때 선택.

[caniuse](https://caniuse.com/css-indeterminate-pseudo) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate) | [test](https://codepen.io/naradesign/pen/jOyLoEW?editors=1100)



### line-clamp

텍스트 콘텐츠가 박스를 넘치는 경우 설정한 위치에서 말줄임 기호를 표시할 수 있다.

```
display: -webkit-box;
-webkit-box-orient: vertical;
-webkit-line-clamp: 3; /* Ellipsis position */
overflow: hidden;
text-overflow: ellipsis;
max-height: calc(16px * 1.5 * 3); /* Max height of the box */
font-size: 16px;
line-height: 1.5;
```

w3c 초안에서는 `max-lines`, `block-ellipsis`, `continue`의 단축 속성으로 설명하고 있지만 브라우저에서 아직 구현 전.(2021-04)

[caniuse](https://caniuse.com/css-line-clamp) | [w3c](https://drafts.csswg.org/css-overflow-3/#fragmentation)



### min(), max(), clamp()

비교 함수라고 부른다. 계산식으로 구성한 여러 인자 중 하나의 값을 반환한다. `min()` 함수는 작은 값을 반환하고 `max()` 함수는 가장 큰 값을 반환한다. `clamp()` 함수는 '최젓값, 선호값, 최댓값' 이렇게 3개의 인자로 구성한다.

```
width: min(240px, 48%); // 가장 작은 평가값 반환
width: max(240px, 48%, 72vw); // 가장 큰 평가값 반환
width: clamp(240px, 48%, 24vw * 3); // 최젓값 ~ 최댓값 사이의 선호값 반환
```

`calc()` 함수의 모든 인자 형식은 비교 함수에서도 사용할 수 있다. 선호값은 최젓값과 최댓값 사이를 벗어나지 않는다.

[caniuse](https://caniuse.com/css-math-functions) | [w3c](https://drafts.csswg.org/css-values-4/#comp-func)



### interaction media features

상호작용 미디어 피처를 통해 포인팅 장치의 유무와 정확도 그리고 호버 가능 여부를 판단할 수 있다. 이 기능을 사용할 때 포인팅 장치를 사용할 수 없는 사용자를 차별하지 않도록 주의해야 한다.

```
@media (pointer: fine) {
    /* 정밀한 포인팅 장치에 대응(마우스, 터치 패드, 스타일러스 펜) */
}
@media (pointer: coarse) { // coarse[kɔːrs] == '거친, 굵은'
    /* 정밀하지 않은 포인팅 장치에 대응(스마트폰, 터치 스크린, 닌텐도) */
}
@media (pointer: none) {
    /* 포인팅 불능 장치에 대응(방향 키패드) */
}
@media (hover: none) {
    /* hover 불능 장치에 대응(방향 키패드) */
}
@media (hover) { // (hover: hover)의 약식 표기
    /* hover 장치에 대응(마우스, 터치 패드, 스타일러스 펜, 닌텐도) */
}
```

`any-pointer`, `any-hover` 인자는 참으로 판단할 수 있는 상황을 더 확장하는 방향으로 작용하기 때문에 더욱 주의해서 사용해야 한다. 예1) 데스크톱/노트북이 터치 스크린을 지원할 때 `pointer: coarse`은 `false`로 평가하지만 `any-pointer: coarse` 인자는 `true`로 평가한다. 예2) 터치 스크린 장치(예: 태블릿)에 마우스를 연결한 경우 `pointer: fine` 인자는 `false`로 평가하지만 `any-pointer: fine` 인자는 `true`로 평가한다. 예3) 터치 스크린 장치(예: 태블릿)에 마우스를 연결한 경우 `hover` 인자는 `false`로 평가하지만 `any-hover: hover` 인자는 `true`로 평가한다.

[caniuse](https://caniuse.com/css-media-interaction) | [w3c](https://www.w3.org/TR/mediaqueries-4/#mf-interaction)



### ::placeholder

자리 표시자 텍스트를 스타일링할 수 있다.

```
::placeholder {
    font-size: 16px;
    color: #767676; /* Contrast ratio required */
}
```

자리 표시자는 입력하는 순간 시야에서 사라지기 때문에 접근성 문제가 있다. 가능하다면 항상 힌트를 제공하는 방식을 추천한다. [닐슨 노먼 그룹의 자리 표시자 관련 기사](https://www.nngroup.com/articles/form-design-placeholders/)를 참고하길 바란다.

[caniuse](https://caniuse.com/css-placeholder) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)



### :placeholder-shown

자리 표시자 화면 표시 상태를 선택한다. 사용자가 값을 입력하기 시작하면 자리 표시자가 사라지면서 선택을 해제한다. `:not()` 선택자를 이용하면 자리 표시자 비활성 상태를 선택하는 것도 가능하다.

```
:placeholder-shown {
    /* 자리 표시자 활성 스타일 */
}
[placeholder]:not(:placeholder-shown) {
    /* 자리 표시자 비활성 스타일 */
}
```

[caniuse](https://caniuse.com/css-placeholder-shown) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown)



### :read-only, :read-write

'읽기 전용, 읽고 쓰기' 요소를 선택할 수 있다. 선택하는 요소가 폼 콘트롤로 제한되어 있지 않다. 폼 콘트롤 아닌 대부분의 읽기 전용 요소는 `:read-only`로 선택된다. `input`, `textarea` 뿐만 아니라 `contenteditable` 속성이 있으면 `:read-write` 선택자로 선택한다. `p`, `select` 요소는 `:read-only`와 일치한다.

[caniuse](https://caniuse.com/css-read-only-write) | [w3c(https://html.spec.whatwg.org/multipage/semantics-other.html#selector-read-only)



### #rrggbbaa, #rgba

red, green, blue, alpha 색상을 16진수 방식으로 표기할 수 있다. 각 색상 채널은 `00` ~ `ff` 까지 256 단계로 표현할 수 있다. alpha 채널은 `00`일 때 투명하고 `ff`일 때 불투명하다.

```
/* 알파값이 '00'이므로 완전 투명 */
background: rgba(0,0,0,0);
background: #00000000;
background: #0000;

/* 알파값이 '80'이므로 50% 투명 */
background: rgba(0,0,0,.5);
background: #00000080;

/* 알파값이 'ff'이므로 완전 불투명 */
background: rgba(255,255,255,1);
background: rgb(255,255,255);
background: #ffffffff;
background: #ffff;
background: #fff;
```

[caniuse](https://caniuse.com/css-rrggbbaa) | [w3c](https://drafts.csswg.org/css-color/#hex-notation)



### shape-outside, shape-margin, shape-image-threshold

`float` 스타일을 확장하는 속성이다. `float` 요소 주변의 인라인 텍스트가 흐르는 형태를 정의한다. `shape-outside` 속성은 [\<basic-shape\>](https://www.w3.org/TR/css-shapes/#typedef-basic-shape) 형태 함수를 지원한다. `url()` 값을 사용하면 이미지 알파 채널 기반으로 인라인 텍스트가 흐르도록 만드는 것도 가능하다.

```
/* <basic-shape> 기반 */
shape-outside: circle(120px at 0 -8px);
shape-margin: 16px;

/* 이미지 알파 채널 기반 */
shape-outside: url(...);
shape-margin: 16px;
shape-image-threshold: 0;
```

외부 이미지 자원은 이미지를 제공하는 서버측 CORS 설정에 따라 표시 여부가 결정된다. 외부 이미지 자원의 CORS가 허용되지 않으면 `shape-outside` 속성은 무시된다.

[caniuse](https://caniuse.com/css-shapes) | [w3c](https://www.w3.org/TR/css-shapes/) | [test](https://codepen.io/naradesign/pen/ZELaqVK?editors=1100)


### scroll-snap-type, scroll-snap-align

설정한 축(`x`, `y`, `both`...)으로 스크롤할 때 자손 아이템이 스크롤 컨테이너에 들러붙는 성질(`proximity`, `mandatory`)을 제어할 수 있다.

```
html {
  scroll-snap-type: y proximity;
}
h1, h2, h3, h4, h5, h6 {
  scroll-snap-align: start;
}
```

`scroll-snap-type`의 값은 `none | [x|y|block|inline|both] [mandatory|proximity]?` 형식으로 표현할 수 있다. `scroll-snap-align`의 값은 `[none|start|end|center]{1,2}` 형식으로 표현할 수 있다.

`scroll-margin`, `scroll-padding` 속성으로 스냅 위치를 정밀하게 제어할 수 있다.

[caniuse](https://caniuse.com/css-snappoints) | [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Scroll_Snap/Basic_concepts) | [test](https://webkit.org/demos/scroll-snap/index.html)



### position: sticky
[caniuse](https://caniuse.com/css-sticky) | []()



### text-orientation
[caniuse](https://caniuse.com/css-text-orientation) | []()



### var(--value)
[caniuse](https://caniuse.com/css-variables) | []()



### tab-size
[caniuse](https://caniuse.com/css3-tabsize) | []()



### display: flow-root

플로팅(float) 박스는 일반적인 흐름에서 벗어나기 때문에 부모 박스는 플로팅 박스 높이만큼 늘어나지 않는다. `display: flow-root` 속성은 포함 콘텐츠를 일반적인 흐름 속에 배치한다. 플로팅 요소를 사용할 때 clearfix라고 부르는 다양한 hack을 사용하지 않아도 된다.

```
.container { display: flow-root; }
.float { float: left; }
```

[caniuse](https://caniuse.com/flow-root) | [test](https://codepen.io/naradesign/pen/ZELRWbR?editors=1100)



### font-family: system-ui
[caniuse](https://caniuse.com/font-family-system-ui) | []()



### font-kerning
[caniuse](https://caniuse.com/font-kerning) | []()



### font-variant-numeric
[caniuse](https://caniuse.com/font-variant-numeric) | []()



### justify-content: space-evenly
[caniuse](https://caniuse.com/justify-content-space-evenly) | []()



### text-rendering
[caniuse](https://caniuse.com/kerning-pairs-ligatures) | []()



### object-fit, object-position
[caniuse](https://caniuse.com/object-fit) | []()



### prefers-color-scheme media feature
[caniuse](https://caniuse.com/prefers-color-scheme) | []()



### prefers-reduced-motion
[caniuse](https://caniuse.com/prefers-reduced-motion) | []()



### text-decoration-*
[caniuse](https://caniuse.com/text-decoration) | []()



### text-emphasis
[caniuse](https://caniuse.com/text-emphasis) | []()



### font-variation-settings
[caniuse](https://caniuse.com/variable-fonts) | []()



### will-change
[caniuse](https://caniuse.com/will-change) | []()




## 참고
* [caniuse.com](https://caniuse.com/?cats=CSS&statuses=all)
* [What To Expect When You're Expecting To Drop IE11](https://dev.to/samthor/what-to-expect-when-you-re-expecting-to-drop-ie11-ifg)
