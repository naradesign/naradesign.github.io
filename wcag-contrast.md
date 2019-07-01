## WCAG 2.0 지침이 전하는 전경색과 배경색 명도 대비.

WCAG 2.0 지침에는 글꼴의 색과 문서의 배경 색이 어느 정도의 명도 대비를 지녀야 하는지에 대한 지침이 있습니다. 하지만 지침이 제시하는 것을 실무에 바로 적용하기가 어려운데 이는 지침이 제시하는 구체적인 숫자의 의미와 적합성 수준에 대한 이해를 요구하기 때문 입니다.

### WCAG 2.0에서 적합성 수준의 의미.
WCAG 2.0 지침에서 '적합성 수준'이란 세부 지침들이 갖는 중요도를 3단계로 분류함으로써 웹 사이트의 접근성 정책을 세우는데 기준을 마련하고 웹 사이트 구축 후에는 어느 정도 수준까지 접근성을 확보 했는지 되도록 알기 쉽게 설명하려는 목적이 있습니다. 수준 `A`는 중요도가 가장 높고 비교적 달성이 용이한 최소한의 등급이며 수준 `AAA`는 중요도가 가장 낮지만 달성하기가 어렵고 달성 했을때 접근성이 극대화 되는 매우 까다로운 수준 이라고 설명할 수 있습니다.

1. `A` : 웹 접근성을 확보했다는 주장을 펼치기 위하여 반드시 지켜야 할 최소한의 수준으로써 강력하게 권장된다.
1. `AA` : 최소한의 수준을 넘어서 보다 향상된 접근성을 갖추기 위한 수준으로써 권장된다.
1. `AAA` : 웹 접근성을 극대화 하고자 할 때 갖추어야 할 수준으로써 이 수준은 의무화 하기에 너무 어려울 수도 있다.

즉, 적합성 수준이란 딱히 각각의 수준에 특별한 의미가 있는 것이 아니라 지침의 중요도에 따라서 등급을 매긴 것에 불과 합니다. 만약 여러분의 웹 사이트가 적합성 수준이 `A`라고 표기된 지침을 모두 지켰다면 여러분의 웹 사이트에 대한 접근성 수준은 `A`라고 부를 수 있을 것입니다. `A` 정도만 되어도 훌륭한 것입니다. 만약 이 수준이 형편 없는 수준이라는 평가를 받아야 했다면 아마 'C'라고 명명했을지도 모릅니다.

### 전경색과 배경색의 명도 대비에 관한 지침.
> #### 1.4.3 명암 대비 (최소한의): 다음과 같은 경우를 제외하고 문자와 문자 이미지의 시각적인 표현은 최소한 `4.5:1`의 명암 대비를 부여해야 한다.(수준 AA)
>
> * 큰 문자: 큰 비율의 문자와 큰 비율의 이미지 문자는 적어도 `3:1`의 명암 비율을 갖는다.
> * 기타: 순수하게 장식적이며 누구라도 알아볼 수 없는 문자와 이미지 문자 또는 사진과 같이 시각적으로 의미를 전달하는 피상적 사용자 인터페이스 구성요소는 명암비를 필요로 하지 않는다.
> * 로고타입: 로고나 브랜드 이름에 포함된 문자는 최소 명암비를 필요로 하지 않는다.
>
> #### 1.4.6 명암 대비 (향상): 다음과 같은 경우를 제외하고 문자의 시각 표현과 문자 이미지는 적어도 7:1의 명암대비를 부여해야 한다.(수준 AAA)
>
> * 큰 문자: 큰 비율의 문자와 큰 비율의 이미지 문자는 적어도 `4.5:1`의 명암 비율을 갖는다.
> * 기타: 순수하게 장식적이며 누구라도 알아볼 수 없는 문자와 이미지 문자 또는 사진과 같이 시각적으로 의미를 전달하는 피상적 사용자 인터페이스 구성요소는 명암비를 필요로 하지 않는다.
> * 로고타입: 로고나 브랜드 이름에 포함된 문자는 최소 명암비를 필요로 하지 않는다.

### 모든 전경 글꼴과 배경 색은 최소한 `4.5:1`의 명암 대비를 만족해야 한다.
명암 대비는 글꼴의 크기 또는 굵기과 밀접한 관계가 있습니다. 따라서 모든 크기의 글꼴에 `4.5:1`의 명암 대비를 부여해야 하는 것은 아닙니다. 만약 글꼴이 크거나 굵다면 명암 대비는 조금 더 완화된 기준을 적용해도 됩니다. 지침에서는 큰 문자(<span style="font-size: 18pt">18pt 이상</span> 또는 <span style="font-weight: bold; font-size: 14pt">14pt 굵은</span> 글꼴)에 한하여 `3:1` 수준의 명암 대비를 갖출것을 요구하고 있으며 이는 일반적인 크기의 글꼴(약 `12~14px` 정도)이 `4.5:1`의 명암 대비를 갖추어야 하는 것으로부터 조금 완화된 기준 입니다.

WCAG 2.0 지침은 명암의 강도를 `1~21` 단계로 나누고 명암을 전혀 구분할 수 없는 상태를 `1:1`(white:white) 으로 표현하며 전경과 배경이 확연하게 구분되는 상태를 `21:1`(black:white) 으로 표현 합니다.

사람이 이 명암의 등급을 정확히 판별하는 것은 어렵기 때문에 여기서 실무 적용시 애로 사항이 발생하게 되고 빈번하게 사용되는 색에 대한 사용 메뉴얼을 필요로 하게 됩니다. 이것을 도와주는 것이 바로 색 분석 도구 인데 웹에서 즉시 판별할 수 있고 또는 전용 소프트웨어를 설치해도 됩니다.

### 전경/배경색 명암 대비 분석 도구들.
* Colour Contrast Check(snook.ca) – <a href="http://www.snook.ca/technical/colour_contrast/colour.html">http://www.snook.ca/technical/colour_contrast/colour.html</a>
* Colour Contrast(Juicy Studio) – <a href="http://juicystudio.com/services/luminositycontrastratio.php">http://juicystudio.com/services/luminositycontrastratio.php</a>
* Colour Contrast Analyzer(Colors on the web) – <a href="http://www.colorsontheweb.com/colorcontrast.asp">http://www.colorsontheweb.com/colorcontrast.asp</a>
* Contrast Analyser(The Paciello Group) – <a href="http://www.paciellogroup.com/resources/contrast-analyser.html">http://www.paciellogroup.com/resources/contrast-analyser.html</a> Windows/MAC Application.

사용해 본 결과 Colour Contrast Check(snook.ca) 도구가 가장 섬세하게 필요한 정보들을 제공해 주고 있어서 충분히 만족스러웠습니다.

### WCAG 2.0 지침의 명도 대비 적합성 수준을 표시한 전경/배경색 사용 예.
모든 예를 표시할 수 없기 때문에 일반적으로 널리 사용되고 있는 흰색 배경에 무채색 글자를 표현 하였습니다. 붉은색 글씨로 `Passed` 표시가 된 글꼴의 명도 대비는 적어도 WCAG 2.0의 `AA`(지침1.4.3) 또는 `AAA`(지침1.4.6) 수준을 만족한다는 의미 입니다. 이 표로 알 수 있는 것은 `12px` 글꼴을 사용할 때 회색의 밝기는 적어도 `#767676` 이 되어야만 '노안, 약시, 또는 일시적으로 정상 시력을 갖지 못한 사람들'에게 웹 문서가 편안하게 보인다는 사실입니다. 이 밖의 다양한 글꼴 색 또는 배경 색에 대한 조합은 앞서 소개드린 분석 도구들을 사용하여 도움을 받으시기 바랍니다.

<table>
    <caption>WCAG 2.0 기준(보통 문자, 큰 문자)에 따라 다양한 명도 대비를 보여주는 표(`Passed`는 적합한 수준임)</caption>
    <tbody>
        <tr>
            <th scope="col">Contrast Ratio</th>
            <th scope="col"><abbr title="ForeGround">FG</abbr>/<abbr title="BackGround">BG</abbr> Color</th>
            <th scope="col">Normal Text <br>
            12pt(16px, 1em, 100%) + Normal</th>
            <th scope="col">Large Text <br>
            14pt(19px, 1.2em, 120%) + Bold</th>
            <th scope="col">Large Text <br>
            18pt(24px, 1.5em, 150%) + Normal</th>
        </tr>
        <tr style="color:#000000">
            <th scope="row">21:1</th>
            <td scope="row">#000000/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.
            <br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.
            <br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.
            <br>
            <strong style="color:blue">Passed AAA</strong></td>
        </tr>
        <tr style="color:#333333">
            <th scope="row">12.63:1</th>
            <td scope="row">#333333/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
        </tr>
        <tr style="color:#595959">
            <th scope="row" style="background:#ffc">7:1</th>
            <td scope="row">#595959/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
        </tr>
        <tr style="color:#666666">
            <th scope="row">5.74:1</th>
            <td scope="row">#666666/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
        </tr>
        <tr style="color:#767676">
            <th scope="row" style="background:#ffc">4.54:1</th>
            <td scope="row">#767676/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AAA</strong></td>
        </tr>
        <tr style="color:#777777">
            <th scope="row">4.48:1</th>
            <td scope="row">#777777/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
        </tr>
        <tr style="color:#888888">
            <th scope="row">3.54:1</th>
            <td scope="row">#888888/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
        </tr>
        <tr style="color:#959595">
            <th scope="row" style="background:#ffc">3:1</th>
            <td scope="row">#959595/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.<br>
            <strong style="color:blue">Passed AA</strong></td>
        </tr>
        <tr style="color:#999999">
            <th scope="row">2.85:1</th>
            <td scope="row">#999999/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.</td>
        </tr>
        <tr style="color:#CCCCCC">
            <th scope="row">1.61:1</th>
            <td scope="row">#CCCCCC/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.</td>
        </tr>
        <tr style="color:#EEEEEE">
            <th scope="row">1.16:1</th>
            <td scope="row">#EEEEEE/#FFFFFF</td>
            <td style="font:16px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:bold 19px Tahoma">Power of Web. 웹의 힘.</td>
            <td style="font:24px Tahoma">Power of Web. 웹의 힘.</td>
        </tr>
    </tbody>
</table>

<div id="fb-root"></div>
<script async defer crossorigin="anonymous" src="https://connect.facebook.net/ko_KR/sdk.js#xfbml=1&version=v3.3"></script>
<div class="fb-comments" data-href="https://naradesign.github.io/article/wcag-contrast.html" data-numposts="10" data-width="100%"></div>
