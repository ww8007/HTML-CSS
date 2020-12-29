# 전역속성

### 전역속성(Global Attributes)

설명 : 모든 HTML에서 공통적으로 사용 가능한 속성

### class

설명 : 공백으로 구분된 요소의 별칭을 지정
CSS 혹은 JavaScript의 요소 선택기(CSS 선택자나 GetElementsByClassName, QuerySelectorAll 같은)를 통해서 요소를 선택하거나 접근.

-  별명을 설정

js 에서 class 찾는 코드

```html
<script>
   const section = document.querySelector(".section");
</script>
```

### id

문서에서 고유한 식별자(idenifier, ID)를 정의.
CSS 혹은 JavaScript의 요소 선택기(CSS 선택자나 GetElementsByClassName, QuerySelectorAll 같은)를 통해서 요소를 선택하거나 접근.

-  이름을 설정 <- 고유하다(한 곳에 하나만)

js 에서 id 찾는 코드

```html
<script>
   const sectionID = document.getElementById("section");
</script>
```

### style

설명 : 요소에 적용할 CSS를 선언

-  html에서 css를 바로 선언 가능

### title

설명 : 요소의 정보(설명)을 지정

-  부가 설명 지정하는 느낌

예제
![image](https://user-images.githubusercontent.com/54137044/103295581-a1044380-4a37-11eb-90da-6293b14dd103.png)

### lang

설명 : 요소의 언어(ISO 639-1)를 지정

-  일반적으로 한 번만 설정을 해주면 다른 곳에서 설정을 안해도 됨
   -> 다른 언어가 나올 때만 명시해줌

### data-\*

설명 : 사용자 정의 데이터 속성을 지정
HTML에서 JavaScript에서 이용할 수 잇는 데이터(정보)를 HTML에 저장하는 용도

예제
![image](https://user-images.githubusercontent.com/54137044/103297723-3f92a380-4a3c-11eb-8b98-f1b2d8793472.png)

### draggable

설명 : 요소가 Drag and Drop API를 사용 가능한지 여부를 지정

-  draggable 기본 값 : auto 이므로 설정하고 싶다면 true로 설정

```html
<div draggable="true">The element to drag.</div>
```

### hidden

설명 : 요소를 숨김

예제
![image](https://user-images.githubusercontent.com/54137044/103298166-1b839200-4a3d-11eb-9322-6973b9ea54a7.png)

```html
<form id="hidden-form" action="/form-action" hidden>
   <!-- 숨겨진 양식들.. -->
</form>
<button form="hidden-form" type="submit">전송</button>
```

### tabindex

설명 : Tab키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정

-  대화형 콘텐츠(Interactive Content)는 기본적으로 코드 순서대로 탭 순서가 지정됨
-  비대화형 콘텐츠에 tabindex="0"을 지정하여 대화형 콘텐츠와 같이 탭 순서를 사용
-  tabindex="-1"을 통해 포커스는 가능하지만 탭 순서에서 제외 가능
-  tabindex="1" 이상의 양수 값은 논리적 흐름을 방해하기 때문에 사용을 추천하지 않음

임의적으로는 순서를 굳이 바꿀 필요 없음

예제
![image](https://user-images.githubusercontent.com/54137044/103298795-6c47ba80-4a3e-11eb-8b90-af212045192e.png)
