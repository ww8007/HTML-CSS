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

### vw

설명 : viewport 가로 size(너비)
viewport width

-  보는 페이지의 너비의 절반만 사용

### vh

설명 : viewport 세로 size(높이)
viewport height

-  보는 페이지의 높이의 절반만 사용

### vmin

설명 : 현재 더 짧은 길이를 따라감(width, height)

### vmax

설명 : 현재 더 넓은 길이를 따라감(widht, height)

### width

설명 : 요소의 가로너비를 지정

-  inline 요소는 가로 세로 값을 가질 수 없음

*  auto = 100%
   text에 특화됨
   |값 | 의미 |기본값|
   |---|----|---|
   |auto|브라우저가 너비를 계산|auto|
   |단위|px,em,cm 등 단위로 지정| |

### height

설명 : 요소의 세로너비를 지정

-  auto = 0

*  inline 요소는 가로 세로 값을 가질 수 없음
   text에 특화됨
   |값 | 의미 |기본값|
   |---|----|---|
   |auto|브라우저가 너비를 계산|auto|
   |단위|px,em,cm 등 단위로 지정| |

### max-width(height)

설명 : 요소의 최대 가로(세로) 너비를 지정

-  기본값이 none

| 값   | 의미                   | 기본값 |
| ---- | ---------------------- | ------ |
| 단위 | px,em,% 등 단위로 지정 | none   |
| auto | 브라우저가 너비를 계산 |        |

### min-width(height)

설명 : 요소의 최소 가로(세로) 너비를 지정

-  기본값이 0

| 값   | 의미                   | 기본값 |
| ---- | ---------------------- | ------ |
| 단위 | px,em,% 등 단위로 지정 | 0      |
| auto | 브라우저가 너비를 계산 |        |

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103406693-f1e27c00-4b9e-11eb-8563-88d02ec858ca.png)

### margin

설명 : 요소의 '외부(바깥) 여백'을 지정

-  음수 값 사용 가능

*  %를 사용하면 부모 요소의 가로 너비를 따라감

| 값   | 의미                                | 기본값 |
| ---- | ----------------------------------- | ------ |
| 단위 | px,em,% 등 단위로 지정              | 0      |
| auto | 브라우저가 너비를 계산              |        |
| %    | 부모 요소의 너비에 대한 비율로 지정 |        |

margin : 위 우 아래 좌;
margin : 위 [좌, 우], 아래;
margin : [위 아래], [좌, 우];
margin : [위,아래, 좌, 우];

#### 마진 중복(병합, Collapse)

설명 : 마진의 특정 값들이 중복되어 합쳐지는 현상

1. 형제 요소들의 margin-top과 margin-bottom이 만났을 때
2. 부모 요소의 margin-top과 자식 요소의 margin-top이 만났을 때
3. 부모 요소의 margin-bottom과 자식 요소의 margin-bottom이 만났을 때

-  마진중복은 버그가 아닌 현상을 우회 가능 또는 응용 가능
