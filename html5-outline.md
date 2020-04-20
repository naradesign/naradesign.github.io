## HTML5 개요(outline) 알고리즘 이해.

HTML5 outline 알고리즘에 대하여 설명합니다. "outline"은 우리말로 "개요, 윤곽"에 해당하며 "간결하게 추려 낸 주요 내용"을 의미합니다. HTML5 마크업이 문서의 개요를 사용자에게 전달하기 위해 어떤 방법을 사용하는지 이해함으로써 낡은 브라우저와 최신 브라우저 그리고 화면 낭독기에 적절하게 대응할 수 있습니다.

개요를 이해하기 위한 키워드는 다음과 같고요.

* 헤딩
* 섹셔닝 루트
* 섹셔닝 콘텐츠
* 명시적/암시적 섹션
* 유효하지 않은 섹셔닝
* 어색한 섹셔닝

도출된 결론은 다음과 같습니다.

* 유연한 개요를 형성하려면 헤딩과 함께 섹셔닝 콘텐츠(`section`, `article`, `nav`, `aside`)를 쓰자.
* 하위 호환성을 확보하려면 헤딩의 수준을 결정할 때 개요 알고리즘에 의존하지 말자.
* 문서의 구조를 명확하게 하려면 최상위 수준의 헤딩은 하나만.

자세한 내용은 <a href="https://goo.gl/5yPmyW">HTML5 outline 발표자료(35 페이지)</a>를 참고하시기 바랍니다.

### 참고
* <a href="https://www.w3.org/TR/html5/sections.html#headings-and-sections">HTML5 Headings and sections</a>(W3C)
* <a href="https://gsnedders.html5.org/outliner/">HTML5 Outliner</a>(Online tool)
* <a href="https://chrome.google.com/webstore/detail/headingsmap/flbjommegcjonpdmenkdiocclhjacmbi?hl=ko">HeadingsMap</a>(Chrome extension)
* <a href="http://appletree.or.kr/blog/web-development/html/html5%EC%9D%98-%EC%83%88%EB%A1%9C%EC%9A%B4-%EB%AC%B8%EC%84%9C-outline-%EC%95%8C%EA%B3%A0%EB%A6%AC%EB%93%AC/">HTML5의 새로운 문서 Outline 알고리듬</a>(미남이의 이러쿵저러쿵)
* <a href="https://www.slideshare.net/NULINTS/2014-html5">시멘틱한 HTML 마크업 구조 설계, 어떻게 할까?</a>(윤원진)
