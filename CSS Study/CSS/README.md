# CSS

---

### 부모 요소 자식 요소간 size

width 의 경우 부모의 px 단위에 영향을 받게 되므로 퍼센트 단위로 입력해도 무관

```css
body * {
   border: 2px solid;
}

.container {
   width: 600px;
}

.parent {
   width: 50%;
}

.child {
   width: 50%;
}
```

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103401464-43cdd680-4b8c-11eb-8368-42c24ea0c1d7.png)

## em, rm

### em

설명 : 자기 자신의 폰트 크기에 영향을 받음

-  단점 : 부모요소를 계속 따라가기 때문에 관리가 어려움

```css
body * {
   border: 2px solid;
}

.container {
   width: 600px;
   font-size: 10px;
}

.parent {
   width: 30em;
   font-size: 2em;
   /* 폰트 크기 부모로 부터 물려받아서 10px
    size = 10px*30 = 300px;
    */
}

.child {
   width: 15em;
   font-size: 2em;
}
```

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103401860-ffdbd100-4b8d-11eb-8c9f-63754ef44080.png)

### rem

설명 : html에 지정된 폰트 사이즈에만 영향을 받음

html 에서 10px 로 선언을 하고
body 에서 16px 로 따로 또 선언을 해서 사용 가능
-> 장점으로 사용 가능

```css
html {
   font-size: 10px;
}

body {
   font-size: 16px;
}

body * {
   border: 2px solid;
}

.container {
   width: 600px;
   font-size: 15px;
}

.parent {
   width: 30em;
   font-size: 2em;
}

.child {
   width: 20rem;
   font-size: 2em;
}
```
