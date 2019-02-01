## CSS3 미디어쿼리(@media) 규칙 이해.

출력 장치의 여러 특징 가운데 일부를 참조하여 CSS 코드를 분기 처리함으로써 하나의 HTML 소스가 여러가지 뷰를 갖도록 구현할 수 있는 명세이다. 일반적으로 뷰포트 해상도에 따라 CSS 코드를 분기한다.

### CSS 코드 내부에서 분기하는 방법
CSS 코드 내부에서 사용하는 미디어 쿼리의 기본적인 문법 예는 다음과 같다. 일반적으로 권장하고 널리 쓰이는 방식이다.

```
@media only all and (조건문) {실행문}
```

* **@media**: 미디어 쿼리가 시작됨을 선언한다. `@media`, `only`, `all`, `and`, `(조건문)` 사이에 포함되어 있는 공백은 필수적이다.
* **only**: `only` 키워드는 미디어 쿼리를 지원하는 사용자 에이전트만 미디어 쿼리 구문을 해석하라는 명령이며 생략 가능하다. 생략했을 때 기본 값은 `only`로 처리 된다. 생략해도 무방하므로 이 키워드는 일반적으로 작성하지 않는다. 이 자리에는 `not` 키워드를 사용할 수 있는데 뒤에 오는 모든 조건을 부정하는 연산을 한다.
* **all**: `all` 키워드는 미디어 쿼리를 해석해야 할 대상 미디어를 선언한 것이다. `all` 이면 모든 미디어가 이 구문을 해석해야 한다. `all` 키워드 대신 `screen` 또는 `print`와 같은 특정 미디어를 구체적으로 언급할 수도 있다. `all` 키워드는 생략 가능하고 생략했을 때 기본 값은 `all` 으로 처리된다. 이 밖에도 다양한 미디어 타입(`all`, `aural`, `braille`, `embossed`, `handheld`, `print`, `projection`, `screen`, `speech`, `tty`, `tv`)이 있다. `all`, `screen`, `print`를 가장 널리 쓴다.
* **and**: `and` 키워드는 논리적으로 'AND' 연산을 수행하여 앞과 뒤의 조건을 모두 만족해야 한다는 것을 의미한다. 조건이 유일하거나 또는 `only`, `all`과 같은 선행 키워드가 생략되면 `and` 키워드는 사용하지 말아야 한다. `and` 대신 콤마 `,` 기호를 사용하면 'OR' 연산을 수행한다. 'OR' 연산은 나열된 조건 중에서 하나만 참이어도 `{실행문}`을 해석한다.
* **(조건문)**: 브라우저는 조건문이 참일때`{실행문}`을 처리하고 거짓일 때 무시한다. 조건문은 두 가지 이상 등장할 수 있다. 둘 이상의 조건문은 `and` 키워드 또는 콤마 `,` 기호로 연결해야 한다.
* **{실행문}**: 일반적인 CSS 코드를 이 괄호 안에 작성한다. 브라우저는 `(조건문)`이 참일때 실행문 안쪽에 있는 CSS 코드를 해석한다.

### CSS 코드 외부에서 분기하는 방법
조건문에 따라 별도의 외부 CSS 파일을 참조하여 분기하는 방법은 다음과 같다. 이 방식은 성능 최적화 측면에서 권장하지 않는다.

```
<link rel="stylesheet" type="text/css" media="all and (조건A)" href="A.css">
<link rel="stylesheet" type="text/css" media="all and (조건B)" href="B.css">
```

데스크탑 브라우저 사용자가 언제든 조건을 변경(예를 들면 창 크기를 조절해서 해상도를 바꿈)할 수 있기 때문에 웹 브라우저는 조건에 관계 없이 A.css 파일과 B.css 파일을 항상 요청한다. HTTP 요청을 불필요하게 두 번 발생시켜 이 페이지를 처음 로딩하는 사용자에게는 성능 저하의 원인이 된다. CSS 파일은 하나로 병합하고 CSS 코드 내부에서 조건 분기하는 방식을 권장한다.

### 미디어 쿼리 코드 템플릿
아래 코드는 모든 해상도를 커버하기 위한 미디어 쿼리 코드 템플릿이다. All, Mobile, Tablet, Desktop 으로 기기별 대응 코드를 분류 했지만 Liquid 레이아웃 기법을 사용하면 사실상 모든 해상도를 커버할 수 있다.

```
@charset "utf-8";

/* All Device */
모든 해상도를 위한 공통 코드를 작성한다. 모든 해상도에서 이 코드가 실행됨.

/* Mobile Device */
768px 미만 해상도의 모바일 기기를 위한 코드를 작성한다. 모든 해상도에서 이 코드가 실행됨. 미디어 쿼리를 지원하지 않는 모바일 기기를 위해 미디어 쿼리 구문을 사용하지 않는다.

/* Tablet &amp; Desktop Device */
@media all and (min-width:768px) {
    사용자 해상도가 768px 이상일 때 이 코드가 실행됨. 테블릿과 데스크톱의 공통 코드를 작성한다.
}

/* Tablet Device */
@media all and (min-width:768px) and (max-width:1024px) {
    사용자 해상도가 768px 이상이고 1024px 이하일 때 이 코드가 실행됨. 아이패드 또는 비교적 작은 해상도의 랩탑이나 데스크톱에 대응하는 코드를 작성한다.
}

/* Desktop Device */
@media all and (min-width:1025px) {
    사용자 해상도가 1025px 이상일 때 이 코드가 실행됨. 1025px 이상의 랩탑 또는 데스크톱에 대응하는 코드를 작성한다.
}
```

### 조건문이 될 수 있는 특징들
#### width / height
뷰포트의 너비와 높이. 뷰포트의 크기는 HTML body 콘텐츠를 표시하는 영역으로 실제 스크린의 크기와는 다르다. 반응형 웹 구현시 가장 일반적으로 사용하는 조건이 된다.

* Value: &lt;length&gt;
* Applies to: visual and tactile media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (min-width:768px) and (max-width:1024px) { … } // 뷰포트 너비가 768px 이상 '그리고' 1024px 이하이면 실행
@media all and (width:768px), (width:1024px) { … } // 뷰포트 너비가 768px 이거나 '또는' 1024px 이면 실행
@media not all and (min-width:768px) and (max-width:1024px) { … } // 뷰포트 너비가 768px 이상 '그리고' 1024px 이하가 '아니면' 실행
```

#### device-width / device-height
스크린의 너비와 높이. 스크린은 출력 장치가 픽셀을 표시할 수 있는 모든 영역으로 일반적으로 HTML `body` 콘텐츠를 표시하는 뷰포트 보다 크다.

* Value: &lt;length&gt;
* Applies to: visual and tactile media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (device-width:320px) and (device-height:480px) { … } // 스크린 너비가 320px '그리고' 높이가 480px 이면 실행
@media all and (min-device-width:320px) and (min-device-height:480px) { … } // 스크린 너비가 최소 320px 이상 '그리고' 높이가 최소 480px 이상이면 실행
```

#### orientation
뷰포트의 너비와 높이 비율을 이용하여 세로 모드인지 가로 모드인지를 판단한다.

* Value: portrait | landscape
* Applies to: bitmap media types
* Accepts min/max prefixes: no

#### Example:
```
@media all and (orientation:portrait) { … } // 세로 모드. 뷰포트의 높이가 너비에 비해 상대적으로 크면 실행
@media all and (orientation:landscape) { … } // 가로 모드. 뷰포트의 너비가 높이에 비해 상대적으로 크면 실행
```

#### aspect-ratio
뷰포트의 너비와 높이에 대한 비율. '너비/높이' 순으로 조건을 작성한다. `min/max` 접두사를 사용하면 너비 값의 최소/최대 비율을 정할 수 있다.

* Value: &lt;ratio&gt;
* Applies to: bitmat media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (aspect-ratio:5/4) { … } // 뷰포트 너비가 5, 높이가 4 비율이면 실행
@media all and (min-aspect-ratio:5/4) { … } // 뷰포트 너비가 5/4 비율 이상이면 실행
@media all and (max-aspect-ratio:5/4) { … } // 뷰포트 너비가 5/4 비율 이하면 실행
```

#### device-aspect-ratio
스크린의 너비와 높이에 대한 비율. '너비/높이' 순으로 조건을 작성한다. `min/max` 접두사를 사용하면 너비 값의 최소/대최 비율을 정할 수 있다.

* Value: &lt;ratio&gt;
* Applies to: bitmap media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (device-aspect-ratio:5/4) { … } // 스크린 너비가 5, 높이가 4 비율이면 실행
@media all and (min-device-aspect-ratio:5/4) { … } // 스크린 너비가 5/4 비율 이상이면 실행
@media all and (max-device-aspect-ratio:5/4) { … } // 스크린 너비가 5/4 비율 이하면 실행
```

#### color
출력 장치의 색상에 대한 비트 수. 출력 장치가 컬러가 아닌 경우 `0`의 값에 대응한다.

* Value: &lt;integer&gt;
* Applies to: visual media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (color) { … } // 출력 장치가 컬러를 지원하면 실행
@media all and (color:0) { … } // 출력 장치가 컬러가 아니면 실행
@media all and (color:8) { … } // 출력 장치가 8비트 색상이면 실행
@media all and (min-color:8) { … } // 출력 장치가 8비트 이상 색상이면 실행
@media all and (max-color:8) { … } // 출력 장치가 8비트 이하 색상이면 실행
```

#### color-index
출력 장치가 색상 색인 테이블을 사용하는 경우 표현할 수 있는 색의 수. 출력 장치가 색상 색인 테이블을 사용하지 않으면 `0`의 값에 대응한다. 현재 제대로 지원하는 브라우저가 없다.

* Value: &lt;integer&gt;
* Applies to: visual media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (color-index) { … } // 출력 장치가 색상 색인 테이블을 사용하면 실행
@media all and (color-index:0) { … } // 출력 장치가 색상 색인 테이블을 사용하지 않으면 실행
@media all and (color-index:256) { … } // 출력 장치가 256 색을 지원하면 실행
@media all and (min-color-index:256) { … } // 출력 장치가 256 이상 색을 지원하면 실행
@media all and (max-color-index:256) { … } // 출력 장치가 256 이하 색을 지원하면 실행
```

#### monochrome
출력 장치가 흑백인 경우 픽셀당 비트 수. 출력 장치가 흑백이 아니라면 `0`의 값에 대응한다.

* Value: &lt;integer&gt;
* Applies to: visual media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (monochrome) { … } // 출력 장치가 흑백이면 실행
@media all and (monochrome:0) { … } // 출력 장치가 흑백이 아니면 실행
@media all and (min-monochrome:2) { … } // 출력 장치가 흑백이고 2비트 이상이면 실행
@media all and (max-monochrome:2) { … } // 출력 장치가 흑백이고 2비트 이하이면 실행
```

#### resolution
출력 장치의 해상력에 대응한다. `min/max` 접두사는 사각형 아닌 픽셀(인쇄 장치)에도 대응하지만 접두사 없는 `resolution` 조건은 사각형 픽셀에만 대응한다. 조건의 값으로 dpi와 dpcm 단위를 사용할 수 있다.

* Value: &lt;resolution&gt;
* Applies to: bitmap media types
* Accepts min/max prefixes: yes

#### Example:
```
@media all and (resolution:96dpi) { … } // 1인치당 96개의 사각형 화소를 제공하면 실행
@media all and (min-resolution:96dpi) { … } // 1인치당 96개 이상의 화소를 제공하면 실행
@media all and (max-resolution:96dpi) { … } // 1인치당 96개 이하의 화소를 제공하면 실행
```

#### scan
TV의 스캔 방식에 따라 대응한다. `progressive` 값은 초당 60회 수준의 고화질 스캔에 대응하고 `interlace` 값은 초당 30회 수준의 일반 스캔에 대응한다. 대부분의 HDTV는 `progressive`와 `interlace` 방식을 모두 지원하고 있다.

* Value: progressive | interlace
* Applies to: "tv" media types
* Accepts min/max prefixes: no

#### Example:
```
@media tv and (scan:progressive) { … } // 초당 60회 수준의 고화질 스캔 방식 TV에 대응한다
@media tv and (scan:interlace) { … } // 초당 30회 수준의 일반 스캔 방식 TV에 대응한다
```

#### grid
출력 장치가 그리드 방식이면 대응한다. 그리드 방식은 타자기와 같이 고정된 글꼴만 사용하는 장치이다. 통상 출력 장치는 비트맵이 아니면 그리드 방식이다. 값은 정수 `0`과 `1` 뿐이고 `0`의 값은 비트맵 방식에 대응한다.

* Value: &lt;integer&gt; 0 | 1
* Applies to: visual and tactile media types
* Accepts min/max prefixes: no

#### Example:
```
@media all and (grid) { … } // 출력 장치가 그리드 방식이면 실행
@media all and (grid:0) { … } // 출력 장치가 그리드 방식이 아니면 실행
@media all and (grid:1) { … } // 출력 장치가 그리드 방식이면 실행
```
