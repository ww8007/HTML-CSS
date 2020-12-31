# CSS

### 인라인(in-line) 방식

설명 : HTML 요소(태그) 'style'속성에 직접 작성하는 방식

인라인으로 style을 선언하는 방식은 좋은 방식이 아님
인라인 스타일 자체가 문제가 아니라 사용자가 직접 이렇게 작성하는 것 보다는
자동으로 작성되게 하는 것이 목적

```html
<div style="color:red; fornt-size=20px; font-weight: bold;> HELLO</ div>
```

### 내장(embedded) 방식

설명 : HTML &#60;style&#62;&#60;/style&#62; 안에 작성하는 방식

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
            color: red;
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div>HELLO</div>
</body>
</html>
```

### 링크(link)방식

설명 : HTML &#60;link&#62;를 이용하여 외부 문서로 CSS를 불러와 적용하는 방식

-  가장 일반적인 방식
-  ./ link 해서 css 파일 불러옴

### @import 방식

설명 : CSS @import 를 이용하여 외부 문서로 CSS 불러와 적용하는 방식

-  link와 동일하게 css 가져옴
-  link와 다른 점
   link 는 html에서 외부 css
   import 는 css에서 외부 css
-  주의사항

1. import 규칙을 통해 불러오면 line by line로 불러옴
   직렬 호출 방식 - 시간이 오래 걸림

```css
@import url("./common2.css");
```

## 선택자(Selector)

### 1.전체 선택자(Universla Selector)

설명 : (요소 내부의)모든 요소를 선택 -> \*

```css
* {
   color: red;
}
```

### 2.테그 선택자(Type Selector)

설명 : 태그이름이 E인 요소 선택

앞 뒤 요소에 기호가 없으면 테그 선택자로 받아들이면 된다.

```css
li {
   color: red;
}
```

### 3.클래스 선택자

설명 : HTML class 속성 값이 E인 요소 선택

.E
선택자앞에 . 이 있으면 클래스 선택자로 받아들이면 된다.

````css
.E {
   color: red;
}
### 4.아이디 선택자

설명 : HTML id 속성의 값이 E인 요소 선택

#E

```css
#orange {
   color: red;
}
````

## 복합 선택자(Combinators)

### 1. 일치 선택자(Basic Combinator)

설명 : E와 F를 동시에 만족하는 요소 선택

ex) EF

```css
span.orange {
   color: red;
}
```

### 2. 자식 선택자(Child Combinator)

설명 : E의 자식요소 F를 선택

ex ) E > F
E : 조건
F : 검색

```css
ul > .oragne {
   color: red;
}
```

### 3. 후손(하위) 선택자(Desecendant Combinator)

설명 : E의 후손(하위)요소 F를 선택

ex) E F(띄어쓰기가 선택자의 기호로 사용)

```css
div .orange {
   color: red;
}
```

### 4. 인접 형제 선택자(Adjacent Sibling Combinator)

설명 : E의 다음 형제 요소 F 하나만 선택

ex) E + F
다음에 인접해 있는 형제 요소
아래 테그가 선택됨

```css
.orange + li {
   color: red;
}
```

### 5. 일반 형제 선택자(General Sibling Combinator)

설명 : E의 다음 형제 요소 F 모두 선택

ex) E ~ F
다음의 모든 형제 선택
앞쪽은 포함되지 않음

```css
.orange ~ li {
   color: red;
}
```

## 상속(Inheritance)

특정한 css 요소들은 부모 요소를 선언하는게 하위 요소들에게도 적용됨
모든 부분에서 적용되는 것은 아님

1. font
   font-size
   font-weight
   font-style
   lint-height
   font-family
2. color
3. text-align
4. text-indent
5. text-decoration
6. letter-spacing
7. opacity

글자를 다루는 기본적인 속성들이 상속이 됨

### 강제 상속

```html
<div class="parent">
   <div class="child"></div>
</div>
```

position : inherit 으로 씀으로 인해 강제 상속을 할 수 있음

```css
.parent {
   position: absolute;
}
.child {
   position: inherit;
}
```

### 우선순위

같은 요소가 여러 선언의 대상이 될 경우

-  명시도 점수가 높은 선언이 우선(명시도)
-  점수가 같은 경우, 가장 마지막에 해석(늦게 작성)되는 선언이 우선 -> 선언순서
-  명시도는 '상속'규칙보다 우선(중요도)
-  !important 가 작용된 선언 방식이 다른 모든 방식보다 우선(중요도)
-  :hover - 가상 클래스

1. !important
   모든 선언을 무시하고 가장 우선
   점수 : 무한대
2. 인라인 선언 방식(Style Attribute)
   HTML style 속성을 사용
   점수 : 1000pt
3. 아이디 (Id Selector)
   아이디 선택자
   점수 : 100pt
4. 클래스 (Class Selector)
   클래스 선택자
   점수 : 10pt
   :hover 가상 클래스 10점
5. 태그 선택자(Type Selector)
   태그 선택자
   점수 : 1pt
   ::before - 가상 요소 1점
6. 전체(Universal Selector)
   전체 선택자
   점수 : 0pt
7. 상속(CSS Inheritance)
   상속 받은 속성은 항상 우선하지 않음
   점수 : 계산x
8. 부정 선택자
   선택자 부정
   점수 : 점수x

```css
div {
   color: red !important;
   /* ! important */
}
#color_yellow {
   color: yellow;
   /* 아이디 선택자 */
}
.color_green {
   color: green;
   /* 클래스 선택자 */
}
div {
   color: blue;
   /* 태그 선택자 */
}
* {
   color: darkblue;
   /* 전체선택자 */
}
body {
   color: violet;
   /* 상속 */
}
```

## 가상 클래스 선택자(Pseudo-Classes Selectors)

1. HOVER

설명 : E에 마우스(포인터)가 올라가 있는 동안에만 E 선택
E: hover

transition : 에니메이션 효과

2. ACTIVE

설명 : E를 마우스로 클릭하는 동안에만 E 선택
E: active
