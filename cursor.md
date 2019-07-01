## `a`, `button`, `label` 요소의 커서 모양.

그동안은 단순히 "커서 모양만으로 클릭 가능하다는 것을 예측할 수 있으면 좋겠다." 라고만 생각했습니다. 즉, `button`, `label` 모두 <code style="cursor: pointer;">{cursor:pointer}</code> 스타일로 처리해 왔는데 주변에서 이런 방식에 이의를 제기했던 사람은 없었습니다.

개인적 경험에 비춰 봐도 커서 모양이 나를 혼란에 빠트린 적은 없었거든요. 이래도 그만 저래도 그만 아주 사소한 문제일 수 있는데 사람들이 별로 관심을 두지 않는 문제라서 더 흥미롭게 느껴지네요.

<a href="https://www.w3.org/TR/css-ui-3/#cursor" target="_blank">W3C CSS cursor</a> 명세와 함께 구글, 페이스북, 애플 웹 사이트를 돌아보고 내린 결론은 다음과 같습니다.

"가능하다면 W3C 권장 표준을 따르는 것이 좋겠다. 그럴 수 있을 것 같다. 그래도 될 것 같다."

### 첫째
표준에서 <code style="cursor: pointer;">{cursor:pointer}</code> 값은 링크를 가리킵니다. "The cursor is a pointer that indicates a **link**." 라고 명시해 두었는데요. 따라서 앞으로 가능한 한 이 규칙에 따르려고 합니다.

### 둘째
하지만 커서 모양만 놓고 봤을 때 문서 여백에 해당하는 `body` 요소와 `button`, `label` 요소의 커서 모양이 <code style="cursor: default;">{cursor:default}</code> 형태로 동일하다는 것은 좋은 사용자 경험이 아닐 거라고 생각합니다.

### 셋째
커서 모양은 표준이 있으므로 따르고, 콘텐츠 스타일에는 표준이 없으므로 `button`, `label` 요소에 커서 모양 이외 다른 시각적 단서를 남기는 것이 좋겠습니다. 예를 들면 `button`, `label` 요소에 커서를 올렸을 때 해당 요소에 배경 색이나 명도를 다르게 처리함으로써 클릭할 수 있다는 시각적 단서를 남기고 사용자에게 확신을 줄 수 있을 것이라고 생각합니다.

<iframe style="width: 100%;" title="버튼과 레이블 커서 모양을 표준에 따르되 다른 시각적 단서를 제공한 예." src="https://codepen.io/naradesign/embed/pEvmdx/?height=300&amp;theme-id=light&amp;default-tab=result&amp;embed-version=2" width="300" height="300" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen">See the Pen <a href="http://codepen.io/naradesign/pen/pEvmdx/"><button> 요소와 <label> 요소의 커서는 어떤 형태이어야 하는가?</label></button></a> by Jeong Chan-Myeong (<a href="http://codepen.io/naradesign">@naradesign</a>) on <a href="http://codepen.io">CodePen</a>.
</iframe>

"가능하다면 W3C 권장 표준을 따르는 것이 좋겠다. 그럴 수 있을 것 같다. 그래도 될 것 같다."

영감을 주었던 글: <a href="http://story.pxd.co.kr/1165" target="_blank">세상에서 가장 쪼잔한 질문 – 체크박스 옆 라벨 커서는 어떻게 만들어야 할까?</a>

<div id="fb-root"></div>
<script async defer crossorigin="anonymous" src="https://connect.facebook.net/ko_KR/sdk.js#xfbml=1&version=v3.3"></script>
<div class="fb-comments" data-href="https://naradesign.github.io/article/cursor.html" data-numposts="10" data-width="100%"></div>
