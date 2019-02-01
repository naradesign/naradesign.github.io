## HTML5 Transparent content models(투명 콘텐츠 모델).

### [원문] 3.2.4.3. Transparent content models
> Some elements are described as transparent; they have "transparent" in the description of their content model. The content model of a transparent element is derived from the content model of its parent element: the elements required in the part of the content model that is "transparent" are the same elements as required in the part of the content model of the parent of the transparent element in which the transparent element finds itself.


### [번역] 3.2.4.3. 투명 콘텐츠 모델
> 일부 요소들은 투명합니다. 투명한 요소들은 콘텐츠 모델 설명에서 "투명"한 것으로 되어 있습니다. 투명 요소의 콘텐츠 모델은 투명 요소의 부모 콘텐츠 모델을 따릅니다. "투명"한 콘텐츠 모델에 필요한 요소는 투명한 요소의 부모 콘텐츠 모델이 요구하는 것과 동일한 요소입니다.


### 투명 콘텐츠 모델 해설.
투명한 요소들은 `a`, `ins`, `del`, `object`, `video`, `audio`, `map`, `noscript`, `canvas` 인데요. "일부 요소들은 투명"하다는 설명은 구체적으로 이 요소들이 투명하다는 것을 의미합니다. 이 요소들의 콘텐츠 모델(자식으로 허용하는 요소)은 'transparent' 라고 설명하고 있는데요. 투명 요소의 콘텐츠 모델은 투명 요소 부모 콘텐츠 모델과 동일하게 결정됩니다.

예를 들어 `<p><a><div>…</div></a></p>` 이런 구조의 마크업이 있을 때 `a` 요소는 투명한 요소입니다. 투명한 `a` 요소는 제거할 수도 있으며 `a` 요소를 제거한 경우에도 문법적으로 유효해야 합니다. `a` 요소를 제거한 상황에서도 유효한 문법이 되려면 `a` 요소는 투명한 요소가 되어야 하고 이것은 `a` 요소의 콘텐츠 모델이 `p` 요소의 콘텐츠 모델에 따라야 한다는 것을 의미합니다.

`p` 요소의 콘텐츠 모델은 'phrasing' 이기 때문에 'flow' 콘텐츠인 `div` 요소는 `a` 요소의 자식이 될 수 없습니다. 하지만 `p` 요소가 없거나 `p` 대신 `section` 요소가 래퍼가 된다면 `section` 요소는 콘텐츠 모델이 'flow' 이기 때문에 이 상황에서는 `a` 요소는 'flow' 콘텐츠인 `div` 요소를 자식으로 둘 수 있게 됩니다.

`div` 요소는 'flow' 콘텐츠입니다. 예전에는 블럭 레벨이라고 불렀으나 HTML5 부터는 명세에 더 이상 블럭 레벨 또는 인라인 레벨이라는 설명을 사용하지 않습니다. 블럭 레벨 요소는 대부분 'flow' 콘텐츠가 됐고, 인라인 레벨 요소는 대부분 'phrasing' 콘텐츠로 분류가 됐습니다.

결국 투명한 요소와 투명한 콘텐츠 모델 덕분에 `a` 요소는 그 부모가 무엇인지에 따라 다양한 유형의 콘텐츠를 자식으로 담을 수 있게 됐습니다. 이게 정말 중요한 포인트입니다. 정리하면…

1. 콘텐츠 모델이 'transparent' 이면 그 부모가 투명한 요소라는 것을 의미한다.
1. 콘텐츠 모델이 'transparent' 라는 것은 투명한 요소의 콘텐츠 모델이 투명한 요소의 부모 콘텐츠 모델을 따른다는 것을 의미한다.
1. 투명한 요소를 제거하더라도 그 부모와 자식 사이의 관계는 유효해야 한다.

### 참고
* W3C HTML5.1 – transparent content models
  * <a href="https://www.w3.org/TR/html51/dom.html#transparent-content-models">https://www.w3.org/TR/html51/dom.html#transparent-content-models</a>
* 명세 번역
  * 지성봉 – <a href="https://mulder21c.github.io/html/dom.html#transparent-content-models">https://mulder21c.github.io/html/dom.html#transparent-content-models</a>
  * 조은 – <a href="https://www.facebook.com/eun.cho.161/posts/1395358057213835?hc_location=ufi">https://www.facebook.com/eun.cho.161/posts/1395358057213835?hc_location=ufi</a>

