## WCAG 2.0 한글 번역.
이 문서는 WCAG 2.0 지침의 <a href="http://www.w3.org/TR/WCAG20/#guidelines">WCAG 2.0 Guidelines</a> 본문을 발췌하여 한국어로 번역한 것입니다. 번역에는 오류가 포함되어 있을 수 있습니다. 규범력을 갖는 정확한 정보를 원한다면 <a href="http://www.w3.org/TR/WCAG20/">WCAG 2.0 원문</a>을 참고하세요.

### 원칙 1: 인지 - 정보와 인터페이스 구성요소는 사용자가 인지할 수 있는 방법으로 표시해야 한다.
#### 지침 1.1 대체 텍스트: 텍스트 아닌 콘텐츠는 확대, 점자, 음성, 기호 또는 단순한 언어등 다른 양식을 원하는 사람들의 욕구에 대응할 수 있도록 대체 텍스트를 제공해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv.html">지침 이해 1.1</a>

1.1.1 텍스트 아닌 콘텐츠: 아래 나열된 상황을 제외하고 텍스트 아닌 콘텐츠는 그 목적에 상응하는 대체텍스트를 포함한 상태로 표시해야 한다.(수준 A)

* 콘트롤, 인풋: 만약 텍스트 아닌 콘텐츠가 콘트롤 또는 사용자 입력을 받는 것이라면 이것의 목적을 설명하는 이름이 있어야 한다.(콘트롤과 사용자 입력을 받는 콘텐츠를 위한 추가 요구사항은 지침 4.1을 참조.)
* 시간 기반의 미디어: 만약 텍스트 아닌 콘텐츠가 시간 기반의 미디어라면 텍스트 아닌 콘텐츠에는 최소한 동등한 설명의 텍스트 대체수단을 제공해야 한다.(미디어에 대한 추가 요구사항은 지침 1.2를 참조.)
* 시험: 만약 텍스트 아닌 콘텐츠가 텍스트로 표현하기 어려운 시험이나 연습 과정이라면 텍스트 아닌 콘텐츠에는 최소한 동등한 설명의 텍스트 대체수단을 제공해야 한다.
* 감각: 만약 텍스트 아닌 콘텐츠가 주로 특정 감각의 경험에 의존하도록 의도 되었다면 적어도 텍스트 아닌 콘텐츠에는 동등한 설명의 텍스트 대체수단을 제공해야 한다.
* CAPTCHA: 텍스트 아닌 콘텐츠의 목적이 컴퓨터가 아닌 사람에 의한 접근을 확인하기 위함이라면 텍스트 아닌 콘텐츠의 목적을 설명하고 동등한 설명의 텍스트 대체수단을 제공해야 한다. 그리고 CAPCHA의 대체 서식은 다양한 장애유형의 편의를 위해 다양한 유형의 감각으로 인지할 수 있도록 출력해야 한다.
* 장식, 양식, 보이지 않는: 만약 텍스트 아닌 콘텐츠가 순수하게 장식이거나 시각적 양식이거나 또는 사용자에게 표현되지 않을 때 보조 공학기술이 이것을 무시할 수 있도록 구현해야 한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-text-equiv-all">예제 1.1.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html">이해 1.1.1</a>

#### 지침 1.2 시간 기반 미디어: 시간 기반 미디어에 대한 대체 수단을 제공해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv.html">지침 이해 1.2</a>

1.2.1 음성과 영상(기록된): 음성 또는 영상이 문자를 위한 대체 미디어이고 그렇게 설명한 것이 아니라면 기록된 음성 또는 영상 미디어는 다음과 같이 동등한 대체 정보를 제공해야 한다.(수준 A)

* 기록된 음성: 시간 기반 미디어 대체 수단은 기록된 음성 콘텐츠와 동등한 정보로 제공해야 한다.
* 기록된 영상: 시간 기반 미디어 대체 수단 또는 음성 트랙은 기록된 영상 콘텐츠와 동등한 정보로 제공해야 한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-av-only-alt">예제 1.2.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-av-only-alt.html">이해 1.2.1</a>

1.2.2 자막(기록된): 미디어가 문자를 위한 대체 미디어이고 그렇게 설명한 것이 아니라면 기록된 음성 콘텐츠에 동기화된 자막을 제공해야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-captions">예제 1.2.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-captions.html">이해 1.2.2</a>

1.2.3 음성 해설 또는 미디어 대체(기록된): 미디어가 문자를 위한 대체 미디어이고 그렇게 설명한 것이 아니라면 실시간 미디어를 위한 대체 수단 또는 기록된 영상 콘텐츠의 음성 해설은 미디어에 동기화 상태로 제공해야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-audio-desc">예제 1.2.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-audio-desc.html">이해 1.2.3</a>

1.2.4 자막(실시간): 모든 실시간 음성 콘텐츠에는 미디어에 동기화된 자막을 제공해야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-real-time-captions">예제 1.2.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-real-time-captions.html">이해 1.2.4</a>

1.2.5 음성 해설(기록된): 기록된 모든 영상 콘텐츠에는 미디어에 동기화된 음성 해설을 제공해야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-audio-desc-only">예제 1.2.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-audio-desc-only.html">이해 1.2.5</a>

1.2.6 수화(기록된): 기록된 모든 음성 콘텐츠에는 미디어에 동기화된 수화 해설을 제공해야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-sign">예제 1.2.6</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-sign.html">이해 1.2.6</a>

1.2.7 추가된 음성 해설(기록된): 영상의 느낌을 전달하기 위한 목적으로 주요 음성을 정지하고 다른 음성 해설을 추가하는 경우 추가된 음성 해설은 기록된 모든 영상 콘텐츠에 동기화 해야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-extended-ad">예제 1.2.7</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-extended-ad.html">이해 1.2.7</a>

1.2.8 미디어 대체(기록된): 시간 기반의 기록된 모든 동기화 미디어와 기록된 영상 미디어에는 대체 수단을 제공해야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-text-doc">예제 1.2.8</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-text-doc.html">이해 1.2.8</a>

1.2.9 음성(실시간): 실시간 음성 콘텐츠에는 동등한 정보의 대체 수단을 제공해야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-media-equiv-live-audio-only">예제 1.2.9</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-live-audio-only.html">이해 1.2.9</a>

#### 지침 1.3 융통성: 콘텐츠는 정보 또는 구조의 손실 없이 다른 형태(예를 들면 더 단순하게)로 표시될 수 있도록 제작해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation.html">지침 이해 1.3</a>

1.3.1 정보와 관계: 화면에 전달되는 정보 및 구조와 관계는 텍스트로 변환하거나 기계적으로 인식할 수 있어야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-content-structure-separation-programmatic">예제 1.3.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html">이해 1.3.1</a>

1.3.2 의미있는 배열: 콘텐츠 배열 표시가 의미에 영향을 미치는 경우 바른 읽기 배열은 기계적으로도 인식 할 수 있어야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-content-structure-separation-sequence">예제 1.3.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-sequence.html">이해 1.3.2</a>

1.3.3 감각적인 특성: 콘텐츠의 이해와 조작을 위해 제공된 설명은 모양, 크기, 위치, 방향, 소리와 같은 구성요소의 감각적인 특성에 전적으로 의존하면 안된다.(수준 A)

참고: 색상에 관한 요구사항은 가이드라인 1.4를 참조할 것.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-content-structure-separation-understanding">예제 1.3.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-understanding.html">이해 1.3.3</a>

#### 지침 1.4 분별력: 배경으로부터 전경을 분리하는 것을 포함하여 콘텐츠는 사용자가 보고 듣기 쉽게 제작해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast.html">지침 이해 1.4</a>

1.4.1 색의 사용: 정보 전달, 행위 표시, 응답 메시지 또는 시각적 요소의 구별등을 시각적으로만 의미있는 방식으로 사용하면 안된다.(수준 A)

참고: 이것의 달성 기준은 특히 색깔의 인식에 관한 것이다. 다른 지각의 형태는 색상이나 그 외의 시각적 표현 코딩에 의한 프로그래밍 방식의 접근을 포함하여, 지침 1.3에서 다루고 있다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-without-color">예제 1.4.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html">이해 1.4.1</a>

1.4.2 음성 제어: 웹 페이지에서 3초 이상 자동으로 음성을 출력한다면 시스템 볼륨에 의존하지 않고도 음성을 정지하거나 음량을 제어할 수 있도록 해야 한다.(수준 A)

참고: 이 만족 기준을 충족하지 못하는 모든 콘텐츠는 페이지 전체를 이용하려는 사용자의 능력을 방해하기 때문에 웹 페이지의 모든 콘텐츠는(다른 만족 기준을 충족하더라도) 이 만족 기준을 충족해야 한다. 적합성 요구사항 5: 비인터페이스를 참고.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-dis-audio">예제 1.4.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-dis-audio.html">이해 1.4.2</a>

1.4.3 명암 대비(최소한의): 다음과 같은 경우를 제외하고 문자와 문자 이미지의 시각적인 표현은 최소한 4.5:1의 명암 대비를 부여해야 한다.(수준 AA)

* 큰 문자: <a href="http://www.w3.org/TR/2008/REC-WCAG20-20081211/#larger-scaledef">큰 비율</a>의 문자와 큰 비율의 이미지 문자는 적어도 3:1의 명암 비율을 갖는다.
* 기타: 순수하게 장식적이며 누구라도 알아볼 수 없는 문자와 이미지 문자 또는 사진과 같이 시각적으로 의미를 전달하는 피상적 사용자 인터페이스 구성요소는 명암비를 필요로 하지 않는다.
* 로고타입: 로고나 브랜드 이름에 포함된 문자는 최소 명암비를 필요로 하지 않는다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-contrast">예제 1.4.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html">이해 1.4.3</a>

1.4.4 문자 크기 변경: 자막과 이미지 문자를 제외하고 문자는 보조기술 없이도 콘텐츠를 잃거나 기능상실 없이 200% 이상 조절할 수 있어야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-scale">예제 1.4.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html">이해 1.4.4</a>

1.4.5 문자 이미지: 기술이 시각적 표현을 지원하더라도 다음과 같은 경우를 제외하면 정보는 이미지보다 문자로 전달해야 한다.(수준 AA)

* 사용자 정의 가능한: 문자 이미지를 사용자 요구에 따라 시각적으로 설정할 수 있다.
* 필수적인: 정보를 전달하는데 문자의 특별한 표현이 필수적이다.

참고: 로고타입(로고 또는 상표 이름 문자)은 필수적인 것으로 간주한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-text-presentation">예제 1.4.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-text-presentation.html">이해 1.4.5</a>

1.4.6 명암 대비(향상): 다음과 같은 경우를 제외하고 문자의 시각 표현과 문자 이미지는 적어도 7:1의 명암대비를 부여해야 한다.(수준 AAA)

* 큰 문자: <a href="http://www.w3.org/TR/2008/REC-WCAG20-20081211/#larger-scaledef">큰 비율</a>의 문자와 큰 비율의 이미지 문자는 적어도 4.5:1의 명암 비율을 갖는다.
* 기타: 순수하게 장식적이며 누구라도 알아볼 수 없는 문자와 이미지 문자 또는 사진과 같이 시각적으로 의미를 전달하는 피상적 사용자 인터페이스 구성요소는 명암비를 필요로 하지 않는다.
* 로고타입: 로고나 브랜드 이름에 포함된 문자는 최소 명암비를 필요로 하지 않는다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast7">예제 1.4.6</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast7.html">이해 1.4.6</a>

1.4.7 배경음 없음 또는 낮음: 음성 CAPTCHA(컴퓨터와 사람을 분간하기 위한 자동화 테스트)나 음성 표어(상투적인) 그리고 의미 전달을 의도하지 않은 노래와 랩 같은 음악 표현이 아닌 주로 전경으로 기록된 음성 언어 콘텐츠는 적어도 다음중 하나를 충족해야 한다.(수준 AAA)

* 배경 없음: 배경 음성을 포함하지 않는다.
* 끔: 배경 음성을 끌 수 있다.
* 20 데시벨: 배경 음성은 간헐적으로 발생하는 1~2초 정도의 음성을 제외하고 적어도 전경 음성 콘텐츠보다 20 데시벨 이상 낮아야 한다.

참고: "데시벨"의 정의에 따라서 이 요구를 충족하는 배경 음성은 전경 음성 콘텐츠보다 대략 4배 정도 조용할 것이다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-noaudio">예제 1.4.7</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-noaudio.html">이해 1.4.7</a>

1.4.8 시각적 표현: 문단의 시각적 표현을 위해 다음을 달성해야 한다.(수준 AAA)

1. 전경색과 배경색을 사용자가 선택할 수 있다.
1. 너비는 80자를 넘기지 않는다.(한중일 문자라면 40자)
1. 문단은 좌우 정렬(왼쪽과 오른쪽 여백을 동일하게 맞춤) 하지 않는다.
1. 줄 간격은 적어도 문단 속에서 문자의 절반 정도의 간격이고, 문단 간격은 적어도 줄 간격의 1.5배이다.
1. 문자는 보조 기술 및 풀 스크린창에서 가로 스크롤을 요구하지 않는 방법으로 한 줄을 읽을 수 있도록 200% 이상 확대 가능하다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-visual-presentation">예제 1.4.8</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html">이해 1.4.8</a>

1.4.9 문자 이미지(예외 없음): 문자 이미지는 순수한 장식이나 정보 전달을 위해 필수적인 경우에만 부분적으로 사용해야한다.(수준 AAA)

참고: 로고타입(로고 또는 상표 이름 문자)은 필수적인 것으로 간주한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-visual-audio-contrast-text-images">예제 1.4.9</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-text-images.html">이해 1.4.9</a>

### 원칙 2: 운용 - 사용자 인터페이스 구성요소와 탐색 기능은 조작이 가능해야 한다.
#### 지침 2.1 키보드 접근성: 키보드로 모든 기능이 가능하도록 제작해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/keyboard-operation.html">지침 이해 2.1</a>

2.1.1 키보드: 사용자의 움직임을 이용한 입력 기능이 필요하고 그것이 최후의 수단이 아니라면 콘텐츠의 모든 기능은 개인적인 타이핑 속도에 구애받지 않고 키보드 인터페이스를 이용하여 조작이 가능해야 한다.(수준 A)

참고 1: 예외사항은 입력 기술이 아니라 기본 기능과 관련되어 있다. 예를 들어 문자를 입력하기 위해 필기를 하는 경우 입력 기술(수기)은 경로에 의존하는 입력을 요구하지만 기본 기능(문자 입력)은 그렇지 않다.

참고 2: 이것은 키보드 조작에 마우스 입력이나 다른 입력 수단을 추가로 제공하는 것을 금지하거나 말리는 것을 의도하지 않는다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-keyboard-operation-keyboard-operable">예제 2.1.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/keyboard-operation-keyboard-operable.html">이해 2.1.1</a>

2.1.2 키보드 트랩 방지: 키보드 인터페이스를 이용하여 페이지 구성요소로 포커스 이동이 가능하다면 포커스는 키보드 인터페이스 만으로 구성요소로부터 떠날 수 있어야 한다. 방향키 또는 탭키나 다른 표준화된 탈출 수단 이외의 방법이 필요하다면 사용자에게 포커스 이동 방법을 알려주어야 한다.(수준 A)

참고: 이 만족 기준을 충족하지 못하는 모든 콘텐츠는 페이지 전체를 이용하려는 사용자의 능력을 방해하기 때문에 웹 페이지의 모든 콘텐츠는(다른 만족 기준을 충족하더라도) 이 만족 기준을 충족해야 한다. 적합성 요구사항 5: 비인터페이스를 참고.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-keyboard-operation-trapping">예제 2.1.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/keyboard-operation-trapping.html">이해 2.1.2</a>

2.1.3 키보드(예외 없음): 콘텐츠의 모든 기능은 개인적인 타이핑 속도에 구애받지 않고 키보드 인터페이스를 이용하여 조작이 가능해야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-keyboard-operation-all-funcs">예제 2.1.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/keyboard-operation-all-funcs.html">이해 2.1.3</a>

#### 지침 2.2 충분한 시간: 사용자가 콘텐츠를 읽고 사용할 수 있는 충분한 시간을 제공해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits.html">지침 이해 2.2</a>

2.2.1 시간 조절: 콘텐츠에 시간 제한이 설정되어 있다면 최소한 다음중 하나를 만족해야 한다:(수준 A)

* 끄기: 사용자는 시간 제한이 발생하기 전에 시간 제한을 끌 수 있어야 한다. 또는
* 조절: 사용자는 시간 제한이 발생하기 전에 적어도 기본 시간의 10배 이상으로 시간 제한을 조절할 수 있어야 한다. 또는
* 연장: 시간이 만료되기 전에 사용자에게 경고하고 단순한 조작(예를 들면 "스페이스 바를 누르세요")으로 적어도 20초 이상 시간 제한을 연장할 수 있어야 한다. 그리고 사용자는 최소한 10회 이상 시간 제한을 연장 할 수 있어야 한다. 또는
* 실시간 예외: 시간 제한이 요구되는 실시간 이벤트 분야(예를 들면 경매)와 시간 제한을 대체 할 수 없을 때 예외로 한다. 또는
* 필수적 예외: 시간 제한이 필수적이고 시간을 연장하는 것이 무효한 실행이 될 때 예외로 한다. 또는
* 20 시간 예외: 제한 시간이 20시간보다 길면 예외로 한다.

참고: 이 만족 기준은 시간 제한의 결과로써 콘텐츠나 문맥 속에서 예측하지 못한 변화 없이 과업을 완료할 수 있도록 사용자를 돕는다. 이 만족 기준은 만족 기준 3.2.1과 함께 고려해야 한다. 콘텐츠나 문맥의 어떤 제한도 사용자의 실행에 의한 결과여야 한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-time-limits-required-behaviors">예제 2.2.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html">이해 2.2.1</a>

2.2.2 일시 정지, 정지, 숨김: 움직이거나 깜빡이거나 스크롤링되거나 또는 자동으로 갱신되는 정보는 다음을 모두 만족해야 한다:(수준 A)

* 움직임, 깜빡임, 스크롤링:(1) 자동으로 시작되고(2) 5초 이상 지속되고(3) 다른 콘텐츠와 함께 제공 되는 움직이거나 깜빡이거나 또는 스크롤되는 모든 정보들은 필수적인 분야가 아니라면 일시 정지, 정지 또는 숨김 기능이 있어야 한다. 그리고
* 자동 갱신:(1) 자동으로 시작되고(2) 다른 콘텐츠와 함께 제공되는 모든 자동 갱신 정보들은 필수적인 분야가 아니라면 일시 정지, 정지 또는 숨김 또는 빈도 조절 기능이 있어야 한다.

참고 1: 요구사항들은 깜빡임이나 번쩍이는 콘텐츠와 관련되어 있다. 가이드라인 2.3을 참조할 것.

참고 2: 이 만족 기준을 충족하지 못하는 모든 콘텐츠는 페이지 전체를 이용하려는 사용자의 능력을 방해하기 때문에 웹 페이지의 모든 콘텐츠는(다른 만족 기준을 충족하더라도) 이 만족 기준을 충족해야 한다. 적합성 요구사항 5: 비인터페이스를 참고.

참고 3: 소프트웨어에 의해 주기적으로 갱신되거나 생성되거나 사용자 도구에의해 흐르거나 화면 표시의 정지와 재생 사이에 표시되는 콘텐츠에는 적용할 필요가 없다. 이것은 기술적으로 불가능 할 것이고 다양한 상황에서 오해의 소지가 있다.

참고 4: 단계를 미리 로드하거나 이와 유사한 상황으로 모든 사용자를 위한 상호작용 단계를 발생시킬 수 없는 분야의 애니메이션은 필수적인 상황으로 간주한다. 진행상황을 표시하지 않으면 사용자는 혼란스럽거나 콘텐츠가 멈추었거나 깨졌다고 생각한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-time-limits-pause">예제 2.2.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-pause.html">이해 2.2.2</a>

2.2.3 타이밍 금지: 상호작용 없는 동기화된 미디어와 실시간 이벤트를 제외하고 타이밍은 콘텐츠가 제시하는 활동이나 이벤트의 필수 요소가 아니다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-time-limits-no-exceptions">예제 2.2.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-no-exceptions.html">이해 2.2.3</a>

2.2.4 중단: 비상사태에 해당하는 경우를 제외하고 중단은 연기되거나 사용자가 억제할 수 있어야 한다. (수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-time-limits-postponed">예제 2.2.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-postponed.html">이해 2.2.4</a>

2.2.5 재 인증: 인증된 세션이 만료될 때 사용자는 재 인증 후 데이터 손실 없이 계속 활동할 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-time-limits-server-timeout">예제 2.2.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-server-timeout.html">이해 2.2.5</a>

#### 지침 2.3 발작: 발작을 일으키는 것으로 알려진 콘텐츠를 디자인 하면 안된다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/seizure.html">지침 이해 2.3</a>

2.3.1 3회의 번쩍임 또는 임계치 이하: 웹 페이지는 1초에 3회 이상 번쩍이는 어떤것도 포함해서는 안된다. 또는 번쩍임은 일반적인 것이어야 하고 붉은 번쩍임은 임계치 아래 있어야 한다.(수준 A)

참고: 이 성공 기준을 만족하지 못하는 콘텐츠는 페이지와 콘텐츠를 이용하려는 사용자의 능력을 방해하기 때문에(다른 성공 기준을 만족하는지 아닌지 여부를 떠나) 반드시 이 성공 기준을 달성해야 한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-seizure-does-not-violate">예제 2.3.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/seizure-does-not-violate.html">이해 2.3.1</a>

2.3.2 3회의 번쩍임: 웹 페이지는 1초에 3회 이상 번쩍이는 어떤것도 포함해서는 안된다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-seizure-three-times">예제 2.3.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/seizure-three-times.html">이해 2.3.2</a>

#### 지침 2.4 탐색 가능성: 탐색하거나 콘텐츠를 찾거나 위치를 판단할 수 있도록 도울 방법을 제공해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms.html">지침 이해 2.4</a>

2.4.1 블럭 우회: 여러 웹 페이지에서 반복되는 콘텐츠 블럭을 우회할 수 있어야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-skip">예제 2.4.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html">이해 2.4.1</a>

2.4.2 페이지 제목 달기: 웹 페이지는 주제나 목적을 설명하는 제목이 있어야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-title">예제 2.4.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-title.html">이해 2.4.2</a>

2.4.3 포커스 순서: 웹 페이지가 순차적으로 탐색 되고 탐색 순서가 의미 또는 조작에 영향을 미치는 경우 포커스를 받을 수 있는 콤포넌트는 의미와 조작 순서에 맞게 포커스를 받아야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-focus-order">예제 2.4.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-order.html">이해 2.4.3</a>

2.4.4 링크 목적(문맥상): 사용자에 의해 다양하게 해석될 수 있는 링크 목적인 경우를 제외하고 각각의 링크는 독립적인 링크 텍스트 또는 링크 텍스트와 함께 제공된 프로그램 방식의 문맥에 의해서 그 목적을 알 수 있어야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-refs">예제 2.4.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-refs.html">이해 2.4.4</a>

2.4.5 다양한 방법: 웹 페이지가 어떤 과정의 결과 이거나 단계인 경우를 제외하고 웹 페이지 셋 안에서 하나의 웹 페이지로 이동하기 위한 다양한 방법을 제공해야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-mult-loc">예제 2.4.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-mult-loc.html">이해 2.4.5</a>

2.4.6 제목과 레이블: 제목과 레이블은 주제 또는 목적을 설명해야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-descriptive">예제 2.4.6</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html">이해 2.4.6</a>

2.4.7 보이는 포커스: 키보드 조작 가능한 모든 사용자 인터페이스는 키보드 포커스 표시가 보이는 방식으로 제공해야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-focus-visible">예제 2.4.7</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-visible.html">이해 2.4.7</a>

2.4.8 위치: 웹 페이지 셋 안에서 사용자의 위치에 관한 정보를 알 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-location">예제 2.4.8</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-location.html">이해 2.4.8</a>

2.4.9 링크 목적(링크만): 사용자에 의해 다양하게 해석될 수 있는 링크 목적인 경우를 제외하고 각각의 링크는 독립적인 링크 텍스트로부터 메커니즘에 의해 목적을 식별할 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-link">예제 2.4.9</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-link.html">이해 2.4.9</a>

2.4.10 섹션 제목: 섹션 제목은 콘텐츠를 체계화한 것이어야 한다.(수준 AAA)

참고 1: "제목"은 일반적인 의미로써 타이틀을 포함하여 다른 콘텐츠 유형에 대한 제목을 추가하는 또 다른 방법으로 사용된다.

참고 2: 이 만족 기준은 사용자 인터페이스 콤포넌트가 아닌 글을 포함한 섹션을 다루고 있다. 사용자 인터페이스 콤포넌트는 성공 기준 4.1.2 에서 다룬다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-navigation-mechanisms-headings">예제 2.4.10</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-headings.html">이해 2.4.10</a>

### 원칙 3: 이해 - 정보와 사용자 인터페이스 조작은 이해할 수 있어야 한다.
#### 지침 3.1 읽을 수 있는: 콘텐츠는 읽고 이해할 수 있도록 제작해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning.html">지침 이해 3.1</a>

3.1.1 페이지 언어: 모든 웹 페이지의 기본 휴먼 랭귀지는 기계적으로 판단할 수 있어야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-meaning-doc-lang-id">예제 3.1.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-doc-lang-id.html">이해 3.1.1</a>

3.1.2 부분 언어: 고유한 이름, 기술 용어, 알 수 없는 언어, 방언이 섞인 단어 또는 구를 제외하고 휴먼 랭귀지는 콘텐츠의 모든 구 또는 절에서 기계적으로 판단할 수 있어야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-meaning-other-lang-id">예제 3.1.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-other-lang-id.html">이해 3.1.2</a>

3.1.3 낯선 단어: 관용구와 전문용어를 포함하여 단어나 낯선 구절 또는 특이한 양식의 명확한 의미를 기계적으로 판단할 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-meaning-idioms">예제 3.1.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-idioms.html">이해 3.1.3</a>

3.1.4 약어: 확장된 양식이나 약어의 의미는 기계적으로 판단할 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-meaning-located">예제 3.1.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-located.html">이해 3.1.4</a>

3.1.5 독서 수준: 적절한 이름과 제목을 제거한 글이 중등교육 수준보다 높은 읽기 능력을 필요로 할 때에는 콘텐츠를 보충하거나 또는 중등교육 수준의 읽기 버전을 이용할 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-meaning-supplements">예제 3.1.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-supplements.html">이해 3.1.5</a>

3.1.6 발음: 문맥 속에서 발음을 알 수 없는 모호하지만 의미있는 단어의 명확한 발음을 기계적으로 판단할 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-meaning-pronunciation">예제 3.1.6</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-pronunciation.html">이해 3.1.6</a>

#### 지침 3.2 예측 가능성: 웹 페이지의 출현과 조작은 예측할 수 있도록 제작해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior.html">지침 이해 3.2</a>

3.2.1 포커스: 어떤 콤포넌트라도 포커스를 받았을 때 문맥의 변화가 발생하면 안된다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-consistent-behavior-receive-focus">예제 3.2.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-receive-focus.html">이해 3.2.1</a>

3.2.2 인풋: 사용자가 콤포넌트를 실행하기 전까지 사용자 인터페이스 콤포넌트 설정은 알리지 않은 어떤 문맥의 변화도 자동으로 발생해서는 안된다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-consistent-behavior-unpredictable-change">예제 3.2.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-unpredictable-change.html">이해 3.2.2</a>

3.2.3 일관된 탐색: 사용자가 변화를 주기 전까지 하나의 웹 페이지 셋에 포함된 여러 페이지의 반복 탐색 장치는 일관된 순서를 지녀야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-consistent-behavior-consistent-locations">예제 3.2.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-consistent-locations.html">이해 3.2.3</a>

3.2.4 일관된 식별: 웹 페이지 셋에서 같은 기능을 가진 구성요소들은 일관성 있게 식별되어야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-consistent-behavior-consistent-functionality">예제 3.2.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-consistent-functionality.html">이해 3.2.4</a>

3.2.5 요청에 의한 변화: 문맥의 변경은 오직 사용자의 요청에 의해서만 발생해야 한다. 그렇지 않으면 변경을 끌 수 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-consistent-behavior-no-extreme-changes-context">예제 3.2.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-no-extreme-changes-context.html">이해 3.2.5</a>

#### 지침 3.3 입력 지원: 실수를 예방하고 정정할 수 있도록 사용자를 도와야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error.html">지침 이해 3.3</a>

3.3.1 오류 식별: 만약 입력 오류가 자동으로 감지되면 오류 항목을 식별하고 사용자에게 문자로 알려야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-minimize-error-identified">예제 3.3.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-identified.html">이해 3.3.1</a>

3.3.2 레이블 또는 설명: 콘텐츠가 사용자 입력을 요구할 때에는 레이블 또는 설명을 제공해야 한다.(수준 A)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-minimize-error-cues">예제 3.3.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-cues.html">이해 3.3.2</a>

3.3.3 오류 의견: 인풋 오류가 자동으로 감지되고 정정하기 위한 의견이 있을 때 콘텐츠의 목적이나 보안을 위태롭게 하지 않는 이상 사용자에게 의견을 제공해야 한다.(수준 AA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-minimize-error-suggestions">예제 3.3.3</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-suggestions.html">이해 3.3.3</a>

3.3.4 오류 예방(법, 금융, 자료): 법적인 책임이 있거나 금융 거래를 하면서 자료 저장 시스템에서 사용자의 자료를 고치거나 지울 때 또는 사용자 전송에 대한 응답을 테스트 할 때 웹 페이지는 적어도 다음중 하나가 참이어야 한다:(수준 AA)

1. 원상회복: 제출된 내용은 원래 상태로 되돌릴 수 있어야 한다.
1. 점검: 사용자가 입력한 자료는 입력 오류를 확인해야 하고 그것을 교정하기 위한 기회를 제공해야 한다.
1. 확인: 전송을 완료하기 전에 검토, 확인, 교정할 수 있어야 한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-minimize-error-reversible">예제 3.3.4</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-reversible.html">이해 3.3.4</a>

3.3.5 도움말: 문맥에 대한 섬세한 도움말이 있어야 한다.(수준 AAA)

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-minimize-error-context-help">예제 3.3.5</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-context-help.html">이해 3.3.5</a>

3.3.6 오류 예방(모든): 사용자 정보 전송을 요구하는 웹 페이지는 적어도 다음중 하나가 참이어야 한다:(수준 AAA)

1. 원상회복: 제출된 내용은 원래 상태로 되돌릴 수 있어야 한다.
1. 점검: 사용자가 입력한 자료는 입력 오류를 확인해야 하고 그것을 교정하기 위한 기회를 제공해야 한다.
1. 확인: 전송을 완료하기 전에 검토, 확인, 교정할 수 있어야 한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-minimize-error-reversible-all">예제 3.3.6</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-reversible-all.html">이해 3.3.6</a>

### 원칙 4: 견고 - 콘텐츠는 보조 기술을 포함한 다양한 사용자 응용 프로그램에 의하여 해석이 가능하도록 충분히 견고해야 한다.
#### 지침 4.1 호환성: 보조 기술을 포함하여 현재와 미래의 사용자 응용 프로그램 호환성을 극대화 해야 한다.
<a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat.html">지침 이해 4.1</a>

4.1.1 문법 해석: 명세가 허락하지 않는 이상 마크업 언어로 콘텐츠를 구현할 때 요소는 시작과 종료 태그를 가져야 하고 명세에 따라 중첩해야 하며 같은 속성을 반복하지 않아야 하고 모든 ID는 유일해야 한다.(수준 A)

참고: 닫는 꺽쇠 또는 짝이 맞지 않는 속성 값 따옴표 처럼 중요한 문자가 빠진 시작과 종료 태그를 일컬음.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-ensure-compat-parses">예제 4.1.1</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-parses.html">이해 4.1.1</a>

4.1.2 이름, 역할, 값: 이름과 역할은 모든 사용자 인터페이스 콤포넌트(스크립트가 생성하는 폼 요소와 링크등의 구성요소를 모두 포함)를 위하여 프로그래밍 방식으로 결정되어야 한다. 상태, 속성, 값은 사용자에 의해 프로그래밍 방식으로 결정할 수 있어야 한다. 그리고 이 항목들의 변화에 대한 알림은 보조 기술을 포함하여 사용자 에이전트에서 이용할 수 있어야 한다.(수준 A)

참고: 이 달성 기준은 주로 고유한 인터페이스 구성요소를 스크립팅하거나 개발하는 웹 저작자를 위한 것이다. 예를 들면 표준 HTML 콘트롤은 명세에 따라 사용할 때 이미 달성 기준을 만족한다.

<a href="http://www.w3.org/WAI/WCAG20/quickref/#qr-ensure-compat-rsv">예제 4.1.2</a>, <a href="http://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html">이해 4.1.2</a>

### 참조
* <a href="http://www.w3.org/TR/WAI-WEBCONTENT/">WCAG 1.0 <sup>ENG</sup></a>
* <a href="http://gregshin.pe.kr/wcag/wai-pageauth.html">WCAG 1.0 <sup>KOR</sup></a>
* <a href="http://www.w3.org/TR/WCAG20/">WCAG 2.0 <sup>ENG</sup></a><sup></sup>
* <a href="http://www.w3c.or.kr/Translation/WCAG20/">WCAG 2.0 <sup>KOR</sup></a>
