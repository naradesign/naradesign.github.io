## CSS flexible 레이아웃: flex item의 정렬과 간격.

<a href="flex-grow-shrink.html">flex item의 팽창과 수축</a>, <a href="flex-direction-order.html">flex item의 방향과 순서</a>에 이어 오늘은 '**flex item의 정렬과 간격**'에 관하여 설명합니다.

먼저 **진행 축**(main axis)과 **교차 축**(cross axis)을 이해할 필요가 있습니다. '진행 축'이란 flex item이 배치되는 축(x/y)을 의미합니다. '교차 축'이란 flex item이 배치되는 방향과 90도 교차하는 축을 의미합니다. 진행 축과 교차 축은 상대적인 개념이라서 `flex-direction`의 값( `row`, `column`)에 따라 교차 축이 바뀌기 때문에 헷갈리기 쉽습니다. `flex-direction:row`인 경우 교차 축은 y가 되지만 `flex-direction:column`인 경우 교차 축은 x가 되겠지요.

**한 줄**(single line)과 **여러 줄**(multi line)의 개념도 이해해야 합니다. 단일 행 또는 여러 행이라고 표현하지 않는 이유는 `flex-direction` 값( `row`, `column`)에 따라 여러 줄이 행이 될 수도 있지만 열이 될 수도 있기 때문입니다. 여러 줄은 `flex-basis` 값과 `flex-wrap:wrap` 속성에 의해 한 줄로 표현하기에 빈 공간(free space)이 모자라는 경우에만 발생합니다.

 `justify-content` 속성만 진행 축 정렬에 관여하고 `align-items`, `align-self`, `align-content` 속성은 모두 교차 축 정렬에 관여합니다.

* <a href="#flex-item의-진행-축-정렬과-간격을-제어하는-justify-content">flex item의 '진행 축' 정렬과 간격을 제어하는 'justify-content'.</a>
* <a href="#flex-item의-교차-축-정렬을-제어하는-align-items">flex item의 '교차 축' 정렬을 제어하는 'align-items'.</a>
* <a href="#flex-item의-독립적-교차-축-정렬을-제어하는-align-self">flex item의 '독립적 교차 축' 정렬을 제어하는 'align-self'.</a>
* <a href="#flex-item의-여러-줄-교차-축-정렬과-간격을-제어하는-align-content">flex item의 '여러 줄 교차 축' 정렬과 간격을 제어하는 'align-content'.</a>

### flex item의 '진행 축' 정렬과 간격을 제어하는 'justify-content'.
** `justify-content` 속성은 '진행 축' 정렬과 아이템 사이의 간격을 제어합니다**. `flex-direction: row | row-reverse` 인 경우 x축 정렬을 제어합니다. `flex-direction: column | column-reverse` 인 경우 y축 정렬을 제어합니다.

* Name: `justify-content`
* Value: `flex-start` \| `flex-end` \| `center` \| `space-between` \| `space-around`
* Initial: `flex-start`
* Applies to: **flex containers**

값이 `left`, `right`, `top`, `bottom`이 아닌 이유는 flex item의 진행 방향이 `flex-direction`의 값( `row`, `row-reverse`, `column`, `column-reverse`)에 따라 언제든 달라질 수 있기 때문입니다. 여분의 공간(free space)이 존재하는 경우 `space-between`, `space-around` 값을 통해서 flex item 사이의 공간을 제어할 수 있는데 `space-between`은 flex item과 flex container 경계면 사이에는 빈 공간을 만들지 않습니다. `center`, `space-between`, `space-around` 값에 의해 발생하는 flex item의 간격은 균등 분할되며 개별적으로 빈 공간을 제어하기를 원하는 경우 해당 flex item 요소에 별도의 `margin`을 추가해야 합니다.

<div class="cp_embed_wrapper"><iframe name="cp_embed_1" src="https://codepen.io/naradesign/embed/YVpaYZ?height=920&amp;theme-id=light&amp;slug-hash=YVpaYZ&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'justify-content'%20property%20test.&amp;name=cp_embed_1" scrolling="no" frameborder="0" height="920" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'justify-content' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_YVpaYZ"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### flex item의 '교차 축' 정렬을 제어하는 'align-items'.
** `align-items` 속성은 진행 축과 교차하는 '교차 축' 정렬을 제어합니다**. 여기서부터 조금 헷갈리기 쉬워요. `flex-direction: row | row-reverse` 인 경우 y축 정렬을 제어합니다. `flex-direction: column | column-reverse` 인 경우 x축 정렬을 제어합니다.

* Name: `align-items
* Value: `flex-start` \| `flex-end` \| `center` \| `baseline` \| `stretch`
* Initial: `stretch` // flex-direction:row 상태에서 flex item의 높이를 100%로 렌더링하는 이유는 이것 때문.
* Applies to: **flex containers**

 `flex-wrap:wrap` 속성에 의해 여러 줄(multi line)이 발생하는 경우 여러 줄의 정렬과 간격을 제어하는 `align-content` 속성의 값( `flex-start`, `flex-end`, `center`, `space-between`, `space-around`)에 따라 `align-items` 정렬은 무시됩니다. `baseline` 값은 flex item의 글꼴 사이즈( `font-size`)와 줄 간격( `line-height`)이 모두 동일한 경우  `flex-start` 값과 동일한 결과를 보여주지만, 글꼴 사이즈( `font-size`) 또는 줄 간격( `line-height`)을 flex item 마다 다르게 설정하면 포함하고 있는 문자열의 `baseline` 기준으로 정렬합니다. `baseline`을 쓸 일은 별로 없을 것 같은 생각이 드네요.

<div class="cp_embed_wrapper"><iframe name="cp_embed_2" src="https://codepen.io/naradesign/embed/mmOzqy?height=1000&amp;theme-id=light&amp;slug-hash=mmOzqy&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'align-items'%20property%20test.&amp;name=cp_embed_2" scrolling="no" frameborder="0" height="1000" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'align-items' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_mmOzqy"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### flex item의 '독립적 교차 축' 정렬을 제어하는 'align-self'.
** `align-self` 속성은 flex item의 독립적인 '교차 축' 정렬을 제어합니다**. flex item 요소에 각각 적용하기 때문에 flex container에 적용되어 있는 `align-items  속성의 교차 축 정렬 결과보다 우선 순위가 높습니다.

* Name: `align-self`
* Value: `auto` \| `flex-start` \| `flex-end` \| `center` \| `baseline` \| `stretch` // auto 값을 제외하면 align-items 값과 동일함.
* Initial: `auto` // auto 값은 flex container에 적용된 align-items 값으로 처리.
* Applies to: **flex items**

 `auto` 값은 flex container에 적용되어 있는 `align-items` 속성의 교차 축 정렬에 따르게 됩니다. 그 밖의 다른 값들( `flex-start`, `flex-end`, `center`, `baseline`, `stretch`)의 성질은 `align-items` 와 동일합니다.

<div class="cp_embed_wrapper"><iframe name="cp_embed_3" src="https://codepen.io/naradesign/embed/pPejdK?height=1110&amp;theme-id=light&amp;slug-hash=pPejdK&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'align-self'%20property%20test.&amp;name=cp_embed_3" scrolling="no" frameborder="0" height="1110" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'align-self' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_pPejdK"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### flex item의 '여러 줄 교차 축' 정렬과 간격을 제어하는 'align-content'.
** `align-content` 속성은 여러 줄(multi line)의 '교차 축' 정렬과 줄 사이 간격을 제어합니다**. 여러 줄이 발생하는 경우( `flex-wrap:wrap`)에만 적용되고, 여러 줄이 발생하는 경우 `align-items`의 교차 축 정렬보다 적용 우선순위가 높습니다.

* Name: `align-content`
* Value: `flex-start` \| `flex-end` \| `center` \| `space-between` \| `space-around` \| `stretch`
* Initial: `stretch`
* Applies to: **multi-line flex container**

 `align-items` 속성과 `align-content` 속성에서 이해하기 어려운 부분은 "왜 두 속성을 분리했는가?" 입니다. 양쪽 모두 교차 축 정렬에 관여하고 있으며 동일한 값( `stretch`, `center`, `flex-start`, `flex-end`)을 사용하기 때문에 하나의 속성으로 통일하는 것이 가능해 보였거든요.

 `align-items`인 경우 `stretch` 값의 표현이 flex item 박스를 교차축으로 끝까지 잡아 늘리는데 반해서, `align-content`인 경우 `stretch` 값의 표현은 flex item 박스의 교차축 크기는 변경하지 않고 교차축으로 줄 사이의 간격을 균등하게 벌어지게 만드는 점이 다르기는 합니다.

한 줄 또는 여러 줄 사이 교차축으로 빈 공간 없이 flex item을 가득 채우려면 `align-items:stretch; align-content:stretch;` 이렇게 두 속성 모두 값을 `stretch`로 처리하면 됩니다. 사실 `align-items`와 `align-content`의 기본값이 모두 `stretch` 이기 때문에 교차 축으로 `width`, `max-width`, `height`, `max-height` 속성을 사용하지 않았다면 교차축으로 빈 공간 없이 flex item이 채워지게 되어 있습니다. 아래 예제는 교차축 줄 사이 간격을 테스트하기 위해 `width`, `height` 값을 사용했습니다.

<div class="cp_embed_wrapper"><iframe name="cp_embed_4" src="https://codepen.io/naradesign/embed/ybMOgV?height=1306&amp;theme-id=light&amp;slug-hash=ybMOgV&amp;default-tab=result&amp;user=naradesign&amp;embed-version=2&amp;pen-title=CSS%20flex%20'align-content'%20property%20test.&amp;name=cp_embed_4" scrolling="no" frameborder="0" height="1306" allowtransparency="true" allowfullscreen="true" allowpaymentrequest="true" title="CSS flex 'align-content' property test." class="cp_embed_iframe " style="width: 100%; overflow:hidden; display:block;" id="cp_embed_ybMOgV"></iframe></div>
<script async="" src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

### 마무리
이번 포스팅을 마지막으로 flexible box 레이아웃 모듈 설명을 모두 마칩니다. 그동안 정리했던 내용을 다시 한번 요약하면 아래와 같습니다.

* <a href="flex-grow-shrink.html">CSS flexible 레이아웃: **flex item의 팽창과 수축**.</a>
  * 플렉스 컨테이너와 플렉스 아이템(flex container &amp; flex item)의 개념.
    * flex container(플렉스 컨테이너)
    * flex item(플렉스 아이템)
  * 신축성(flexibility): flex item의 팽창 및 수축.
    * flex item의 팽창을 제어하는 `flex-grow` 속성.
    * flex item의 수축을 제어하는 `flex-shrink` 속성.
    * flex item의 기준 사이즈를 제어하는 `flex-basis` 속성.
    * flex item의 단축 속성 `flex`.
* <a href="flex-direction-order.html">CSS flexible 레이아웃: **flex item의 방향과 순서**.</a>
  * flex item의 '방향'을 제어하는 `flex-direction`.
  * flex item의 '줄 바꿈'을 제어하는 `flex-wrap`.
  * flex item의 '뱡향과 줄 바꿈'을 제어하는 단축 속성 `flex-flow`.
  * flex item의 '배치 순서'를 제어하는 `order`.
* <a href="#">CSS flexible 레이아웃: **flex item의 정렬과 간격**.</a>
  * flex item의 '진행 축' 정렬과 간격을 제어하는 `justify-content`.
  * flex item의 '교차 축' 정렬을 제어하는 `align-items`.
  * flex item의 '독립적 교차 축' 정렬을 제어하는 `align-self`.
  * flex item의 '여러 줄 교차 축' 정렬과 간격을 제어하는 `align-content`.

### 참고
* <a href="https://www.w3.org/TR/css-flexbox-1/" target="_blank" rel="noopener noreferrer">CSS Flexsible box layout module level 1(Candidate Recommendation)</a>
* <a href="https://speckyboy.com/css-flexbox-toolbox/">CSS Flexbox learning guides, tools &amp; frameworks.</a>
* <a href="http://flexbox.help/">flexbox.help</a>
* <a href="http://caniuse.com/#search=flexible" target="_blank" rel="noopener noreferrer">caniuse.com</a>
