## CSS flex: Webkit, Android 2.1~4.3, IE 10 문제 해결.

### Webkit 이슈.
웹킷 계열 브라우저에서는 폼 콘트롤 요소가 플렉스 아이템이 되지 않기 때문에 플렉스 흐름에 참여하지 않습니다. 폼 콘트롤 요소가 플렉스 아이템이 되어 플렉스 흐름에 참여하도록 하려면 `-webkit-appearance:none;` 처리해야 합니다. 이 문제는 Android 뿐만 아니라 웹킷 계열 브라우저(Chrome, Safari) 공통의 문제입니다.

### 안드로이드 2.1~4.3 이슈.
안드로이드 2.1~4.3 브라우저는 2009년 플렉스 명세에 `-webkit-` 접두사를 붙여야 지원할 수 있습니다. 지원하는 속성 수가 최신 표준에 비해 적고 속성 전체 목록을 확인해 보면 단축 속성은 지원하지 않습니다. 안드로이드 4.4 이후 버전부터는 최신 표준 명세를 지원하고 있으며 제조사 접두어는 필요 없습니다.

### IE 10 이슈.
IE 9 이하 버전 브라우저는 플렉스 명세를 지원하지 않습니다. IE 10 브라우저는 2012년의 플렉스 명세를 지원합니다. IE 10 브라우저를 지원하려면 2012년 플렉스 속성에 `-ms-` 제조사 접두어를 붙여야 합니다.

### 안드로이드 2.1~4.3 + IE 10 지원하기.
아래는 안드로이드 2.1~4.3 브라우저와 IE 10 브라우저에 모두 대응하기 위한 코드를 정리해 둔 것입니다. 안드로이드 2.1~4.3 브라우저와 IE 10 브라우저를 모두 지원해야 하는 상황을 가정하고 예제 코드를 만들었습니다.

안드로이드 2.1~4.3 브라우저와 IE 10 브라우저가 공통으로 지원하지 않는 속성은 `flex-flow`, `justify-content: space-around`, `align-self`, `align-content` 입니다.

안드로이드 2.1~4.3 브라우저는 표준 명세의 `flex-shrink`, `flex-basis`, `flex` 속성을 지원하지 않습니다. `flex-wrap`, `order`에 대응하는 속성은 명세에는 존재하지만 지원하지 않습니다.

IE 10 브라우저는 표준 명세의 `flex-grow`, `flex-shrink`, `flex-basis` 속성을 지원하지 않고 단축 속성인 `-ms-flex: 0 1 auto;` 속성과 값을 지원합니다.

```
{// 플렉스 컨테이너에 적용. 플렉스 컨테이너 생성.
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

{ // 플렉스 아이템에 적용. 확장 지수 설정.
  -webkit-box-flex: 1;
  -ms-flex: 1;
  flex-grow: 1;
}

{ // 플렉스 컨테이너에 적용. 주축 row 설정.
  -webkit-box-orient: horizontal;
  -ms-flex-direction: row;
  flex-direction: row;
}

{ // 플렉스 컨테이너에 적용. 주축 column 설정.
  -webkit-box-orient: vertical;
  -ms-flex-direction: column;
  flex-direction: column;
}

{ // 플렉스 컨테이너에 적용. 주축 row-reverse 설정.
  -webkit-box-orient: horizontal;
  -webkit-box-direction: reverse;
  -ms-flex-direction: row-reverse;
  flex-direction: row-reverse;
}

{ // 플렉스 컨테이너에 적용. 주축 column-reverse 설정.
  -webkit-box-orient: vertical;
  -webkit-box-direction: reverse;
  -ms-flex-direction: column-reverse;
  flex-direction: column-reverse;
}

{ // 플렉스 컨테이너에 적용. 감싸기(줄바꿈) 금지 설정.
  -webkit-box-lines: single;
  -ms-flex-wrap: nowrap;
  flex-wrap: nowrap;
}

{ // 플렉스 컨테이너에 적용. 감싸기(줄바꿈) 설정. 확인 결과 안드로이드 2.1~4.3 아래 속성 지원 안 함.
  <del>-webkit-box-lines: multiple;</del>
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
}

{ // 플렉스 아이템에 적용. 아이템 정렬 순서 설정. 확인 결과 안드로이드 2.1~4.3 아래 속성 지원 안 함.
  <del>-webkit-box-ordinal-group: 1;</del>
  -ms-flex-order: 1;
  order: 1;
}

{ // 플렉스 컨테이너에 적용. 아이템 주축 start 정렬.
  -webkit-box-pack: start;
  -ms-flex-pack: start;
  justify-content: flex-start;
}

{ // 플렉스 컨테이너에 적용. 아이템 주축 end 정렬.
  -webkit-box-pack: end;
  -ms-flex-pack: end;
  justify-content: flex-end;
}

{ // 플렉스 컨테이너에 적용. 아이템 주축 center 정렬.
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}

{ // 플렉스 컨테이너에 적용. 아이템 주축 space-between 정렬.
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}

{ // 플렉스 컨테이너에 적용. 아이템 교차축 start 정렬.
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
}

{ // 플렉스 컨테이너에 적용. 아이템 교차축 end 정렬.
  -webkit-box-align: end;
  -ms-flex-align: end;
  align-items: flex-end;
}

{ // 플렉스 컨테이너에 적용. 아이템 교차축 center 정렬.
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

{ // 플렉스 컨테이너에 적용. 아이템 교차축 stretch 정렬.
  -webkit-box-align: stretch;
  -ms-flex-align: stretch;
  align-items: stretch;
}

{ // 플렉스 컨테이너에 적용. 아이템 교차축 baseline 정렬.
  -webkit-box-align: baseline;
  -ms-flex-align: baseline;
  align-items: baseline;
}
```

### 참고
* <a href="https://www.w3.org/TR/2009/WD-css3-flexbox-20090723/">2009년 플렉스 명세</a>
* <a href="https://www.w3.org/TR/2012/WD-css3-flexbox-20120322/">2012년 플렉스 명세</a>
* <a href="https://msdn.microsoft.com/ko-kr/library/hh673531(v=vs.85).aspx">IE 10 플렉스 설명서</a>
* <a href="http://caniuse.com/#feat=flexbox">http://caniuse.com/#feat=flexbox</a>
* <a href="https://github.com/philipwalton/flexbugs">https://github.com/philipwalton/flexbugs</a>

<div id="fb-root"></div>
<script async defer crossorigin="anonymous" src="https://connect.facebook.net/ko_KR/sdk.js#xfbml=1&version=v3.3"></script>
<div class="fb-comments" data-href="https://naradesign.github.io/article/flex-browser-compatibility.html" data-numposts="10" data-width="100%"></div>
