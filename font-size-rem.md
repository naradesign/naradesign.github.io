## CSS3 `{font-size:*rem}` relative value.

CSS3 `font-size` 속성 값으로 새로운 상대적 단위 `rem`을 사용할 수 있게 됐습니다.

* 용법 – <a href="http://snook.ca/archives/html_and_css/font-size-with-rem">http://snook.ca/archives/html_and_css/font-size-with-rem</a>
* 명세 – <a href="http://www.w3.org/TR/css3-values/#font-relative-lengths">http://www.w3.org/TR/css3-values/#font-relative-lengths</a>
* 브라우저 지원 현황 – <a href="http://caniuse.com/#search=rem">http://caniuse.com/#search=rem</a> (IE9 브라우저와 최신 브라우저에서 모두 지원합니다. 하지만 IE9 미만을 지원하는 폴백이 있습니다. 용법 참조.)

### rem 값의 의미
본래 <a href="http://en.wikipedia.org/wiki/Em_(typography)">em</a>이라는 단위는 글꼴 세트의 알파벳 대문자 `M`의 너비를 의미한다고 합니다. 어원 자체는 그렇고 통상 웹 브라우에서는 `1em` = `16px` 으로 환산이 되고요. `1em`은 웹 브라우저에서 글꼴 사이즈를 지정하지 않았을 때 표시되는 글꼴 크기의 기본값입니다. CSS3의 글꼴 크기 값으로 새로 등장한 `rem` 단위는 root em 이라는 의미입니다. HTML 문서에서 root 요소는 `&lt;html&gt;` 요소를 의미하고 `html` 요소에 지정된 글꼴 크기로부터 선택된 요소의 글꼴 크기를 상대적으로 결정하는 것이 바로 `rem` 단위의 핵심입니다.

### `em` vs `rem`
`em` 단위는 부모로부터 글꼴 크기를 물려받지만, `rem` 단위는 부모가 아닌 시조(root = `html`)로부터 글꼴 크기를 물려받는다는 점이 다릅니다. 예를 들어.. `em` 단위는 부모로부터 글꼴 크기를 물려받기 때문에 같은 값을 지니더라도 노드가 깊어질수록 글꼴 크기가 기하 급수적으로 크거나 작아집니다. 이런 방식의 문제는 부모 또는 조상 노드 가운데 어떤 요소의 글꼴 사이즈 값을 변경할 때 모든 자식과 자손 요소도 그 영향을 받는다는 점입니다. 예측하기 어렵고 계산하기 복잡하다는 것이 치명적인 문제입니다. 글꼴의 확대 축소를 유연하게 만들기 위한 목적으로 존재하지만 복잡하기 때문에 개발자들은 이 방법을 기피해왔습니다.

> * html = 100% = 16px
>   * body = 0.5**em** = 8px
>     * div = 0.5**em** = 4px
>       * p = 0.5**em** = 2px

`rem` 단위는 부모 아닌 시조로부터 글꼴 크기를 물려받기 때문에 `html` 요소에 기본 글꼴 크기를 지정해 두면 항상 `html` 요소로부터 글꼴 크기를 상속 받습니다. `html` 요소의 글꼴 크기를 변경하는것 만으로 페이지의 모든 글꼴 크기를 변경할 수 있다는 점 자체는 `em` 요소와 다를바 없지만 `rem` 요소는 부모 요소로부터 상속을 받지 않기 때문에 페이지 모든 글꼴의 크기 변화를 예측할 수 있고 계산하기도 쉽습니다. `em` 단위를 사용했을 때 `p` 요소가 `2px` 크기로 현실성 없게 작아진 것에 비하면 `rem` 단위를 사용했을 때에는 그렇지 않게 됩니다.

> * html = 100% = 16px
>   * body = 0.5**rem** = 8px
>     * div = 0.5**rem** = 8px
>       * p = 0.5**rem** = 8px

### 유용한 상황
단말기의 해상도에 따라 기본 글꼴 크기를 전체적으로 다르게 제어할 필요가 있을 때 미디어쿼리와 함께 `rem` 단위를 사용하면 효과적입니다. 예를 들어 데스크톱 글꼴이 `10px` ~ `20px` 범위인데 모바일 단말에서 전체적으로 `20px` ~ `40px` 범위로 키우고 싶다면 CSS 만으로 아주 간단하게 처리할 수 있습니다.

<div id="fb-root"></div>
<script async defer crossorigin="anonymous" src="https://connect.facebook.net/ko_KR/sdk.js#xfbml=1&version=v3.3"></script>
<div class="fb-comments" data-href="https://naradesign.github.io/article/font-size-rem.html" data-numposts="10" data-width="100%"></div>
