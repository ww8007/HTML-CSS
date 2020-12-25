# TAG2(inilne)

### a

    설명 : 다른 페이지, 같은 페이지 위치, 파일, 이메일, 전화번호 등 다른 ULR 연결 할 수 있는 하이퍼 링크 설정
    ** 중요 **
    ex )    1. download         다운로드 용(힌트용 실제 다운로드 아님)
                value : bool
            2. **href**             링크 URL(생략가능)
                value :
            3. hreflang         링크 URL 언어
                value : ko, en
            4. rel              링크 URL과의 관계
                value : license, prev, next
            5. **target**           링크 URL 표시 위치
                value   : _self(현재창), _blank(새로)
                default : _self
            6. type             링크 URL MIME 타입
                value : text/html
                링크를 보낼 때 자동으로 명시되기 때문에 사용하지는 않아도 됨
    <img> src = "경로" alt " " 동일하게
    <a> href "경로"

```html
<h2 id="title1">제목1</h2>
```

```css
a {
  display: inline;
}
```

#### 맛보기 css

    부록 : h의 id 값은 교유값을 가져야 한다.
    고유 id title1의 제목으로 바로 이동가능

```css
<li><a href="#title1">제목1</a></li>
<h2 id="title1">제목1</h2>
```

### abbr

    설명 : 약어를 지정 (Abbreviation)
    title : 전역속성(전체 글자나 설명을 제공)

```css
abbr {
  display: inline;
}
```

### b

    설명 : 문체가 다른 글자의 범위를 설정(Bring Attention)
    전에는 bold의 약자로 사용되었지만 지금은 의미를 가짐
    특별한 의미를 가지지 않는 곳에 사용하고 도움을 주는 용도
    다른 태그가 적합하지 않은 경우 마지막 수단으로 사용

```css
b {
  display: inline;
}
```

### mark

    설명 : 사용자의 관심을 끌기 위해 하이라이팅 할 때 사용
    형광팬 사용한 것 처럼 글자 배경 노랑색
    css로도 표현이 가능하지만 html

```css
mark {
  display: inline;
}
```

### em

    설명 : 단순한 의미 강조를 표시(Emphasis)
    중첩이 가능 -> 중첩될 수록 강조 의미가 강해짐
    정보통신보조기기에서 구두 강조로 발음도미
    기본 체 : 이탤릭체(Italic type)

```css
em {
  display: inline;
}
```

### strong

    *** 의미적 bold와 너무 비슷해 보인다면 다르게 css 표현 ***
    설명 : 의미의 중요성을 나타내기 위해 사용(Strong Importance)
    em 테그는 강조를 나타내고 strong 테그는 중요도를 나타냄
    글자가 기본적으로 두껍게 표시됨
    b tag 와 동일하게 bold체로 나타냄 -> 혼용하지 않도록 css 작성 필요

```css
strong {
  display: inline;
}
```

### i

    설명 : 평범한 글자와 구분(아이콘, 특수기호)
    기본체 : 이탤릭체(Italic type)

[ITAGICON](https://www.w3schools.com/tags/tag_i.asp)
[Fontawesome](https://fontawesome.com/)

```html
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.8.2/css/all.min.css"
/>
```

```css
i {
  display: inline;
}
```

### dfn

    설명 : 용어를 정의할 때 사용(Definition)
    <dl>(<dt>, <dd>) dl로 묶고 dt와 dd 사용 <- 용어가 많을 때 사용
    용어가 하나일 때 사용

```css
dfn {
  display: inline;
}
```

### cite

    설명 : 창작물에 대한 참조를 설정
    책, 논문, 영화, tv 프로그램, 게임의 제목
    기본 체 : 이텔릭체
    글씨를 다룬다 -> inline
    h1~h6 글씨 다루긴 하지만 -> block

```css
cite {
  display: inline;
}
```

### q

    설명 : 짧은 인용문을 설정(Inline Quotation)
    긴 인용문 사용시 blockquote 사용
    cite

```css
q {
  display: inline;
}
```

### u

    설명 : 밑줄이 있는 글자를 설정
    순수하게 꾸미는 용도 -> css에서 다룰 수 있기 때문에 별 필요 x
    <a>와 혼동하는 위치에서 사용하지 않도록 한다.

```css
<span style = "text-decoration: underline">
    사용할 수 있는 경우 사용 권장 x
```

```css
u {
  display: inline;
}
```

### code

    설명 : 컴퓨터 코드 범위를 설정 (Inline Code)
    기본적으로 고정폭(Monospace)글꼴 계열로 표시
    css font-family
    정확하게 사용자에게 어디가 코드 부분인지 인지하기 위해 사용

```css
code {
  display: inline;
}
```

### kbd

    설명 : 키보드에서 사용자 입력을 나타내는 텍스트 범위를 설정
    Ctrl Alt K ESC

```css
kbd {
  display: inline;
}
```

### sup, sub

    설명 : 위 첨자(<sup>), 아래 첨자(<sub>)
    Superscripted text, Subscript text
    수학기호 또는 화학 기호 등 표시

```css
sup,
sub {
  display: inline;
}
```

### time

    *** IE 지원 불가 ***
    설명 : 날짜나 시간을 나타내기 위한 목적
    datetime 유효한 날짜 문자
    YYYY - MM - DD

```css
time {
  display: inline;
}
```

### span

    설명 : 본질적으로 아무것도 의미가 없음
    div -> block 의미 없음
    span -> inline 의미 없음
     차이점은 inline 과 block의 차이

```css
span {
  display: inline;
}
```

### br /

    설명 : 줄바꿈 설정
    닫히는 테그가 없음 -> 빈 테그
    간격을 넓히고 싶다면 css를 활용해야함
     -> br을 여러번 쓰는 것은 하면 안됨
    일반적으로 p tag -> line-height
        16px * 1.4
        첫 문장 두번 째 문장 -> 기본 폰트 16px
        (50-34)/2 = 17px

```css
br {
  display: inline;
}
```

### del

    설명 : 삭제된(변경된) 텍스트의 범위를 지정
    cite        변경을 설명하는 리소스의 URI(변경된 이유)
    datetime    변경이 일어난 유요한 날짜 문자(변경 날짜)

```css
del {
  display: inline;
}
```

### ins

    설명 : 새로 추가된 텍스트의 범위를 지정
    cite        변경을 설명하는 리소스의 URI(변경된 이유)
    datetime    변경이 일어난 유요한 날짜 문자(변경 날짜)

```css
ins {
  display: inline;
}
```
