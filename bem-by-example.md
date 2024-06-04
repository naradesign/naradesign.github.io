## 예제로 이해하는 BEM.
이 글은 [BEM by Example(NATHAN RAMBECK)](https://seesparkbox.com/foundry/bem_by_example)의 한글 번역이다. 본문에서 언급하는 [불꽃상자](https://seesparkbox.com/)는 이 게시물을 발행한 웹 사이트 이름이다. 지금부터 번역을 시작한다.

BEM은 불꽃상자에서 폭넓게 사용하는 잘 알려진 CSS 클래스 명명 규칙이다. BEM의 기본 개념은 단순하고 직관적이지만 BEM을 처음 접할 때 저지르기 쉬운 오류들을 예제를 통해 설명한다.

BEM(Block-Element-Modifier)은 CSS 클래스 이름을 위한 불꽃상자의 명명 규칙 표준이다. BEM은 여러 웹 사이트에서 꽤나 많이 채택되었다. CSS를 쉽게 읽고, 쉽게 이해하고, 확장하기에 용이하다.



### 왜 BEM인가?
BEM 명명 규칙은 세 가지 뚜렷한 이점을 제공한다.

1. BEM은 목적 또는 기능을 전달한다.
2. BEM은 구성 요소의 구조를 전달한다.
3. BEM은 선택자 명시도를 항상 낮은 수준으로 유지한다.

*역자 주: CSS 명시도를 잘 모르는 독자는 [명시도 명세](https://www.w3.org/TR/selectors-3/#specificity)와 [명시도 계산기](https://specificity.keegan.st/)를 참고.*

### BEM은 어떻게 동작하는가?
BEM 클래스 이름은 최대 세 가지로 구성된다.

1. 블록(Block): 구성 요소의 가장 바깥쪽 상위 요소를 블록으로 정의한다.
2. 요소(Element): 구성 요소 안쪽에는 하나 또는 그 이상의 요소가 있을 수 있다.
3. 변경자(Modifier): 블록 또는 요소는 변경자를 이용하여 변형을 표시할 수 있다.

세 가지 형식을 모두 클래스 이름에 사용하면 이렇게 보일 것이다.

```css
.block__element--modifier
```

소개는 간단하게 마치고 구체적인 예제를 좀 살펴보자.



### 예제

#### 요소 또는 변경자가 없는 단순한 구성 요소
간단한 구성 요소는 단일 요소와 단일 클래스를 사용하는 것만으로도 블록이 될 수 있다.
```html
<!-- 역자 주 / btn은 하나의 구성 요소다 -->
<button class=”btn”></button>

<style>
  .btn {}
</style>
```

#### 변경자가 있는 구성 요소
구성 요소에 변형이 있을 수 있다. 변형은 변경자 클래스로 구현한다.
```html
<!-- DO THIS / 역자 주 / btn 구성 요소에 --submit 변경자를 추가해서 확장했다 -->
<button class="btn btn--submit"></button>

<style>
  .btn {
    display: inline-block;
    color: blue;
  }
  .btn--submit {
    color: green;
  }
</style>
```

변경자 클래스만 사용하면 안 된다. 변경자 클래스는 기본 클래스를 대체하기 위한 것이 아니라 확장하기 위한 것이다.

```html
<!-- DON'T DO THIS / 이렇게 하지 마세요 -->
<button class="btn--secondary"></button>

<style>
  .btn--secondary {
    display: inline-block;
    color: green;
  }
</style>
```


#### 하위 요소가 있는 구성 요소
더 복잡한 구성 요소에는 하위 요소가 있다. 스타일이 필요한 각 하위 요소에는 명명된 클래스가 있어야 한다.

BEM의 목적 중 하나는 명시도를 낮추고 일관성 있게 유지하는 것이다. HTML의 하위 요소에서 클래스 이름을 생략하지 않아야 한다. 클래스 이름을 생략하면 구성 요소 내부에 있는 이름 없는 요소의 스타일을 처리하기 위해 명시도가 더 높은 선택자를 사용해야 한다(아래 `img` 및 `figcaption` 요소 참고). 클래스 이름을 생략하면 당장은 장황한 클래스 이름을 사용하지 않아서 더 간결해 보일 수 있지만 결국 미래엔 명시도 증가 때문에 위기를 맞게 된다. BEM의 목표 중 하나는 대부분의 선택자가 단일 클래스 이름만 사용하는 것이다.*(역자 주: BEM이 선택자 중첩을 금지한다는 의미는 아니다. 하위 요소에 클래스 선택자를 사용하면 !important 같은 끔찍한 규칙을 덜 사용하도록 돕는다.)*

```html
<!-- DO THIS -->
<figure class="photo">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">Look at me!</figcaption>
</figure>

<style>
  .photo { } /* 명시도 10 */
  .photo__img { } /* 명시도 10 */
  .photo__caption { } /* 명시도 10 */
</style>

<!-- DON'T DO THIS / 이렇게 하지 마세요 -->
<figure class="photo">
  <img src="me.jpg">
  <figcaption>Look at me!</figcaption>
</figure>

<style>
  .photo { } /* 명시도 10 */
  .photo img { } /* 명시도 11 */
  .photo figcaption { } /* 명시도 11 */
</style>
```

구성 요소에 여러 수준의 하위 요소가 있는 경우 클래스 이름에서 각 수준을 나타내려고 하면 안 된다. BEM은 구조의 깊이를 전달하지 않는다. 구성 요소의 하위 요소를 나타내는 BEM 클래스 이름은 오직 기본 블록 이름과 하나의 요소 이름만 허용한다. 아래 예시에서 `photo__caption__quote`는 BEM을 잘못 사용한 것으로 `photo__quote`가 더 적합하다.

```html
<!-- DO THIS -->
<figure class="photo">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">
    <blockquote class="photo__quote">
      Look at me!
    </blockquote>
  </figcaption>
</figure>

<style>
  .photo { }
  .photo__img { }
  .photo__caption { }
  .photo__quote { }
</style>


<!-- DON'T DO THIS / 이렇게 하지 마세요 -->
<figure class="photo">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">
    <blockquote class="photo__caption__quote"> <!-- 클래스 이름에 여러 하위 요소(또는 구조)를 명명하지 말 것 -->
      Look at me!
    </blockquote>
  </figcaption>
</figure>

<style>
  .photo { }
  .photo__img { }
  .photo__caption { }
  .photo__caption__quote { } /* 역자 주: 초심자의 가장 흔한 실수다 */
</style>
```


#### 변경자가 있는 요소
경우에 따라 구성 요소의 하위 단일 요소에 변형을 주려고 할 수 있다. 이런 경우 구성 요소를 따로 추가하는 대신 하위 요소에 변경자를 추가하면 된다.

```html
<figure class="photo">
  <img class="photo__img photo__img--framed" src="me.jpg">
  <figcaption class="photo__caption photo__caption--large">Look at me!</figcaption>
</figure>

<style>
  .photo__img--framed {
    /* incremental style changes */
  }
  .photo__caption--large {
    /* incremental style changes */
  }
</style>
```


#### 구성 요소 변경자 기반으로 하위 요소 스타일 처리하기
동일한 구성 요소의 하위 요소를 동일한 방식으로 일관성 있게 수정하려면 기본 구성 요소에 변경자를 추가하고 하나의 변경자를 기반으로 각 하위 요소 스타일을 처리한다. 이렇게 하면 명시도가 높아지지만 구성 요소 수정이 훨씬 수월해진다.

```html
<!-- DO THIS / 역자 주 / BEM이 선택자 중첩을 금지하는 건 아니다. 다만 지금보다 중첩이 더 깊어지면 곤란하다. -->
<figure class="photo photo--highlighted">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">Look at me!</figcaption>
</figure>

<style>
  .photo--highlighted .photo__img { }
  .photo--highlighted .photo__caption { }
</style>

<!-- DON'T DO THIS / 이렇게 하지 마세요 -->
<figure class="photo">
  <img class="photo__img photo__img--highlighted" src="me.jpg">
  <figcaption class="photo__caption photo__caption--highlighted">Look at me!</figcaption>
</figure>

<style>
  .photo__img--highlighted { }
  .photo__caption--highlighted { }
</style>
```


#### 여러 단어 명명법(케밥 케이스, 카멜 케이스 접목)
BEM 이름은 의도적으로 `블록__요소--변경자`를 분리하기 위해 단일 밑줄 대신 이중 밑줄과 이중 하이픈을 사용한다. 단일 하이픈을 단어 구분 기호로 사용할 수 있기 때문이다. 클래스 이름은 읽기 쉬워야 하기 때문에 보편적으로 인식할 수 없는 약어는 바람직하지 않다.

```html
<!-- DO THIS / 역자 주 / 케밥 케이스를 접목한 명명법 -->
<div class="some-thesis some-thesis--fast-read">
  <div class="some-thesis__some-element"></div>
</div>

<style>
  .some-thesis { }
  .some-thesis--fast-read { }
  .some-thesis__some-element { }
</style>

<!-- DO THIS / 역자 주 / 이렇게 카멜 케이스를 접목해도 된다 -->
<div class="someThesis someThesis--fastRead">
  <div class="someThesis__someElement"></div>
</div>

<style>
  .someThesis { }
  .someThesis--fastRead { }
  .someThesis__someElement { }
</style>

<!-- DON'T DO THIS / 이렇게 하지 마세요 -->
// These class names are harder to read
<div class="somethesis somethesis--fastread">
  <div class="somethesis__someelement"></div>
</div>

<style>
  .somethesis { }
  .somethesis--fastread { }
  .somethesis__someelement { }
</style>
```



### BEM은 확실하다
아직 BEM을 사용하지 않는다면 다음 프로젝트에서 BEM을 사용할 것을 강력하게 추천한다. 당장은 익숙하지 않겠지만 크고 작은 프로젝트에서 빠르게 이득을 보게 될 거라고 확신한다. 기묘한 BEM 명명 규칙을 처음 접할 때 대부분의 사람들이 저지르는 실수를 피하는데 이 예제가 도움이 되기를 바란다.

### 저자
Nathan은 컨텐츠 관리 솔루션 설계 및 확장 가능한 설계 시스템 작성 경험이 있는 백엔드 개발자다. Nathan은 [Dayton Web Developers](http://www.meetup.com/dayton-web-developers/) 및 [Dayton Drupal User Group](http://www.meetup.com/drupal-dayton/)의 설립자다. [Nathan의 글을 더 읽을 수 있다](https://seesparkbox.com/foundry/author/nathan_rambeck). [Twitter](https://twitter.com/nrambeck), [CodePen](https://codepen.io/nrambeck/), [GitHub](https://github.com/nrambeck)에서 그를 찾을 수 있다.

### 역자
마크업 개발자 정찬명입니다. 포스트에 문제가 있으면 [이슈](https://github.com/naradesign/article/issues)로 등록해 주세요. 비공개로 연락하려면 메일 주세요. dece24 앳 gmail 닷 com
