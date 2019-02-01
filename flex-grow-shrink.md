## CSS flexible 레이아웃: flex item의 팽창과 수축.

오늘은 흔히 flex 또는 flexible 박스 모델이라고 부르는 <a href="https://www.w3.org/TR/css-flexbox-1/">CSS Flexsible box layout module level 1(Candidate Recommendation)</a> 명세를 설명해 보려고 합니다. 아직 표준 후보 단계이지만 <a href="http://caniuse.com/#search=flexible">현존하는 최신 브라우저에 flexible box layout module은 이미 구현</a>되어 있습니다.

기존에 우리가 사용하던 레이아웃 기법은 `displa`, `float`, `position` 으로써 컬럼 레이아웃을 표현하는데 한계가 있고 구현 방법이 복잡한 문제가 있었는데요. flexible(신축성 있는, 유연한) 박스 모델의 장점을 한 마디로 표현하면 "**복잡한 계산 없이 박스의 크기와 순서를 유연하게 배치할 수 있다.**" 라고 정리할 수 있습니다. 쉬운 예를 들면 컬럼의 한 쪽은 고정하고 다른 한 쪽을 가변폭으로 처리하고 싶을 때 유용하지만 그것 이상의 편의를 제공합니다. 어떤 속성과 값을 통해 무엇을 할 수 있는지 설명해 보겠습니다.

* <a href="#플렉스-컨테이너와-플렉스-아이템flex-container--flex-item의-개념">플렉스 컨테이너와 플렉스 아이템(flex container &amp; flex item)의 개념.</a>
  * <a href="#flex-container">flex container</a>
  * <a href="#flex-item">flex item</a>
* <a href="#신축성flexibility-flex-item의-팽창-및-수축">신축성(flexibility): flex item의 팽창 및 수축.</a>
  * <a href="#flex-item의-팽창을-제어하는-flex-grow-속성">flex item의 팽창을 제어하는 'flex-grow' 속성.</a>
  * <a href="#flex-item의-수축을-제어하는-flex-shrink-속성">flex item의 수축을 제어하는 'flex-shrink' 속성.</a>
  * <a href="#flex-item의-기준-사이즈를-제어하는-flex-basis-속성">flex item의 기준 사이즈를 제어하는 'flex-basis' 속성.</a>
  * <a href="#flex-item의-단축-속성-flex">flex item의 단축 속성 'flex'.</a>

### 플렉스 컨테이너와 플렉스 아이템(flex container &amp; flex item)의 개념.
flex 박스 모델은 `tr`/ `td` 개념와 유사합니다.  flex 박스는 **flex container**(부모, 마치 `tr`)와 **flex item**(자식, 마치 `td`)으로 이루어 집니다. **flex container** 요소에 `display` 속성의 값을 `flex` 또는 `inline-flex` 라고 선언하면 해당 요소는 flex container가 되고 자식 요소는 자동으로 flex item이 되어 flex 박스로 렌더링하기 시작합니다.

#### flex container
flex container는 flex item의 면적, 방향, 정렬을 결정하는 컨테이너 입니다. flex container 요소에 `display` 속성의 값으로 `inline-flex`를 선언하면 인라인 수준의 flex container를 생성하고, `flex` 값을 선언하면 블럭 수준의 flex container를 생성합니다. `inline-flex` 상태의 컨테이너는 `inline-block` 박스와 같은 형태로 표시합니다.

#### flex item
flex item은 컨테이너 내부에 형성된 free space(남거나 모자라는 공간, `margin`과 유사한 개념이지만 `margin`은 아님)를 팽창지수 또는 수축지수 값에 따라 형제들이 서로 나누어 갖습니다. flex container에 `inline-flex` 또는 `flex` 값을 선언하면 자식 요소들은 자동으로 **flex item**이 됩니다. flex item의 기본적인 스타일(User Agent 기본값)은 다음과 같습니다. 기본 스타일( `flex-grow:0; flex-shrink:1; flex-basis:auto; flex-direction:row; flex-wrap:nowrap;`)은 개발자가 변경할 수 있으며, 단축 속성( `flex`)을 사용할 때 값이 자동으로 재설정(<a href="#flex-item의-단축-속성-flex">flex item의 단축 속성 'flex'</a> 참고)되기도 합니다.

* 여분의 free space가 있어도 폭이 저절로 늘어나지 않습니다.( `flex-grow:0`)
* 부모 박스 초과 시(이 때 flex container 내부에 음수 free space 발생) 자동으로 균등 수축(음수 free space 크기 ÷ flex item 개수)합니다.( `flex-shrink:1`)
* 콘텐츠 너비만큼 수축합니다.( `flex-basis:auto`)
* 행으로 배치 합니다.( `flex-derection:row`)
* 개행하지 않습니다.( `flex-wrap:nowrap`)
* 텍스트 노드도 익명 flex item이 됩니다. 공백은 flex item이 되지 않습니다.

그 밖에 이런 특징도 있습니다.

* `float` 속성은 무시합니다.
* `position:absolute|fixed` 속성이 부여되면 flex item에서 빠지게 됩니다.
* flex item은 형제 또는 부모와 수직 또는 수평 `margin`을 중첩하지 않습니다.
* 브라우저마다 구현이 다를 수 있기 때문에 `margin`/ `padding`의 값으로 상대 단위(%)를 사용하지 않는 것이 좋습니다.

flex container의 자손은 flex item이 되지 않습니다.

* **Name**: display
* **Values**: flex \| inline-flex

<div class="cp_embed_wrapper"><iframe name="cp_embed_1" src="https://codepen.io/naradesign/embed/OmLrYK?height=265&amp;theme-id=light&amp;slug-hash=OmLrYK&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20container%20display%20property%20test.&amp;name=cp_embed_1" scrolling="no" frameborder="0" height="265" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex container display property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_OmLrYK"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### 신축성(flexibility): flex item의 팽창 및 수축.
flex item은 `flex-grow`(팽창지수), `flex-shrink`(수축지수), `flex-basis`(기준 사이즈) 속성과 이것들의 단축 속성인 `flex` 속성으로 박스의 팽창, 수축, 기준 사이즈를 제어할 수 있습니다. W3C 명세는 `flex` 단축 속성( `flex : none | [<flex-grow> <flex-shrink>? || <flex-basis>] `)으로 제어하는 것을 권장합니다. 단축 속성은 명시하지 않은 값을 일반적인 용도에 맞게 재설정하기 때문입니다. 단축 속성 선언 시 재설정되는 값에 대한 설명은 <a href="#flex-item의-단축-속성-flex">flex item의 단축 속성 'flex'</a>를 참고하세요. 참고: CSS 명세에서 바 `|`는 분리된 값들 중 반드시 '하나'를 선언해야 한다는 의미입니다. 더블 바 `||`는 분리된 값들 중 '하나 또는 그 이상'을 선언할 수 있다는 의미입니다. 물음표 `?`는 '생략하거나 또는 한 번만 선언'해야 한다는 의미입니다.

#### flex item의 팽창을 제어하는 `flex-grow` 속성.
* **Name**: flex-grow
* **Value**: &lt;number&gt; // 음수 값은 유효하지 않음. 보통 `0` 또는 `1` 값을 선언.
* **Initial**: 0 // 단축 속성 `flex` 사용 시 `flex-grow` 값을 생략하면 값은 초기 값은 `1`으로 다시 설정 됨.
* **Applies to**: flex items

 `flex-grow` 속성의 기본값은 `0` 이기 때문에 flex item은 기본적으로 팽창하지 않습니다. `flex-grow`의 값이 `0`이 아닌 경우에는 컨테이너 내부에 형성된 빈 공간(free space)을 팽창지수( `flex-grow`)에 따라 flex item에 반영하여 남은 공간을 채우게 됩니다. 공간이 남는 경우에는 `flex-grow` 속성에 의해 팽창하지만, 공간이 남지 않는 경우에는 아무리 값을 올려도 컨테이너의 너비 이상으로 팽창하지 않습니다. `max-width` 속성을 선언했다면 이 값을 초과하여 팽창하지 않습니다.

<div class="cp_embed_wrapper"><iframe name="cp_embed_2" src="https://codepen.io/naradesign/embed/aWdzQo?height=640&amp;theme-id=light&amp;slug-hash=aWdzQo&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20property%20test.&amp;name=cp_embed_2" scrolling="no" frameborder="0" height="640" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_aWdzQo"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

#### flex item의 수축을 제어하는 `flex-shrink` 속성.
* **Name**: flex-shrink
* **Value**: &lt;number&gt; // 음수 값은 유효하지 않음. 보통 `0` 또는 `1` 값을 선언.
* **Initial**: 1 // 단축 속성 `flex` 사용 시 `flex-shrink` 값을 생략해도 초기 값은 여전히 `1`이 된다.
* **Applies to**: flex items

 `flex-shrink` 속성의 기본값은 `1` 이기 때문에 flex item은 기본적으로 수축합니다. `flex-shrink` 값이 `0`인 경우 flex item의 너비가 컨테이너를 초과 해도 수축하지 않습니다. 한편 `flex-shrink` 값이 `0`이 아닌 경우에는 flex item이 컨테이너를 초과했을 때 넘치는 공간(이 때 음수 free space 발생)의 크기를 기준으로 수축지수( `flex-shrink`)에 따라 수축하게 됩니다. 컨테이너를 초과해서 공간이 모자라는 경우에는 `flex-shrink` 속성에 의해 수축하지만, 공간이 모자라지 않는 경우에는 아무리 값을 올려도 수축하지 않습니다. `min-width` 속성을 선언했다면 이 값 미만으로 수축하지 않습니다.

<div class="cp_embed_wrapper"><iframe name="cp_embed_3" src="https://codepen.io/naradesign/embed/vmLvWO?height=650&amp;theme-id=light&amp;slug-hash=vmLvWO&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20'flex-shrink'%20property%20test.&amp;name=cp_embed_3" scrolling="no" frameborder="0" height="650" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS 'flex-shrink' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_vmLvWO"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

#### flex item의 기준 사이즈를 제어하는 `flex-basis` 속성.
* **Name**: flex-basis
* **Value**: content \| &lt;width&gt;
* **Initial**: auto
* **Applies to**: flex items

 `flex-basis` 속성은 flex item 요소가 `flex-grow` 또는 `flex-shrink` 속성에 의해 팽창/수축하기 이전의 기준 크기를 명시하는 속성입니다. flex item에 `width/height`값을 명시하는 것은 `flex-basis` 값을 선언하는 것과 결과적으로 동일합니다. flex item의 팽창 또는 수축은 `width/height`값 또는 `flex-basis`에 선언한 값을 기준으로 free space(빈 공간) 값을 구하게 되고, free space 값은 팽창/수축 지수를 통해 flex item의 크기에 영향을 미치게 되므로 `flex-basis`(또는 `width/height`) 값을 가능하다면 명시적으로 선언하는 것이 좋습니다. 동일한 flex item에 `width/height` 값과 `flex-basis` 값을 동시 선언하는 경우 `flex-basis` 값은 `width` 값을 덮어 쓰기 때문에 코드를 간결하게 작성하려면 `width/height` 값을 선언하는 것보다 `flex-basis` 값을 선언하는 것을 권장합니다. `content` 값은 선언 불가능한 값입니다. `content` 값을 적용하려면 `auto` 값을 선언하고 `width/height` 속성을 사용하지 않아야 합니다.

<div class="cp_embed_wrapper"><iframe name="cp_embed_4" src="https://codepen.io/naradesign/embed/gWPQjV?height=650&amp;theme-id=light&amp;slug-hash=gWPQjV&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20'flex-basis'%20property%20test.&amp;name=cp_embed_4" scrolling="no" frameborder="0" height="650" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS 'flex-basis' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_gWPQjV"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

#### flex item의 단축 속성 `flex`.
 `flex` 속성은 `flex-grow`, `flex-shrink`, `flex-basis` 속성의 값을 하나의 속성값으로 작성할 수 있는 단축 속성입니다. flex item 요소에 `flex`와 관련 있는 아무런 속성도 선언하지 않은 경우 `flex-grow:0; flex-shrink:1; flex-basis:auto;` 다시 말하면 `flex:0 1 auto;` 상태가 됩니다. 세 가지 속성을 모두 선언할 수도 있지만 하나만 선언하고 다른 값을 생략할 수도 있는데요. 생략한 속성의 값은 자동으로 재설정 됩니다.

`flex` 단축 속성**은 아래와 같이 다양한 형태로 선언할 수 있습니다. 생략한 일부 속성의 값은 flex item에 아무런 속성도 선언하지 않았을 때의 값 `flex:0 1 auto;` 와도 다르고 `flex:none;` 을 선언했을 때의 값 `flex:0 0 auto;` 와도 다르다는 점에 유의하세요.

* `flex: none;`
  * // `flex-grow:0; flex-shrink:0; flex-basis:auto;` 상태가 된다.
* `flex: <flex-grow>`
  * // `flex-shrink:1; flex-basis:0;` 상태가 된다.
* `flex: <flex-basis>`
  * // `flex-grow:1; flex-shrink:1;` 상태가 된다.
* `flex: <flex-grow> <flex-shrink>`
  * // `flex-basis:0;` 상태가 된다.
* `flex: <flex-grow> <flex-basis>`
  * // `flex-shrink:1;` 상태가 된다.
* `flex: <flex-grow> <flex-shrink> <flex-basis>`
  * // 생략한 속성 없음.

### 관련 글
* <a href="flex-direction-order.md">CSS flexible 레이아웃: flex item의 방향과 순서.</a>
* <a href="flex-justify-align">CSS flexible 레이아웃: flex item의 정렬과 간격.</a>

### 참고
* <a href="https://www.w3.org/TR/css-flexbox-1/">CSS Flexsible box layout module level 1(Candidate Recommendation)</a>
* <a href="https://speckyboy.com/css-flexbox-toolbox/">CSS Flexbox learning guides, tools &amp; frameworks.</a>
* <a href="http://flexbox.help/">flexbox.help</a>
* <a href="http://caniuse.com/#search=flexible">caniuse.com</a>

