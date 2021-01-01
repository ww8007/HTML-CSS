# 기본 css 설정

---

기본적으로 margin이나 padding이나 빈공간이 남는 경우가 생기게 된다

![image](https://user-images.githubusercontent.com/54137044/103399045-94d8cd00-4b82-11eb-9b76-7509e79b86f4.png)

이를 방지 하기 위해 reset.css를 불러와서 href로 연결해서 사용하게 되는데
[reset.css](https://www.jsdelivr.com/package/npm/reset-css)
여기서 reset.min.css를 불러와서 사용하면 모든 스타일이 초기화가 된다

```html
<link
   rel="stylesheet"
   href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css"
/>
```

![image](https://user-images.githubusercontent.com/54137044/103399096-c94c8900-4b82-11eb-936a-9f6e1b5c13c2.png)

## codepen

[codepen]https://codepen.io/

-  codepen reset 설정
   ![image](https://user-images.githubusercontent.com/54137044/103399437-812e6600-4b84-11eb-8b37-bbd65380d8cb.png)

-  codepen 기본 셋팅 완료

![image](https://user-images.githubusercontent.com/54137044/103399421-7247b380-4b84-11eb-8f08-c5f654514b0b.png)

## Emmet 문법

[Emmet](https://emmet.io/)

단축어 같은 느낌(유용하게 사용가능)
tag를 만들 때 많이 사용
기본 내장되어 있음으로 따로 설치는 필요 없음

-  .box + tab
   box 라는 클래스의 div tag 생성
-  ul.list
   ul tag 이면서 class = list
   tag 선택자
-  css h100
   height = 100px;
