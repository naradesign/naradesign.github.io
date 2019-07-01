## HTML5 New elements.

늦은 감이 있지만 HTML5 에서 새롭게 등장한 새로운 시멘틱 요소들에 관한 명세를 부분적으로 번역(의역)해서 요약했습니다. 참고 사항에 있는 주요한 해설을 임의로 포함했기 때문에 직역을 통해서 발견할 수 없는 단어나 문장이 번역에 포함되어 있습니다. 애매하거나 잘못 해석한 부분에 대한 댓글 또는 토론을 기다리고 있습니다. 이 글은 <a href="https://docs.google.com/presentation/d/1EDoo-_013DT0-oGbi6ubczmQYnJg-IwMuthU1EcPAmk/edit?usp=sharing">발표 자료 형식</a>으로 강의했던 내용을 텍스트로 옮긴 것입니다. HTML5가 의미 있게 쓰였으면 좋겠네요.

### New sections
#### &lt;header&gt;
> The header element represents introductory content for its nearest ancestor sectioning content or sectioning root element. A header typically contains a group of introductory or navigational aids.

가까운 조상 섹셔닝 콘텐츠(article, section, nav, aside) 또는 가까운 조상 섹셔닝 루트(`body`, `figure`, `fieldset`, `blockquote`, `td`)의 머리말이 된다. 보통 도입부 또는 탐색 영역을 포함한다.

<cite><a href="https://www.w3.org/TR/html5/sections.html#the-header-element">https://www.w3.org/TR/html5/sections.html#the-header-element</a></cite>

#### &lt;footer&gt;
> The footer element represents a footer for its nearest ancestor sectioning content or sectioning root element. A footer typically contains information about its section such as who wrote it, links to related documents, copyright data, and the like.

가까운 조상 섹셔닝 콘텐츠(article, section, nav, aside) 또는 가까운 조상 섹셔닝 루트(`body`, `figure`, `fieldset`, `blockquote`, `td`)의 꼬리말이 된다. 보통 저자 정보, 관련 링크, 저작권 등의 내용을 포함한다.

<cite><a href="https://www.w3.org/TR/html5/sections.html#the-footer-element">https://www.w3.org/TR/html5/sections.html#the-footer-element</a></cite>

#### &lt;section&gt;
> The section element represents a generic section of a document or application. A section, in this context, is a thematic grouping of content. The theme of each section should be identified, typically by including a heading (h1-h6 element) as a child of the section element.

문서 또는 애플리케이션의 절(섹션)을 의미한다. 각 절을 주제에 따라 나눈 것으로 각 섹션의 주제는 서로 구분 되어야 한다. 개요(outline)를 생성하는 섹셔닝 콘텐츠이다. 문서의 구조를 견고하게 만들기 위해 헤딩(`h1`~`h6`)을 포함하는 것을 권장한다.

<cite><a href="https://www.w3.org/TR/html5/sections.html#the-section-element">https://www.w3.org/TR/html5/sections.html#the-section-element</a></cite>

#### &lt;article&gt;
> The article element represents a complete, or self-contained, composition in a document, page, application, or site and that is, in principle, independently distributable or reusable, e.g. in syndication. This could be a forum post, a magazine or newspaper article, a blog entry, a user-submitted comment, an interactive widget or gadget, or any other independent item of content.

독립적인 배포와 재 사용이 가능한 완결형 요소를 의미한다. 포럼 게시물, 잡지 또는 뉴스 기사, 블로그 본문, 사용자가 작성한 댓글, 상호작용 위젯 등 독립적인 내용이 올 수 있다. 개요(outline)를 생성하는 섹셔닝 콘텐츠이다. 문서의 구조를 견고하게 만들기 위해 헤딩(`h1`~`h6`)을 포함하는 것을 권장한다.

<cite><a href="https://www.w3.org/TR/html5/sections.html#the-article-element">https://www.w3.org/TR/html5/sections.html#the-article-element</a></cite>

#### &lt;nav&gt;
> The nav element represents a section of a page that links to other pages or to parts within the page: a section with navigation links.

다른 페이지 또는 현재 페이지의 일부를 링크하는 주된 탐색 섹션이다. 개요(outline)를 생성하는 섹셔닝 콘텐츠이다. 문서의 구조를 견고하게 만들기 위해 헤딩(`h1`~`h6`)을 포함하는 것을 권장한다.

<cite><a href="https://www.w3.org/TR/html5/sections.html#the-nav-element">https://www.w3.org/TR/html5/sections.html#the-nav-element</a></cite>

#### &lt;aside&gt;
> The aside element represents a section of a page that consists of content that is tangentially related to the content around the aside element, and which could be considered separate from that content. Such sections are often represented as sidebars in printed typography. The element can be used for typographical effects like pull quotes or sidebars, for advertising, for groups of nav elements, and for other content that is considered separate from the main content of the page.

페이지의 주된 내용과 관련이 약해서 구분할 필요가 있는 섹션. 관련 기사, 광고 등의 내용을 포함할 수 있다. 개요(outline)를 생성하는 섹셔닝 콘텐츠이다. 문서의 구조를 견고하게 만들기 위해 헤딩(`h1`~`h6`)을 포함하는 것을 권장한다.

<cite><a href="https://www.w3.org/TR/html5/sections.html#the-aside-element">https://www.w3.org/TR/html5/sections.html#the-aside-element</a></cite>

### New grouping content
#### &lt;main&gt;
> The main element represents the main content of the body of a document or application. The main content area consists of content that is directly related to or expands upon the central topic of a document or central functionality of an application. The main content area of a document includes content that is unique to that document and excludes content that is repeated across a set of documents such as site navigation links, copyright information, site logos and banners and search forms (unless the document or applications main function is that of a search form). Authors must not include more than one main element in a document. Authors must not include the main element as a descendant of an article, aside, footer, header or nav element.

문서의 핵심 주제 또는 애플리케이션의 핵심 기능과 직접적으로 관련 있는 콘텐츠 영역을 의미한다. 페이지마다 반복되지 않는 내용을 포함해야 한다. 섹셔닝 콘텐츠는 아니기 때문에 개요(outline)를 형성하지는 않는다. 하나의 페이지 안에서 한 번만 선언할 수 있고 `article`, `aside`, `header`, `footer`, `nav` 요소의 자식이 될 수 없다.

<cite><a href="https://www.w3.org/TR/html5/grouping-content.html#the-main-element">https://www.w3.org/TR/html5/grouping-content.html#the-main-element</a></cite>

#### &lt;figure&gt;
> The figure element represents some flow content, optionally with a caption, that is self-contained (like a complete sentence) and is typically referenced as a single unit from the main flow of the document. The element can thus be used to annotate illustrations, diagrams, photos, code listings, etc.

문서의 주된 흐름을 위해 참조되는 독립적인 완결형 요소로서 삽화 설명, 도표, 사진, 코드 등 일반적인 내용을 포함할 수 있다. 선택적으로 처음 또는 마지막에 `figcaption` 요소를 자식 요소로 포함할 수 있고 또는 생략할 수 있다. `figure` 안에서 `figcaption` 요소가 선언 된다면 한 번만 선언할 수 있다.

<cite><a href="https://www.w3.org/TR/html5/grouping-content.html#the-figure-element">https://www.w3.org/TR/html5/grouping-content.html#the-figure-element</a></cite>

#### &lt;figcaption&gt;
> The figcaption element represents a caption or legend for the rest of the contents of the figcaption element’s parent figure element, if any.

부모 `figure` 요소의 내용에 대한 설명 또는 범례를 의미한다. 반드시 `figure` 요소의 처음 또는 마지막에 포함할 수 있고 또는 생략할 수 있다. `figure` 안에서 한 번만 선언할 수 있다.

<cite><a href="https://www.w3.org/TR/html5/grouping-content.html#the-figcaption-element">https://www.w3.org/TR/html5/grouping-content.html#the-figcaption-element</a></cite>

### New text level semantics
#### &lt;data&gt;
> The data element represents its contents, along with a machine-readable form of those contents in the value attribute. The value attribute must be present. Its value must be a representation of the element’s contents in a machine-readable format.

자신의 내용을 의미한다. `value` 속성을 통해서 사람에게 제공된 내용을 기계가 읽을 수 있는 값으로 함께 제공하는 요소이다. `value` 속성은 반드시 선언되어야 하고, `value` 속성의 값은 반드시 기계적으로 해석 가능한 형식이어야 한다.

```
예) <data value="ISBN:978-89-5460-326-3">정찬명의 HTML 완벽 가이드</data>
```

<cite><a href="https://www.w3.org/TR/html5/text-level-semantics.html#the-data-element">https://www.w3.org/TR/html5/text-level-semantics.html#the-data-element</a></cite>

#### &lt;time&gt;
> The time element represents its contents, along with a machine-readable form of those contents in the datetime attribute. The kind of content is limited to various kinds of dates, times, time-zone offsets, and durations, as described below. The datetime attribute may be present. If present, its value must be a representation of the element’s contents in a machine-readable format. A time element that does not have a datetime content attribute must not have any element descendants. The datetime value of a time element is the value of the element’s datetime content attribute, if it has one, or the element’s textContent, if it does not.

기계적으로 해석 가능한 `datetime` 속성의 값을 통해 다양한 형식으로 날짜, 시간, 타임존 그리고 기간 정보를 제공한다. `datetime` 속성은 생략 가능하다. 생략하는 경우 `datetime` 속성의 유효한 값(시간을 나타내는 표준 양식, 텍스트)을 내용으로 포함해야 한다.

```
예)
<time>2011-11-12T14:54:39Z</time> // T = time, Z = UTC
<time datetime="2011-11-12T14:54:39Z">11월 12일(UTC)</time>
<time>2011-11-12T14:54+09:00</time> // 9시간을 더하여 한국 시간으로 표시
<time>4h 18m 3s</time> // 기간을 나타내는 형식
<time datetime="4h 18m 3s">4시간 18분 3초</time>
```

<cite><a href="https://www.w3.org/TR/html5/text-level-semantics.html#the-time-element">https://www.w3.org/TR/html5/text-level-semantics.html#the-time-element</a></cite>

#### &lt;mark&gt;
> The mark element represents a run of text in one document marked or highlighted for reference purposes, due to its relevance in another context. When used in a quotation or other block of text referred to from the prose, it indicates a highlight that was not originally present but which has been added to bring the reader’s attention to a part of the text that might not have been considered important by the original author when the block was originally written, but which is now under previously unexpected scrutiny. When used in the main prose of a document, it indicates a part of the document that has been highlighted due to its likely relevance to the user’s current activity.

본래 의도된 맥락에서 벗어나 표시된 문자가 실행된 것, 또는 참조 목적의 강조를 의미한다. 저자에 의한 것이 아닌 현재 독자의 행위나 관심에 따라 강조된 것이다. 검색 결과 목록에서 사용자가 입력한 키워드를 강조할 때 적당하다.

<cite><a href="https://www.w3.org/TR/html5/text-level-semantics.html#the-mark-element">https://www.w3.org/TR/html5/text-level-semantics.html#the-mark-element</a></cite>

#### &lt;wbr&gt;
> The wbr element represents a line break opportunity.

줄 바꿈이 생기는 경우 줄 바꿈이 이루어져야 하는 지점을 의미한다.

```
예) The<wbr>power<wbr>of<wbr>the<wbr>Web<wbr>is<wbr>in<wbr>its<wbr>universality.<wbr>Access<wbr>by<wbr>everyone<wbr>regardless<wbr>of<wbr>disability<wbr>is<wbr>an<wbr>essential<wbr>aspect.
```

`wbr` = Word Break Opportunity

<cite><a href="https://www.w3.org/TR/html5/text-level-semantics.html#the-wbr-element">https://www.w3.org/TR/html5/text-level-semantics.html#the-wbr-element</a></cite>

### New embeded content
#### &lt;video&gt;
> A video element is used for playing videos or movies, and audio files with captions. Content may be provided inside the video element. User agents should not show this content to the user; it is intended for older Web browsers which do not support video, so that legacy video plugins can be tried, or to show text to the users of these older browsers informing them of how to access the video contents.

자막과 함께 영상과 음성을 재생한다. 자식 요소로 폴백 콘텐츠를 제공할 수 있는데 `video` 요소를 지원하지 않는 낡은 웹 브라우저를 위한 것이다. 오래된 플러그인(예를 들면 `*.swf` `object`)을 시도하거나 낡은 브라우저 사용자를 위한 비디오 이용 안내를 문자로 제공할 수도 있다.

<cite><a href="https://www.w3.org/TR/html5/embedded-content-0.html#the-video-element">https://www.w3.org/TR/html5/embedded-content-0.html#the-video-element</a></cite>

#### &lt;audio&gt;
> An audio element represents a sound or audio stream. Content may be provided inside the audio element. User agents should not show this content to the user; it is intended for older Web browsers which do not support audio, so that legacy audio plugins can be tried, or to show text to the users of these older browsers informing them of how to access the audio contents.

음성을 재생한다. 자식 요소로 대체 콘텐츠를 제공할 수 있는데 `audio` 요소를 지원하지 않는 낡은 웹 브라우저를 위한 것이다. 오래된 플러그인(예를 들면 `.swf` `object`)을 시도하거나 낡은 브라우저 사용자를 위한 오디오 이용 안내를 문자로 제공할 수도 있다.

<cite><a href="https://www.w3.org/TR/html5/embedded-content-0.html#the-audio-element">https://www.w3.org/TR/html5/embedded-content-0.html#the-audio-element</a></cite>

#### &lt;source&gt;
> The source element allows authors to specify multiple alternative media resources for media elements. It does not represent anything on its own. The src attribute gives the address of the media resource. The value must be a valid non-empty URL potentially surrounded by spaces. This attribute must be present.

`video` 또는 `audio` 요소에 다양한 형식의 대체 미디어 자원을 제공할 수 있게 해 준다. `src` 속성은 반드시 선언해야 하고 `src` 속성의 값으로는 미디어 자원의 주소를 포함해야 한다.

```
예)

<video>
  <source src="movie.mp4" type="video/mp4"> // 1st fallback 1
  <source src="movie.webm" type="video/webm"> // 1st fallback 2
  <source src="movie.ogv" type="video/ogg"> // 1st fallback 3
  <object> // 2nd fallback
    fall back content . // 3rd fallback
  </object>
</videio>
```

<cite><a href="https://www.w3.org/TR/html5/embedded-content-0.html#the-source-element">https://www.w3.org/TR/html5/embedded-content-0.html#the-source-element</a></cite>

#### &lt;track&gt;
> The track element allows authors to specify explicit external timed text tracks for media elements. It does not represent anything on its own.

`video` 또는 `audio` 요소의 장면 또는 음성과 동기화된 자막.

```
예)

<video>
  <source src="movie.mp4" type="video/mp4">
  <track kind="captions" src="movie.vtt" srclang="en">
</video>
```

`vtt` = Video Text Track

<cite><a href="https://www.w3.org/TR/html5/embedded-content-0.html#the-track-element">https://www.w3.org/TR/html5/embedded-content-0.html#the-track-element</a></cite>

### New forms
#### &lt;datalist&gt;
> The datalist element represents a set of option elements that represent predefined options for other controls. In the rendering, the datalist element represents nothing and it, along with its children, should be hidden.

다른 콘트롤을 위해 미리 정의된 옵션 세트를 의미한다. 숨겨진 상태로 표시된다.

```
예)

<label for="local">지역번호:</label>
<input type="text" id="local" list="local-list">
<datalist id="local-list">
  <option value="02">서울</option>
  <option value="031">경기</option>
</datalist>
```

데모 – <a href="http://naradesign.net/html5/form/input_list.html">http://naradesign.net/html5/form/input_list.html</a>

<cite><a href="https://www.w3.org/TR/html5/forms.html#the-datalist-element">https://www.w3.org/TR/html5/forms.html#the-datalist-element</a></cite>

#### &lt;output&gt;
> The output element represents the result of a calculation or user action.

계산 또는 사용자 실행의 결과를 의미한다.

```
예) <input value="1"> + <input value="1"> = <output>2</output>
```

데모 – <a href="http://naradesign.net/html5/form/output.html">http://naradesign.net/html5/form/output.html</a>

<cite><a href="https://www.w3.org/TR/html5/forms.html#the-output-element">https://www.w3.org/TR/html5/forms.html#the-output-element</a></cite>

#### &lt;progress&gt;
> The progress element represents the completion progress of a task. The progress is either indeterminate, indicating that progress is being made but that it is not clear how much more work remains to be done before the task is complete (e.g. because the task is waiting for a remote host to respond), or the progress is a number in the range zero to a maximum, giving the fraction of work that has so far been completed.

과업의 진척도를 의미한다. 원격 호스트의 응답을 기다려야 하는 경우도 있을 수 있기 때문에 진척도는 정확하지 않을 수도 있다. 낡은 브라우저를 위해 `value` 값과 별도로 콘텐츠를 제공하는 것이 좋다.

```
예) <progress value="0.5">0.5/1</progress>
```

데모 – <a href="http://naradesign.net/html5/form/progress.html">http://naradesign.net/html5/form/progress.html</a>

<cite><a href="https://www.w3.org/TR/html5/forms.html#the-progress-element">https://www.w3.org/TR/html5/forms.html#the-progress-element</a></cite>

#### &lt;meter&gt;
> The meter element represents a scalar measurement within a known range, or a fractional value; for example disk usage, the relevance of a query result, or the fraction of a voting population to have selected a particular candidate. This is also known as a gauge.

알려진 범위 내에서 측정 가능한 값을 의미한다. 디스크 사용량, 질의 결과에 대한 관련성, 후보에 대한 투표 수 등을 측정하는 개념이다.

```
예) <meter value="0.5">0.5/1</meter>
```

데모 – <a href="http://naradesign.net/html5/form/meter.html">http://naradesign.net/html5/form/meter.html</a>

<cite><a href="https://www.w3.org/TR/html5/forms.html#the-meter-element">https://www.w3.org/TR/html5/forms.html#the-meter-element</a></cite>

### New scripting
#### &lt;template&gt;
> The template element is used to declare fragments of HTML that can be cloned and inserted in the document by script.

스크립트에 의해 복사 또는 삽입되는 HTML 코드 샘플이다.

```
예)

<table>
    <thead>
        <tr>
            <th scope="row">Name</th>
            <th scope="row">Age</th>
        </tr>
    </thead>
    <tbody>
        <template id="row">
            <tr>
                <td></td>
                <td></td>
            </tr>
        </template>
    </tbody>
</table>
```


<cite><a href="https://www.w3.org/TR/html5/scripting-1.html#the-template-element">https://www.w3.org/TR/html5/scripting-1.html#the-template-element</a></cite>

#### &lt;canvas&gt;
> The canvas element provides scripts with a resolution-dependent bitmap canvas, which can be used for rendering graphs, game graphics, art, or other visual images on the fly.

실시간 그래프, 게임 그래픽, 아트, 시각적 이미지를 자바스크립트를 통해 비트맵으로 제공한다. 낡은 브라우저를 위한 대체 콘텐츠를 자식 요소로 제공할 수 있다.

데모 – <a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API</a>

<cite><a href="https://www.w3.org/TR/html5/scripting-1.html#the-canvas-element">https://www.w3.org/TR/html5/scripting-1.html#the-canvas-element</a></cite>

<div id="fb-root"></div>
<script async defer crossorigin="anonymous" src="https://connect.facebook.net/ko_KR/sdk.js#xfbml=1&version=v3.3"></script>
<div class="fb-comments" data-href="https://naradesign.github.io/article/html5-new-elements.html" data-numposts="10" data-width="100%"></div>
