## CSS grid 레이아웃.

CSS `flex`와 `grid`를 사용하지 않아도 상상할 수 있는 모든 레이아웃을 구현할 수 있다. 하지만 `flex`와 `grid`는 더 간결하면서도 강력하다. 아래 데모는 `grid` 모듈의 학습 동기를 유발하기 위한 코드 샘플이다.

* [`inline-block`, `float`, `flex`, `grid` 중 가장 간결한 코드는?](https://codepen.io/naradesign/pen/oNbqRqe)
* [`flex`에 없는 `grid`의 고유한 기능은?](https://codepen.io/naradesign/pen/QWyrEvj)
* [`grid`에 없는 `flex`의 고유한 기능은?](https://codepen.io/naradesign/pen/gOPKOXE)

`flex`와 `grid`는 컨테이너와 아이템 구조를 사용하는 점에서 같다. 그리고 설정한 방향으로 아이템을 배치한다는 점도 같다. 한편 `flex`는 레일(=) 위에 아이템을 배치하는 방식인데 `grid`는 격자(#) 위에 아이템을 배치하는 점이 다르다. `grid`는 진행 축이 아닌 방향으로 셀의 확장(병합)이 가능하다는 점도 `flex`와 다르다. `grid` 명세를 사용하면 레이아웃용 `<div>` 노드를 줄이는 데에도 도움이 된다.

아직 `flex`에 익숙하지 않다면 `flex`에 익숙해진 후 `grid`를 학습하길 권한다. `grid` 모듈은 조금 더 복잡하다.

### 속성 색인

격자 위에 아이템을 배치하는 속성이 다양하고 배치 알고리즘이 복잡해 보이는데 실상은 [3개의 단축 속성만으로도 꽤 난도가 높은 레이아웃을 구현할 수 있다](https://codepen.io/naradesign/pen/MWKBmaX?editors=1100). 격자 배치를 표현한 코드는 어떤 코드라도 판독성이 좋지 않다. `<table>`처럼 장황한 코드도 알아보기 어렵지만 `grid`처럼 함축적인 선언도 판독이 쉽지 않다. `grid` 구현할 때 사용하는 3개의 단축 속성은 `grid`, `grid-area`, `gap`인데 이것을 분해하면 18개의 속성으로 이뤄져 있다.

* [CSS 속성 값(value:) 정의 구문 해설](#css-%EC%86%8D%EC%84%B1-%EA%B0%92value-%EC%A0%95%EC%9D%98-%EA%B5%AC%EB%AC%B8-%ED%95%B4%EC%84%A4)
* [그리드 컨테이너 생성하기](#%EA%B7%B8%EB%A6%AC%EB%93%9C-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0)
* [gap](#gap) ⬅️ 격자 사이의 간격, 컨테이너에 적용.
  * [row-gap](#row-gap-column-gap)
  * [column-gap](#row-gap-column-gap)
* [grid](#grid) ⬅️ 트랙의 수와 크기, 컨테이너에 적용.
  * [grid-template](#grid-template)
    * [grid-template-rows](#grid-template-rows-grid-template-columns)
    * [grid-template-columns](#grid-template-rows-grid-template-columns)
    * ~~[grid-template-areas](#grid-template-areas)~~ // TODO:
  * ~~[grid-auto-flow](#grid-auto-flow)~~ // TODO:
  * ~~[grid-auto-rows](#grid-auto-rows)~~ // TODO:
  * ~~[grid-auto-columns](#grid-auto-columns)~~ // TODO:
* ~~[grid-area](#grid-area)~~ ⬅️ 아이템의 배치와 병합, 아이템에 적용. // TODO:
  * ~~[grid-row](#grid-row)~~ // TODO:
    * ~~[grid-row-start](#grid-row-start)~~ // TODO:
    * ~~[grid-row-end](#grid-row-end)~~ // TODO:
  * ~~[grid-column](#grid-column)~~ // TODO:
    * ~~[grid-column-start](#grid-column-start)~~ // TODO:
    * ~~[grid-column-end](#grid-column-end)~~ // TODO:

### CSS 속성 값(value:) 정의 구문 해설

CSS Grid 모듈의 명세를 정확하게 이해하려면 구성요소 값 결합 기호(Component Value Combinators)와 구성요소 값 곱수 기호(Component Value Multipliers)를 판독할 수 있어야 한다. 아래 예제는 `gap` 속성의 값을 기술하는 명세다. 간결하지만 많은 정보를 포함한다.

> Name: 'gap'<br>
> Value: <'row-gap'> <'column-gap'>?

이 명세는 다음과 같이 해석할 수 있다.

> `gap` 속성의 값은 공백으로 분리한 하나 또는 둘의 값을 선언해야 한다. 첫 번째 값은 `row-gap` 속성의 값이고 두 번째 값은 `column-gap` 속성의 값이다. 첫 번째 값은 필수이고, 두 번째 값은 생략하거나 한 번 선언할 수 있다. 선언 순서를 바꿀 수 없다.

이 섹션은 주제에서 벗어난 내용이지만 CSS 명세를 읽는 동안 자주 참고할 내용이기 때문에 특별히 기술했다.

#### 구성요소 값 결합 기호(Component Value Combinators)

값 명세에서 값 형식을 둘 이상 나열한 경우 아래 결합 기호 의미에 따라 필수 값인지 또는 순서를 변경할 수 있는지 알 수 있다.

1. 공백(` `): 둘 이상의 값이 모두 필수. 순서 유지 필수.
2. 이중 앰퍼샌드(`&&`): 둘 이상의 값이 모두 필수. 순서 변경 가능.
3. 이중 바(`||`): 두 값 중 하나 이상 필수. 순서 변경 가능.
4. 단일 바(`|`): 두 값 중 하나만 선언 가능. ⬅️ 이 기호를 기준으로 구문을 쪼개보면 이해하기 쉽다.
5. 대괄호(`[]`): 그룹.

값 결합 기호는 우선순위가 있고 여러 결합 기호가 나타난 경우 우선순위에 따라 묶어서 해석해야 한다. 예를 들어 공백(` `)과 단일 바(`|`)가 함께 보이면 공백이 우선 순위가 높기 때문에 공백으로 분리한 값들을 묶어서 따로 해석한다. `a b | c d | e f` 형식의 정의 구문은 `[a b] | [c d] | [e f]` 형식과 같다.

```
// 아래 두 가지 값 정의 구문은 같다.(예시)
  a b   |   c ||   d &&   e f
[ a b ] | [ c || [ d && [ e f ]]]

// 정의 구문에 따르면 아래의 선언 형식은 모두 유효함.
a b
c
e f d
e f d c
```

#### 구성요소 값 곱수 기호(Component Value Multipliers)

값 명세에서 값 형식 뒤에 곱수 기호가 있으면 선언 횟수에 제한이 있다는 것을 의미한다.

* 애스터리스크(`*`): 횟수 제한 없음. 0, 1, 2 ... ∞ 모두 가능.
* 더하기(`+`): 1회 이상 필요.
* 물음표(`?`): 0회 또는 1회.
* 중괄호(`{A}`): 정확히 A회 필요.
* 중괄호(`{A, B}`): 최소 A회 필요, 최대 B회.
* 중괄호(`{A,}`): B를 생략한 경우. 최소 A회 필요, 최댓값 무제한.
* 해시(`#`): 1회 이상 필요. 값을 콤마(,)로 분리. 횟수 제한 가능. 예) `<length>#{1, 4}`
* 대괄호 뒤 느낌표(`[]!`): 그룹에서 적어도 1회 이상 필요.

### 그리드 컨테이너 생성하기
`grid` 모듈을 사용하려면 가장 먼저 `grid` 컨테이너를 생성해야 한다. `grid` 컨테이너는 `display` 속성의 새로운 값 `grid | inline-grid` 으로 생성할 수 있다.

> * Name: '[display](https://www.w3.org/TR/css-ruby-1/#propdef-display)'
> * New Values: `grid` \| `inline-grid`

값이 `grid`인 경우 블럭 컨테이너를 생성하고 값이 `inline-grid`인 경우 인라인 컨테이너를 생성한다. 자식 요소는 자동으로 그리드 아이템이 된다. 그리드 컨테이너와 그리드 아이템에 선언하지 않은 모든 `grid-*` 속성은 초기값으로 설정된다. `grid` 속성으로 컨테이너의 트랙(행/열)의 수와 크기를 설정하고 `grid-area` 속성으로 아이템의 배치와 병합을 설정하기 전까지는 그리드 컨테이너를 생성한 것 만으로 특별한 효용이 없다.

<iframe height="360" style="width: 100%;" scrolling="no" title="Establishing Grid Containers." src="https://codepen.io/naradesign/embed/bGEjZXP?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/bGEjZXP'>Establishing Grid Containers.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### gap
`gap`은 `grid` 모듈을 통해 [~~`grid-gap`~~](https://www.w3.org/TR/css-align-3/#gap-legacy) 이라는 이름으로 탄생했지만 현재는 더 다양한 의도로 사용하기 위해 속성 이름을 `gap`으로 바꾸고 [CSS 박스 정렬 모듈(CSS Box Alignment Module Level 3)](https://www.w3.org/TR/css-align-3/#gap-shorthand)의 속성이 됐다. `gap`은 `grid` 전용 모듈이 아님에도 불구하고 `grid` 배치할 때 필수 속성으로 간주하기 때문에 여기서 설명한다.

> * Name: '[gap](https://www.w3.org/TR/css-align-3/#gap-shorthand)'
> * Value: [<'row-gap'>](https://www.w3.org/TR/css-align-3/#propdef-row-gap) [<'column-gap'>](https://www.w3.org/TR/css-align-3/#propdef-column-gap)?
> * Applies to: [multi-column containers](https://www.w3.org/TR/css-multicol-1/#multi-column-container), [flex containers](https://www.w3.org/TR/css-flexbox-1/#flex-container), [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)

`gap`은 `row-gap`과 `column-gap`의 단축 속성이다. 두 개의 값을 공백으로 분리하여 작성하는데 첫 번째 `row-gap` 값이 필수다. 두 번째 값을 생략하면 첫 번째 `row-gap`의 값을 `column-gap` 값으로 취한다.

<iframe height="360" style="width: 100%;" scrolling="no" title="CSS 'gap, row-gap, column-gap' properties." src="https://codepen.io/naradesign/embed/abdjEWY?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/abdjEWY'>CSS 'gap, row-gap, column-gap' properties.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### row-gap, column-gap

> * Name: '[row-gap](https://www.w3.org/TR/css-align-3/#propdef-row-gap)', '[column-gap](https://www.w3.org/TR/css-align-3/#propdef-column-gap)'
> * Value: `normal` \| [\<length-percentage\>](https://www.w3.org/TR/css-values-4/#typedef-length-percentage)
> * Applies to: [multi-column containers](https://www.w3.org/TR/css-multicol-1/#multi-column-container), [flex containers](https://www.w3.org/TR/css-flexbox-1/#flex-container), [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)

<iframe height="360" style="width: 100%;" scrolling="no" title="CSS 'row-gap, column-gap' properties." src="https://codepen.io/naradesign/embed/eYJjXQZ?height=355&theme-id=light&default-tab=result,css" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/eYJjXQZ'>CSS 'row-gap, column-gap' properties.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
<br>
<br>

`normal` 값은 `0`과 같다. 단, 다중 열 컨테이너(multi-column containers)에서는 `1em`으로 설정된다.

<iframe height="360" style="width: 100%;" scrolling="no" title="CSS muli-column comtainer's gap property normal value test." src="https://codepen.io/naradesign/embed/vYLaMoB?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/vYLaMoB'>CSS muli-column comtainer's gap property normal value test.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### grid

`grid`는 단축 속성으로 값 정의 구문이 다소 장황하다. 그러나 그리드 컨테이너에 선언할 수 있는 모든 속성을 `grid` 속성에 모아서 선언할 수 있다. `grid` 속성의 명세를 이해하려면 그리드 컨테이너를 제어하는 7개의 하위 속성(`grid-template-*`, `grid-auto-*`)을 모두 알고 있어야 한다. 그리드 컨테이너에 선언하는 속성들은 그리드 트랙(행/열)의 수와 크기에 관여한다. 단축 속성이기 때문에 명시하지 않고 생략한 하위 속성(`grid-*`)의 값들은 초기값으로 재설정된다.

> * Name: '[grid](https://www.w3.org/TR/css-grid-1/#propdef-grid)'
> * Value: [<‘grid-template’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-template) \| [<‘grid-template-rows’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-rows) / [ `auto-flow` && `dense`? ] [<‘grid-auto-columns’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-auto-columns)? \| [ `auto-flow` && `dense`? ] [<‘grid-auto-rows’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-auto-rows)? / [<‘grid-template-columns’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-columns)
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)

`grid` 속성 값 정의 구문을 분해해서 살펴보자. 공백(` `)으로 분리한 구문들은 하나의 그룹으로 묶고 단일 바(`|`)를 기준으로 분리해서 볼 수 있다. 결국 아래와 같이 3개의 선택 그룹(Option 1 `|` Option 2 `|` Option 3)으로 나뉜다. 단일바(`|`)의 의미에 따라 셋 중 하나의 구문을(하나만) 반드시 선언해야 한다.

```
<‘grid-template’> // ⬅️ Option 1
|
<‘grid-template-rows’> / [ auto-flow && dense? ] <‘grid-auto-columns’>? // ⬅️ Option 2
|
[ auto-flow && dense? ] <‘grid-auto-rows’>? / <‘grid-template-columns’> // ⬅️ Option 3
```

정의 구문에 등장하는 슬래시(`/`)는 주로 단축 속성에 나타나는데 자료형은 같지만 다른 속성의 값을 분리할 때 사용한다. `grid` 속성과 다른 하위 속성의 정의 구문에서 슬래시(`/`)는 보통 `행의 값` / `열의 값`을 분리하는 용도로 쓰인다. `[ auto-flow && dense? ]` 값 정의 구문을 묶은 이유는 이 그룹의 값이 이후에 등장하는 공백(` `)으로 분리한 다른 값보다 먼저 나타나야 하기 때문이다.

#### Option 1

```
<‘grid-template’> // ⬅️ Option 1
```

`<‘grid-template’>` 구문은 행/열 트랙의 수와 크기를 명시적으로 선언할 때 사용한다. [grid-template](#grid-template) 속성의 값을 선언할 수 있는데 [grid-template](#grid-template) 속성은 [grid-template-rows](#grid-template-rows-grid-template-columns), [grid-template-columns](##grid-template-rows-grid-template-columns), [grid-template-areas](#grid-template-areas) 속성의 단축 속성이다.

<iframe height="680" style="width: 100%;" scrolling="no" title="CSS grid shorthand property patterns." src="https://codepen.io/naradesign/embed/rNxqxyW?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/rNxqxyW'>CSS grid shorthand property patterns.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

#### Option 2, Option 3

```
<‘grid-template-rows’> / [ auto-flow && dense? ] <‘grid-auto-columns’>? // ⬅️ Option 2
|
[ auto-flow && dense? ] <‘grid-auto-rows’>? / <‘grid-template-columns’> // ⬅️ Option 3
```

Option 2\~3 구문은 한 축 트랙의 수와 크기를 명시적으로 선언하고 슬래시(`/`)로 분리한 다른 축 트랙은 트랙의 수 제한 없이 크기를 일괄 설정할 때 사용한다. [grid-template-rows](#grid-template-rows-grid-template-columns) 또는 [grid-template-columns](#grid-template-rows-grid-template-columns) 속성을 통해 한 축의 트랙 수와 크기를 명시적으로 선언한다. 슬래시(`/`)로 분리한 다른 축의 값(`auto-flow`)을 통해 [grid-auto-flow](#grid-auto-flow) 속성 값을 설정할 수 있고 [grid-auto-rows](#grid-auto-rows), [grid-auto-columns](#grid-auto-columns) 속성 값을 통해 선택한 트랙의 크기를 일괄 설정한다. `auto-flow` 값을 행의 위치에 선언하면 `grid-auto-flow: row` 속성이 설정되어 아이템이 행축(x)으로 흐르고 열의 위치에 선언하면 `grid-auto-flow: column` 속성이 설정되어 아이템이 열축(y)으로 흐르게 된다. `dense` 값을 함께 선언하면 아이템을 밀집 상태로 패킹한다.

<iframe height="560" style="width: 100%;" scrolling="no" title="CSS grid shorthand property patterns." src="https://codepen.io/naradesign/embed/LYGgMVy?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/LYGgMVy'>CSS grid shorthand property patterns.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
<br>
<br>

정리하면 `grid` 속성은 `grid-template-*`, `grid-auto-*` 속성의 단축 속성이다. 하위 속성의 명세를 알고 있어야 `grid` 단축 속성을 제대로 사용할 수 있다.

* [grid](#grid)
  * [grid-template](#grid-template)
    * [grid-template-rows](#grid-template-rows-grid-template-columns)
    * [grid-template-columns](#grid-template-rows-grid-template-columns)
    * [grid-template-areas](#grid-template-areas)
  * [grid-auto-flow](#grid-auto-flow)
  * [grid-auto-rows](#grid-auto-rows)
  * [grid-auto-columns](#grid-auto-columns)

### grid-template

`grid-template` 속성은 [grid-template-rows](#grid-template-rows-grid-template-columns),
[grid-template-columns](#grid-template-rows-grid-template-columns),
[grid-template-areas](#grid-template-areas) 속성의 단축 속성이다. 다시 말하면 `grid-template-*` 속성의 단축 속성이다. 그리드 트랙(행/열)의 수와 크기에 관여한다.

> * Name: '[grid-template](https://www.w3.org/TR/css-grid-1/#propdef-grid-template)'
> * Value: `none` \| [ [<‘grid-template-rows’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-rows) / [<‘grid-template-columns’>](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-columns) ] \| [ [\<line-names\>](https://www.w3.org/TR/css-grid-1/#typedef-line-names)? [\<string\>](https://www.w3.org/TR/css3-values/#string-value) [\<track-size\>](https://www.w3.org/TR/css-grid-1/#typedef-track-size)? [\<line-names\>](https://www.w3.org/TR/css-grid-1/#typedef-line-names)? ]+ [ / [\<explicit-track-list\>](https://www.w3.org/TR/css-grid-1/#typedef-explicit-track-list) ]?
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)

`grid-template` 속성의 모든 값은 `grid` 속성의 값으로도 사용할 수 있기 때문에 `grid-template` 속성을 사용하느니 차라리 `grid` 속성을 쓰는 걸 추천한다. 물론 `grid` 단축 속성을 사용하면 선언하지 않은 다른 값들(`grid-auto-*`)은 초기값으로 설정된다. `grid` 속성을 사용하려면 일단 `grid-template` 속성 값의 형식을 알아야 한다. 값 구문 정의를 분해해서 살펴보자.

```
none // ⬅️ Option 1
|
[ <‘grid-template-rows’> / <‘grid-template-columns’> ] // ⬅️ Option 2
|
[ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]? // ⬅️ Option 3
```

`grid-template` 속성의 값으로 Option 1\~3 중 하나의 형식을(하나만) 사용할 수 있다. `none`을 선언하면 `grid-template` 속성을 선언하지 않은 것과 같고 `grid-template-*` 속성의 모든 값을 초기값으로 설정한다. Option 2\~3 구문은 슬래시(`/`)를 기준으로 왼쪽은 행의 값, 오른쪽은 열의 값이다. Option 2는 `grid-template-rows/columns` 값을 선언하는 형식, Option 3는 `grid-template-areas` 값을 선언하는 형식으로 '셀 이름' 또는 '줄 이름'을 생성한다.

#### Option 1
```
none // ⬅️ Option 1

/* 이 값은 */
grid-template: none;

/* 아래와 같이 각 속성을 초기값으로 설정한다 */
grid-template-rows: none;
grid-template-columns: none;
grid-template-areas: none;
```

#### Option 2
```
[ <‘grid-template-rows’> / <‘grid-template-columns’> ] // ⬅️ Option 2

/* 이런 형식으로 표현할 수 있고 */
grid-template: 80px / 160px 1fr auto;
grid: 80px / 160px 1fr auto;

/* 아래와 같다 */
grid-template-rows: 80px;
grid-template-columns: 160px 1fr auto;
grid-template-areas: none;
```

<iframe height="320" style="width: 100%;" scrolling="no" title="CSS 'grid-template' property." src="https://codepen.io/naradesign/embed/WNrLdPW?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/WNrLdPW'>CSS 'grid-template' property.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

#### Option 3
```
[ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]? // ⬅️ Option 3
```

그리드 컨테이너에 셀 이름(cell names) 또는 줄 이름(line names)을 선언하고 그리드 아이템에서 참조할 때 사용하는 형식이다. 셀 이름을 선언하는 `<string>` 형식이 필수이며 이외의 값은 모두 생략 가능하다. 익명 셀(`'.'`)로 선언하는 것도 가능하지만 그럴바엔 차라리 셀 이름을 생략하는 Option 2 정의 구문을 사용하는 게 낫다.

`grid-template-areas` 속성을 표현하는 이 정의 구문은 특이하게 행과 열의 작성 형식이 다르다. 여기 선언한 '셀 이름(cell names)'과 '줄 이름(line names)'은 그리드 아이템에서 `grid-area` 속성으로 참조할 수 있다. 셀 이름은 `<string>` 위치에 반드시 선언해야 하고 슬래시(`/`) 왼쪽의 행 선언 위치에서만 나타날 수 있다.

셀 이름 `<string>` 정의 값에 숫자를 첫 번째 문자로 사용하면 이름을 참조할 수 없다. 그리드 아이템을 배치하고 병합할 때 셀 이름을 참조하는 코드가 가장 간결(예 `grid-area: a;`)하지만 그리드 컨테이너에 선언한 셀 이름에 의존하기 때문에 코드 관리가 어려울 수 있다.

'줄 번호' 또는 '셀 이름' 중 선호에 따라 한 가지 방식으로 아이템을 배치할 것을 추천한다. 그리드 아이템은 셀 이름이 없는 경우 '줄 번호'를 참조하여 배치하고 병합할 수 있다(예 `grid-area: 1 / 1 / 3 / 3;`). 줄 번호는 선언하지 않아도 자동으로 생성된다.

```
[ <string> <track-size>? ]+ [ / <explicit-track-list> ]? // ⬅️ Option 3(줄 이름을 제거한 형식)

/* -------- Applies to GRID CONTAINER -------- */
/* 셀 이름을 선언 */
grid-template: 'a a b' 80px 'a a c' auto 'd e f' / 160px 1fr auto;
/* == 다음과 같다 */
grid-template-rows: 80px auto auto;
grid-template-columns: 160px 1fr auto;
grid-template-areas: 'a a b' 'a a c' 'd e f';
/* == 다음과 같다 */
grid: 'a a b' 80px 'a a c' auto 'd e f' / 160px 1fr auto; 👍

/* -------- Applies to GRID ITEM -------- */
/* '셀 이름'을 참조(간결하다; 셀 이름에 의존한다) 👍 */
grid-area: a;

/* '줄 번호'를 참조(간결하다; 셀 이름에 의존하지 않는다) 👍 */
grid-area: 1 / 1 / 3 / 3;
grid-area: span 2 / span 2;
grid-area: 1 / 1 / span 2 / span 2;
```

<iframe height="360" style="width: 100%;" scrolling="no" title="CSS 'grid-template' property." src="https://codepen.io/naradesign/embed/BajvYxa?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/BajvYxa'>CSS 'grid-template' property.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
<br>
<br>

'줄 이름' `<line-names>?`을 선언하는 코드는 추천하지 않는다. 왜냐하면 '줄 번호' 또는 '셀 이름' 중 하나를 참조하는 것 만으로도 그리드 아이템의 배치와 병합에 제약이 없기 때문이다. '줄 이름'을 선언하고 참조할 수 있도록 명세에 포함한 것은 불필요했다고 생각한다.

줄 이름 `<line-names>?`은 대괄호(`[]`) 문자 안에 공백(` `)으로 분리한 하나 이상의 이름 값을 선언할 수 있다. 줄 이름은 생략 가능하다. 줄 이름은 대소문자를 구별하고 중복을 허용한다. 같은 줄 이름을 여러 번 선언한 경우; 예를 들어 `row` 또는 `col` 으로 정의한 줄 이름이 여러 개 있다면 그리드 아이템에서 `grid-area: row 1 / col 1 / row 3 / col 3;` 이렇게 암시적으로 생성된 번호를 조합하여 참조할 수도 있다. '줄 이름'을 선언하고 참조하는 방식은 '줄 번호' 또는 '셀 이름'을 참조하는 방식에 비해 코드량이 많고 판독성이 떨어지는 단점이 있다.

```
[ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]? // ⬅️ Option 3

/* -------- Applies to GRID CONTAINER -------- */
/* 셀 이름과 줄 이름을 함께 선언(복잡하다) 😱 */
grid-template:
  [row row-1-start] 'a a b' 80px [row-1-end]
  [row row-2-start] 'a a c' auto [row-2-end]
  [row row-3-start] 'd e f' [row-3-end row]
  /
  [col col-1-start] 160px [col col-1-end col-2-start] 1fr [col col-2-end col-3-start] 1fr [col-3-end col];
/* == 다음과 같다 */
grid-template-rows: [row row-1-start] 80px [row row-1-end row-2-start] auto [row row-2-end row-3-start] auto [row-3-end row];
grid-template-columns: [col col-1-start] 160px [col col-1-end col-2-start] 1fr [col col-2-end col-3-start] 1fr [col-3-end col];
grid-template-areas: 'a a b' 'a a c' 'd e f';

/* -------- Applies to GRID ITEM -------- */
/* '줄 이름'을 참조(추천하지 않는다) 😱 */
grid-area: row 1 / col 1 / row 3 / col 3;
grid-area: row 1 / col 1 / span 2 / span 2;
grid-area: row / col / row-2-end / col-2-end;
grid-area: row / col / span 2 / span 2;
```

### grid-template-rows, grid-template-columns

`grid-template-rows/columns` 속성은 트랙의 수와 크기를 그리드 컨테이너에 명시적으로 선언하는 그리드 레이아웃의 핵심 속성이다. 이 속성의 값 형식은 `grid`, `grid-template` 단축 속성에 사용할 수 있으며 이 속성을 독립적으로 사용하는 대신 `grid` 단축 속성을 사용하길 추천한다.

> * Name: '[grid-template-rows](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-rows)', '[grid-template-columns](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-columns)'
> * Value: `none` \| [\<track-list\>](https://www.w3.org/TR/css-grid-1/#typedef-track-list) \| [\<auto-track-list\>](https://www.w3.org/TR/css-grid-1/#typedef-auto-track-list)
> * Initial: `none`
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)

`grid-template-rows` 속성과 `grid-template-columns` 속성은 각각 행과 열을 제어한다는 특징만 빼면 값의 형식이 같다. 세 가지 형식의 값 `none` \| `<track-list>` \| `<auto-track-list>` 중 하나의 값 형식을(하나만) 선언할 수 있는데 초기값은 `none`이다.

#### \<track-list\>
트랙 목록`<track-list>`의 값 형식은 트랙의 크기`<track-size>`와 수`<track-repeat>`를 선언하는 형식으로 아래와 같이 분해할 수 있다. 줄 이름`<line-names>?`을 생략할 수 있다. 줄 이름 사용을 추천하지 않는다. 줄 이름을 사용하지 않는다면 트랙 목록의 값 정의 구문은 두 번째 줄과 같이 간결하게 다시 정리할 수 있다.

```
<track-list> = [ <line-names>? [ <track-size> | <track-repeat> ] ]+ <line-names>? 😰
⬇️
<track-list> = [ <track-size> | <track-repeat> ]+ 😃
```

단일 바를(`|`) 사용했으므로 두 값 형식 중 하나의 값이 필수이고 더하기(`+`) 곱수 기호를 사용했으므로 그룹(`[]`) 내부의 값은 1회 이상 반복해서 선언할 수 있다. `<track-repeat>` 형식은 `<track-size>`의 반복문인 `repeat()` 함수를 나타낸다. `repeat()` 함수의 첫 번째 인자는 반복 횟수이고 두 번째 인자는 트랙 목록으로 하나 이상의 크기(`px`, `%`, `fr`, `auto`...) 값을 공백으로 분리하여 나열할 수 있다. 실제 사용 형식은 다음과 같다.

```
grid-template-rows: 80px 120px;
grid-template-columns: repeat(2, 80px 1fr);
/* ⬇️ 간결하게 표현할 수 있다. */
grid: 80px 120px / repeat(2, 80px 1fr); 👏

/* 좌우가 같은 표현이다. */
repeat(2, auto) == auto auto
160px repeat(2, auto) == 160px auto auto
160px repeat(2, 80px 1fr) == 160px 80px 1fr 80px 1fr
```

<iframe height="360" style="width: 100%;" scrolling="no" title="CSS 'grid-template-rows/columns' property." src="https://codepen.io/naradesign/embed/yLeZprd?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/yLeZprd'>CSS 'grid-template-rows/columns' property.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
<br>
<br>

아래와 같이 줄 이름 `<line-names>?`을 선언할 수도 있다. 이렇게 선언한 줄 이름은 그리드 아이템에서 `grid-area` 속성의 값으로 참조하여 아이템의 배치와 셀 병합에 사용할 수 있다. 선언만 해 놓고 `grid-area`에서 참조하지 않으면 아무 소용이 없는 코드다. '줄 이름' 대신 '줄 번호'를 참조하거나 '셀 이름'을 선언해서 참조하는 것이 더 간결하다.

```
.container {
/* 이런 장황한 코드를 보고 싶지 않다 😱 */
  grid-template-rows: [row-start row-1-start] 80px [row-end row-1-end row-start row-2-start] 1fr [row-end row-2-end row-start row-3-start] auto [row-end row-3-end];
  grid-template-columns: [col-start col-1-start] 160px [col-end col-1-end col-start col-2-start] 1fr [col-end col-2-end col-start col-3-start] auto [col-end col-3-end];
/*
  줄 이름을 사용하지 않는다면 아래와 같이 간결하게 표현할 수 있다.
  grid: 80px 1fr auto / 160px 1fr auto; 👏
*/
}
```

#### \<auto-track-list\>

자동 트랙 목록`<auto-track-list>`은 트랙 수를 동적으로 결정한다는 점에서 트록 목록`<track-list>`과 다르다. 자동 트랙 목록 형식을 사용하면 미디어 쿼리 규칙에 의존하지 않으면서도 화면 크기에 따라 컬럼 수가 달라지는 레이아웃을 만들 수도 있다. 반응형 웹 구현 패턴 중 하나다. `<auto-track-list>`의 값 정의 구문에서 필수가 아닌 값 형식을 하나씩 제거해 보면 `<auto-repeat>` 구문 하나가 남는다. 고정된 크기의 트랙을 `auto-fill/fit` 알고리즘에 따라서 반복할 수 있다.

```
<auto-track-list> = [ <line-names>? [ <fixed-size> | <fixed-repeat> ] ]* <line-names>? <auto-repeat> [ <line-names>? [ <fixed-size> | <fixed-repeat> ] ]* <line-names>? 😰
⬇️
<auto-track-list> = [ <fixed-size> | <fixed-repeat> ]* <auto-repeat> [ <fixed-size> | <fixed-repeat> ]* 😂
⬇️
<auto-track-list> = <auto-repeat> 😃
⬇️
<auto-repeat> = repeat( [ auto-fill | auto-fit ] , <fixed-size> )

/* 자동 트랙의 값으로 유효한 선언들 */
grid-template-columns: repeat(auto-fill, 80px);
grid-template-columns: repeat(auto-fit, 20%);
grid-template-columns: repeat(auto-fill, minmax(auto, 80px)) 160px;
grid-template-columns: 160px repeat(auto-fit, minmax(80px, auto));
```

`<auto-repeat>` 즉 여기서 `repeat()` 함수는 `repeat(반복 알고리즘, 트랙 크기)` 형식이다. `repeat()` 함수의 첫 번째 인자 중 `auto-fill/fit` 구문은 직역하면 '자동 채우기', '자동 맞추기'인데 컨테이너의 크기와 주어진 트랙 크기 조건에 따라서 트랙 수를 자동으로 결정한다.

트랙 수를 자동으로 결정하려면 최소한 트랙의 크기 또는 트랙의 크기의 범위(`minmax()`)는 지정해 주어야 한다. 트랙 수와 트랙의 크기를 모두 결정하지 않은 상태로 두면 격자를 렌더링할 수 있는 조건이 성립하지 않는다. 결국 `auto-fill/fit` 값은 자동 크기 값(`auto`, `fr`)과는 결합할 수 없다. `auto-fill/fit` 구문은 `minmax()` 함수와 함께 트랙의 '최소, 최대' 크기를 고정해서 결합하는 형식이 일반적이다. `auto-fill/fit` 구문을 사용하지 않으면 트랙의 수는 항상 고정이다.

`auto-fill/fit` 구문은 반복 트랙의 최대 크기를 자동(`auto`)으로 처리할 때 차이를 보인다. `auto-fill`은 트랙의 크기를 줄여서 가능한 많은 수의 트랙을 생성하는 방향으로, `auto-fit`은 트랙의 크기를 늘려서 가능한 적은 수의 트랙을 생성하는 방향으로 처리한다.

```
/* 유효한 결합 형식 */
repeat(auto-fill, 80px);
repeat(auto-fill, minmax(auto, 80px));
repeat(auto-fit, 20%);
repeat(auto-fit, minmax(20%, auto));
80px repeat(auto-fill, 20%);
20% repeat(auto-fit, 80px);

/* 허용하지 않는 결합 ❌ */
repeat(auto-fill, auto); /* auto ❌ */
repeat(auto-fill, 1fr); /* 1fr ❌ */
repeat(auto-fit, ... auto); /* auto ❌ */
repeat(auto-fit, ... 1fr); /* 1fr ❌ */
auto repeat(auto-fill, ...); /* auto ❌ */
1fr repeat(auto-fit, ...); /* 1fr ❌ */
```

<iframe height="440" style="width: 100%;" scrolling="no" title="CSS repeat(), auto-fill, auto-fit." src="https://codepen.io/naradesign/embed/oNbmQar?height=265&theme-id=light&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/naradesign/pen/oNbmQar'>CSS repeat(), auto-fill, auto-fit.</a> by Jeong Chan-Myeong
  (<a href='https://codepen.io/naradesign'>@naradesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### grid-template-areas

> * Name: '[grid-template-areas](https://www.w3.org/TR/css-grid-1/#propdef-grid-template-areas)'
> * Value:
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)


### grid-auto-rows

> * Name: '[grid-auto-rows](https://www.w3.org/TR/css-grid-1/#propdef-grid-auto-rows)'
> * Value:
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)


### grid-auto-columns

> * Name: '[grid-auto-columns](https://www.w3.org/TR/css-grid-1/#propdef-grid-auto-columns)'
> * Value:
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)


### grid-auto-flow

> * Name: '[grid-auto-flow](https://www.w3.org/TR/css-grid-1/#propdef-grid-auto-flow)'
> * Value:
> * Applies to: [grid containers](https://www.w3.org/TR/css-grid-1/#grid-container)


### grid-area

> * Name: '[grid-area](https://www.w3.org/TR/css-grid-1/#propdef-grid-area)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)


### grid-row

> * Name: '[grid-row](https://www.w3.org/TR/css-grid-1/#propdef-grid-row)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)


### grid-row-start

> * Name: '[grid-row-start](https://www.w3.org/TR/css-grid-1/#propdef-grid-row-start)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)


### grid-row-end

> * Name: '[grid-row-end](https://www.w3.org/TR/css-grid-1/#propdef-grid-row-end)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)


### grid-column

> * Name: '[grid-column](https://www.w3.org/TR/css-grid-1/#propdef-grid-column)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)


### grid-column-start

> * Name: '[grid-column-start](https://www.w3.org/TR/css-grid-1/#propdef-grid-column-start)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)


### grid-column-end

> * Name: '[grid-column-end](https://www.w3.org/TR/css-grid-1/#propdef-grid-column-end)'
> * Value:
> * Applies to: [grid items](https://www.w3.org/TR/css-grid-1/#grid-item)



### 참고
* [CSS Values and Units Module Level 3](https://www.w3.org/TR/css3-values/)
* [CSS Grid Layout Module Level 1](https://www.w3.org/TR/css-grid-1/)
* [CSS Box Alignment Module Level 3](https://www.w3.org/TR/css-align-3/#gap-shorthand)
* [MDN CSS 값 정의 구문](https://developer.mozilla.org/ko/docs/Web/CSS/Value_definition_syntax)
* [MDN CSS grid](https://developer.mozilla.org/ko/docs/Web/CSS/grid)
* [Learn CSS grid](https://learncssgrid.com/)
* [Grid by Example](https://gridbyexample.com/examples/)
* [GRID GARDEN](https://cssgridgarden.com/)
