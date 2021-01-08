# HTML-CSS

웹 공부

## meta tag

-  viewport

1. width
   너비 : device-width
2. initial-scale
   초기화면 배율
3. user-scalable=no
   확대 축소 (스마트폰) x
   maximum-scale = 1, minimum-scale = 1
4. http-equiv
   최신의 표준 모드로 랜더링
5. property="og:type"
   og : 정보
   Open Graph 외부에 제공할 정보를 제공
   facebook 에서 사용

-  Twitter Card : twitter

### favicon

shortcut의 경우 root 경로에 위치하면 알아서 찾아줌

```html
<link rel="icon" href="./favicon.png" />
<link rel="apple-touch-icon" href="./favicon.png" />
<link rel="shortcut icon" type="image/x-icon" href="./favicon.ico" />
```

### 구글폰트

[font](https://fonts.google.com/)

### html \_\_ 언더바 두번

BEM 작명 규칙

1. \_\_
   자식요소라고 명시
   ~의 일부분
2. btn--success
   현재 **상태**를 나타냄
   btn--success
   btn--danger
3. 하이픈 한번(-)
   일반적인 css 규칙

### btn

inline-flex -> 필요한 만큼만 사용(텍스트 들어간 만큼만)
a tag
기본적으로 밑줄이 쳐짐
아래와 같이 해결

```css
a {
   text-decoration: none;
}
```

기본

```css
.btn {
   height: 60px;
   background: #eee linear-gradient(to bottom, #fcfcfc, #eee);
   border: 1px solid #d5d5d5;
   border-radius: 4px;
   display: inline-flex;
   align-items: center;
   padding: 0 12px;
   font-size: 14px;
   font-weight: 500;
   line-height: 1.5;
   /* 행간격 */
   cursor: pointer;
   /* 마우스 손 모양 */
   box-sizing: border-box;
}
.btn:hover {
}
```

### input

1. outline  
   사용 까다롭기 때문에 사용 x
2. box-sizing  
   -> 내용 늘어나도 박스 안커지게
3. box-shadow
   -  inset 사용시 안쪽에 생김
      x축 y축
4. focus
   box-shadow 는 , 통해서 색상 안쪽 바깥쪽 사용 가능
5. Vendor Prefix
   실험적 제공기능
   크롬 : webkit
   micro : ms
   firefox : moz

### Hexadecimal

반복 되는 6개는 3개로 축소 가능

### header .inner

inner의 높이가 정해지면 header도 높이가 정해짐

width 값이 정해져 있어야만 가운데 정렬이 가능함

```css
margin: 0 auto;
```

### padding 으로 클릭 여백 확보

a 테그에 삽입 해서 여백을 확보한다

```css
header .main-menu li a {
   display: block;
   padding: 10px;
   color: #3c4146;
}
```

### 이미지 대체 텍스트 삽입

text-indent 이용
-9999 -> 명시적 의미

```css
header .logo a {
   display: block;
   background: url(../img/logo.svg);
   width: 32px;
   height: 32px;
   text-indent: -9999px;
}
```

### float

공통적인 요소

common

### class 없이 다음 요소

```css
#search + [type='submit'] {
}
```
