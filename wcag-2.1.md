## WCAG 2.1 Working Draft 새로운 성공 기준 리뷰.

W3C 에서 2008년 12월 11일 <a href="https://www.w3.org/TR/WCAG20/">WCAG 2.0</a> 버전을 권고(Recommendation) 발표한지 약 8년이 넘었는데요. 최근(2017년 2월 28일) <a href="https://www.w3.org/TR/WCAG21/">WCAG 2.1</a> 버전 초안(Working Draft)을 공개했습니다. 이번에 새로 발표한 초안은 WCAG 2.0 모든 항목을 계승한 상태에서 새로운 지침을 추가한 것입니다. 현재로써는 초안이기 때문에 확정된 항목들은 아니지만 지금까지 합의된 새로운 지침들을 원문과 함께 번역해 두었으니 참고해 주세요. WCAG 2.0 항목과 중복이 되는 부분도 있어 보이는데요. 나중에 조정할 예정이랍니다. 오역은 댓글 부탁드려요.

### 2017년 7월 현재&nbsp;새로운 성공 기준(9개)
#### 1.4.10 Zoom content(Level AA)
> Content can be zoomed to an equivalent width of 320 CSS pixels without loss of content or functionality, and without requiring scrolling on more than one axis, except for parts of the content which require two-dimensional layout for usage or meaning.

#### 1.4.10 내용 확대(수준 AA)
> 내용 또는 기능 손실없이, 사용 또는 의미를 위해 2 차원 배치가 필요한 내용을 제외하고 1차원을 초과하는 스크롤 없이 320 CSS 픽셀과 동일한 너비로 확대할 수 있어야 한다.

// 설명: 웹 페이지에 확대/축소 기능을 넣으라는 의미가 아닙니다. 웹 브라우저가 제공하는 확대/축소 기능을 사용할 때 접근성 문제가 없어야 한다는 것을 의미합니다. 일반적으로 고정폭 웹 페이지는 400%까지 확대하는 경우 세로 스크롤과 함께 가로 스크롤을 유발합니다. 웹 개발자는 이 문제를 해결하기 위해 반응형 또는 가변폭 웹 페이지 레이아웃을 적용해야 합니다.

#### 1.4.11 Graphics Contrast(Level AA)
> The visual presentation of graphical objects that are essential for understanding the content or functionality have a contrast ratio of at least 4.5:1 against the adjacent color(s), except for the following:
>
> **Thicker**
>
> For graphical objects with a minimum width and height of at least 3 CSS pixels, the graphic has a contrast ratio of at least 3:1.
>
> **Sensory**
>
> Non-text content that is primarily intended to create a visual sensory experience has no contrast requirement;
>
> **Logotypes**
>
> Graphics that are part of a logo or brand name have no minimum contrast requirement.
>
> **Essential**
>
> A particular presentation of the graphical is essential to the information being conveyed.

#### 1.4.11 그래픽 명도 대비(수준 AA)
> 내용이나 기능을 이해하는 데 필수적인 그래픽 객체의 시각적 표현은 다음을 제외하고 인접 색상 대비 적어도 4.5 : 1의 명암비를 갖습니다.
>
> **더 두꺼운**
>
> 최소 너비와 높이가 3 CSS 픽셀 이상인 그래픽 객체의 경우 그래픽의 명도 대비가 최소 3 : 1입니다.
>
> **감각**
>
> 주로 시각적 감각 경험을 창출하기위한 비 텍스트 콘텐츠는 명도 대비 요구 사항이 없습니다.
>
> **로고 타입**
>
> 로고 또는 브랜드 이름 그래픽은 최소 명도 대비 요구 사항이 없습니다.
>
> **필수적인**
>
> 그래픽의 특별한 표현이 정보 전달에 필수적인 경우.

// 설명: 이 항목의 목적은 텍스트와 배경색의 명도 대비를 권장하는 지침을 그래픽까지 확대 적용하는 것입니다. 단, 모든 그래픽에 적용하는 것이 아니라 내용이나 기능을 이해하는데 필수적인 그래픽 객체에 한정합니다. 그래픽 객체는 이미지 문자를 의도하지 않으며 주로 아이콘, 선, 다이어그램과 같은 시각적 정보를 의미합니다. 3px 미만의 라인 표현은 얇은 편에 속하기 때문에 4.5 : 1의 명암비를 요구하는 한편 3px 이상의 라인 표현은 두껍기 때문에 3 : 1 수준의 명암비만 요구합니다. 정보&nbsp;아닌 감성을 전달하기 위한 그래픽 또는 정보 전달에 필수적인 표현은 이 항목의 요구 사항을 준수할 필요가 없습니다.

#### 1.4.12&nbsp;User Interface Component Contrast (Minimum)(Level AA)
> Essential visual identifiers of user interface components have a contrast ratio of at least 4.5:1 against the immediate surrounding color(s), except for the following situations:
>
> **Thicker**
>
> A contrast ratio of at least 3:1 is required where the minimum width and height are at least 3 CSS pixels, for the essential visual identifier.
>
> **Inactive**
>
> Disabled or otherwise inactive user interface components
>
> **User agent control**
>
> The color(s) of the user interface component and any adjacent color(s) are determined by the user agent and are not modified by the author.

#### 1.4.12 사용자 인터페이스 구성요소 명도대비(최소)(수준 AA)
> 사용자 인터페이스 구성요소의 필수 시각 식별자는 다음 상황을 제외하고 주변 색 대비 적어도 4.5:1의 명암비를 유지해야 한다.
>
> **더 두꺼운**
>
> 필수 시각 식별자의 최소 너비와 높이가 3 CSS 픽셀인 경우 최소 3:1의 명암비를 갖는다.
>
> **비활성**
>
> 사용 불가능하거나 비활성화된 사용자 인터페이스 구성요소.
>
> **유저 에이전트 콘트롤**
>
> 사용자 인터페이스 구성요소와 인접 색상이 유저 에이전트에 의해 결정되고 저자가 수정할 수 없다.

// 설명: 비활성 상태이거나 또는 유저 에이전트에 의해 수정할 수 없도록 처리된 경우를 제외한다면 3픽셀 미만의 두께를 가진 콘트롤(버튼과 폼 콘트롤 요소들)에 4.5:1의 명암비를 요구합니다. 3px 이상이라면 3:1 수준으로 완화할 수 있습니다. 이 지침은 문자와 배경색 명도대비 그리고 그래픽 명도대비와 유사한 지침입니다.

#### 2.2.6 Interruptions(minimum)(Level AA)
> There is an easily available mechanism to postpone and suppress interruptions and changes in content unless they are initiated by the user or involve an emergency.

#### 2.2.6 방해(최소)(수준 AA)
> 사용자가 시작하거나 긴급 상황이 발생하지 않는 한 내용의 변경과 방해를 중단하거나 연기하는&nbsp;메커니즘을 쉽게 사용할 수 있어야 한다.

// 설명: 주의력과 기억력 장애가 있는 사람이 과업을 수행할 수 있도록 주의를 끄는 자동 변경 콘텐츠를 제공하지 않아야 한다는 것을 의미합니다. 만약 제공하는 경우 손쉽게 중단할 수 있어야 합니다. 이 지침은 WCAG 2.0 – 3.2.5 요청에 의한 변화: 문맥의 변경은 오직 사용자의 요청에 의해서만 발생해야 한다. 그렇지 않으면 변경을 끌 수 있어야 한다. (수준 AAA) 항목과 유사해 보입니다. 다만 이런 변경을 중단할 수 있는 메커니즘을 쉽게 사용할 수 있어야 한다는 측면을 더욱 강조한 것 같네요. 예를 들면 자동 갱신 콘텐츠가 이 항목의 적용을 받습니다. 자동 갱신 콘텐츠를 제공한다면 쉽게 중단하는 방법도 함께 제공해야&nbsp;합니다.

#### 2.2.7 Accessible Authentication(Level A)
> Essential steps of an authentication process, which rely upon recalling or transcribing information, have one of the following:
>
> * alternative essential steps, which do not rely upon recalling and transcribing information; or
> * an authentication-credentials reset process, which does not rely upon recalling and transcribing information
>
> Exceptions:
> * Authentication process involves basic identifying information to which the user has easy access, such as name, address, email address and identification or social security number.
> * This is not achievable due to legal requirements.

#### 2.2.7 접근 가능한 인증(수준 A)
> 인증 절차의 필수 단계로써 정보를 기억하거나 전사(역자 주: 데이터의 형태를 변경하여 쓰는 일)에 의존하는 경우 다음중 하나가 참 이어야 한다.
>
> * 정보를 기억하거나 전사에 의존하지 않는 대체 필수 단계 제공.
> * 정보를 기억하거나 전사에 의존하지 않는 인증 자격 재설정 과정.
>
> 예외:
> * 인증 프로세스에 이름, 주소, 메일 및 신원 또는 사회보장 번호와 같이 사용자가 쉽게 접근할 수 있는 기본 식별 정보가 포함되어 있음.
> * 법적 요구사항 때문에 달성할 수 없는 경우.

// 설명: 개인의 신원을 인증하는 방법으로써 암기 또는 화면에 있는 이미지 문자를 따라 작성하도록 하는 경우 대체 수단을 제공해야 한다는 지침입니다. 암기에 의존하는 경우 학습 장애가 있는 사람이 인증하기 어렵습니다. 전사에 의존하는 경우 인지 장애가 있는 사람이 인증하기 어렵습니다.

#### 2.4.11 Character Key Shortcuts(Level A)
> If a keyboard shortcut consisting entirely of one or more character keys is implemented by the content, then a mechanism is available to turn it off or to remap it to a shortcut that uses at least one non-character key.

#### 2.4.11 문자 단축키(수준 A)
> 콘텐츠에 문자 단축키가 구현되어 있다면 그것을 해제하거나, 문자 아닌 키를 사용하는 단축으로 다시 매핑할 수 있는 메커니즘을 적용해야 한다.

// 설명: 단일 문자 단축키(예를 들면 s 키를 눌렀을 때 전송이 된다)를 제공하는 경우 음성 명령 도구를 이용하는 사람을 방해할 수 있습니다. 또한 실수로 키보드를 누르는 경우에도 문제가 됩니다. 따라서 단일 문자 단축키를 제공하는 경우 이것을 끄거나 다른 키와 조합하는 방식으로 다시 매핑할 수 있어야 합니다. HTML에서 제공하는 accesskey 속성은 항상 alt키와 조합하도록 유저 에이전트에 구현되어 있기 때문에 문제가 되지 않습니다. 문자 아닌 단축키(예를 들면 방향키)는 해당하지 않습니다.

#### 2.6.1 Orientation(Level AA)
> Content is not locked to a specific display orientation, and functionality of the content is operable in all display orientations, except where display orientation is essential for use of the content.

#### 2.6.1 방향(수준 AA)
> 콘텐츠를 이용하기 위해 방향이 필수적인 경우를 제외하고 콘텐츠는 특정 방향으로 잠기지 않아야 하고, 콘텐츠의 모든 기능은 모든 방향에서 조작할 수 있어야 한다.

// 설명: 일부 모바일 콘텐츠는 특정 방향에서만 이용할 수 있도록 방향이 제한되어 있는데요. 전동 휠체어의 팔걸이에 단말을 고정해 둔 상태로 사용하는 사람들이 이용하기 어려울 수 있습니다.

#### 3.2.6 Accidental Activation(Level A)
> For single pointer activation, at least one of the following is true:
>
> * Activation is on the up-event, either explicitly or implicitly as a platform's generic activation/click event;
> * A mechanism is available that allows the user to choose the up-event as an option;
> * Confirmation is provided, which can dismiss activation;
> * Activation is reversible;
> * Down-event activation event is essential and waiting for the up-event would invalidate the activity.

#### 3.2.6 우발적 실행(수준 A)
> 단일 포인터 실행은 적어도 다음중 하나가 참 이어야 한다.
>
> * 플랫폼의 일반적인 실행/클릭 이벤트로써 명시적 또는 암시적으로 업 이벤트에 실행한다.
> * 사용자가 업 이벤트를 선택할 수 있는 메카니즘이 있다.
> * 실행을 취소할 수 있는 확인 절차를 제공.
> * 실행을 되돌릴 수 있다.
> * 실행의 시간 제약은 필수적이고 업 이벤트를 기다리면 실행을 취소한다.

// 설명: 시각 장애, 인지 장애, 운동 장애 사용자가 우발적으로 포인트를 눌러(mousedown, touchstart) 실수로 기능을 실행할 수 있기 때문에 '릴리즈, 터치 엔드, 마우스 업' 이벤트를 통해 기능을 실행해야 합니다. 만약 mousedown, touchstart 이벤트로 실행하는 경우 실행을 취소할 수 있는 확인 기능을 제공하거나, 실행 결과를 되돌릴 수 있어야 합니다. 사용자가 mousedown, touchstart 상태로 일정 시간 이상 기다린다면 실행을 취소해야 합니다.

#### 3.2.7 Change of Content(Level AA)
> Programmatic notification is provided for each change of content that indicates a user action was taken or that conveys information, unless one or more of the following is true:
>
> * There is a programmatically determined relationship between the new content and the control that triggers it;
> * The user has been advised of the change of content before or as a result of using the control;
> * The change of content is not a result of a user action AND not related to the primary purpose of the page.

#### 3.2.7 내용 변경(수준 AA)
> 다음 중 하나 또는 그 이상이 참인 경우가 아니라면 사용자 행위 발생, 또는 정보가 전달되었다는 것을 각 콘텐츠를 변경할 때마다 프로그래밍 방식으로 알려야 한다.
>
> * 새 콘텐츠와 그것을 유발하는 콘트롤 사이의 관계가 프로그래밍 방식으로 결정되어 있다.
> * 사용자는 콘트롤 사용 전후 콘텐츠 변경 알림을 받는다.
> * 콘텐츠 변경이 사용자 행위의 결과가 아니며 현재 페이지의 주요 목적과 관계가 없다.

// 설명: 보조기술 사용자가 내용 변경을 인지할 수 있도록 돕기 위한 지침입니다. 내용 변경이란 모든 내용이 사용자에게 전달된 이후 추가로 변경된 내용을 의미합니다. AJAX를 통해 내용을 갱신한 경우 이 사례에 해당합니다. 이 지침을 준수하면 보조기술 사용자는 변경 내용을 인지한 상태로 의사 결정할 수 있습니다. 개발자는 aria-live 명세를 이용하여 이 지침을 준수할 수 있습니다. 이미 초기에 로드되어 있는 탭 콘텐츠의 토글 또는 툴팁 레이어를 열거나 닫는 동작은 '내용 변경'이 아닌 '상태 변경'으로써 이 지침에서 다루지 않고 4.1.2 지침에서 커버하고 있습니다. 그러나 탭을 토글하는 순간 탭 콘텐츠를 AJAX로 갱신한다면 내용 변경에 해당합니다.
