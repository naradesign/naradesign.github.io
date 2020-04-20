## CSS flexible 레이아웃: flex item의 방향과 순서.

며칠 전 "<a href="flex-grow-shrink.html">CSS flexible 레이아웃: flex item의 수축과 팽창.</a>" 이라는 포스트를 작성했는데요. 오늘은 flex item의 방향과 순서를 설명합니다.  오늘 설명할 속성은 flex item의 방향을 제어하는 `flex-direction`, 줄 바꿈을 제어하는 `flex-wrap`, 그리고 방향과 줄 바꿈을 단축 속성으로 제어하는 `flex-flow`, 배치 순서를 제어하는 `order` 라는 속성에 대하여 설명합니다. 예제를 보면서 이해하기에 충분하므로 자세한 설명은 생략합니다.

* <a href="#flex-item의-방향을-제어하는-flex-direction">flex item의 '방향'을 제어하는 'flex-direction'.</a>
* <a href="#flex-item의-줄-바꿈을-제어하는-flex-wrap">flex item의 '줄 바꿈'을 제어하는 'flex-wrap'.</a>
* <a href="#flex-item의-뱡향과-줄-바꿈을-제어하는-단축-속성-flex-flow">flex item의 '뱡향과 줄 바꿈'을 제어하는 단축 속성 'flex-flow'.</a>
* <a href="#flex-item의-배치-순서를-제어하는-order">flex item의 '배치 순서'를 제어하는 'order'.</a>

### flex item의 '방향'을 제어하는 'flex-direction'.
 `flex-direction` 속성은 flex item이 흐르는 방향(상하좌우)을 제어합니다.

* Name: `flex-direction`
* Value: `row` \| `row-reverse` \| `column` \| `column-reverse`
* Initial: `row`
* Applies to: **flex container**

<div class="cp_embed_wrapper"><iframe name="cp_embed_1" src="https://codepen.io/naradesign/embed/wdzBLz?height=374&amp;theme-id=light&amp;slug-hash=wdzBLz&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'flex-direction'%20property%20test.&amp;name=cp_embed_1" scrolling="no" frameborder="0" height="374" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'flex-direction' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_wdzBLz"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### flex item의 '줄 바꿈'을 제어하는 'flex-wrap'.
 `flex-wrap` 속성은 flex item의 줄 바꿈 성질을 제어합니다.

* Name: `flex-wrap`
* Value: `nowrap` \| `wrap` \| `wrap-reverse`
* Initial: `nowrap`
* Applies to: **flex container**

<div class="cp_embed_wrapper"><iframe name="cp_embed_2" src="https://codepen.io/naradesign/embed/JNRdoz?height=375&amp;theme-id=light&amp;slug-hash=JNRdoz&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'flex-wrap'%20property%20test.&amp;name=cp_embed_2" scrolling="no" frameborder="0" height="375" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'flex-wrap' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_JNRdoz"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### flex item의 '뱡향과 줄 바꿈'을 제어하는 단축 속성 'flex-flow'.
 `flex-flow` 속성은 flex item의 `flex-direction` 속성과 `flex-wrap` 속성의 값을 한꺼번에 작성할 수 있는 단축 속성입니다.

* Name: `flex-flow`
* Value: `<flex-direction>` \|\| `<flex-wrap>` // 둘 중 하나 또는 둘을 선언해야 한다.
* Initial: `row nowrap`
* Applies to: **flex container**

<div class="cp_embed_wrapper"><iframe name="cp_embed_3" src="https://codepen.io/naradesign/embed/jmMPMa?height=950&amp;theme-id=light&amp;slug-hash=jmMPMa&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'flex-flow'%20property%20test.&amp;name=cp_embed_3" scrolling="no" frameborder="0" height="950" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'flex-flow' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_jmMPMa"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### flex item의 '배치 순서'를 제어하는 'order'.
 `order` 속성은 flex item의 배치 순서를 제어하는 속성입니다. 기본값은 ' `0`'이며 `flex-direction` 속성의 방향값( `row`, `row-reverse`, `column`, `column-reverse`)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치합니다.

* Name: `order`
* Value: `<integer>` // '0, 양의 정수, 음의 정수'를 사용할 수 있음.
* Initial: `0`
* Applies to: **flex items** and absolutely-positioned children of flex containers // 절대값으로 처리된 flex-item에도 적용 가능하다고 하는데 어떤 상황에서 쓰이는지 정확히 알 수 없음.

<div class="cp_embed_wrapper"><iframe name="cp_embed_4" src="https://codepen.io/naradesign/embed/EmgKad?height=560&amp;theme-id=light&amp;slug-hash=EmgKad&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'order'%20property%20test.&amp;name=cp_embed_4" scrolling="no" frameborder="0" height="560" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'order' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_EmgKad"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### 관련 글
* <a href="flex-grow-shrink.html">CSS flexible 레이아웃: flex item의 팽창과 수축.</a>
* <a href="flex-justify-align.html">CSS flexible 레이아웃: flex item의 정렬과 간격.</a>

### 참고
* <a href="https://www.w3.org/TR/css-flexbox-1/" target="_blank" rel="noopener noreferrer">CSS Flexsible box layout module level 1(Candidate Recommendation)</a>
* <a href="https://speckyboy.com/css-flexbox-toolbox/">CSS Flexbox learning guides, tools &amp; frameworks.</a>
* <a href="http://flexbox.help/">flexbox.help</a>
* <a href="http://caniuse.com/#search=flexible" target="_blank" rel="noopener noreferrer">caniuse.com</a>
