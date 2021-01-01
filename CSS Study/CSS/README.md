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

- 단점 : 부모요소를 계속 따라가기 때문에 관리가 어려움

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

- 보는 페이지의 너비의 절반만 사용

### vh

설명 : viewport 세로 size(높이)
viewport height

- 보는 페이지의 높이의 절반만 사용

### vmin

설명 : 현재 더 짧은 길이를 따라감(width, height)

### vmax

설명 : 현재 더 넓은 길이를 따라감(widht, height)

### width

설명 : 요소의 가로너비를 지정

- inline 요소는 가로 세로 값을 가질 수 없음

* auto = 100%
  text에 특화됨
  |값 | 의미 |기본값|
  |---|----|---|
  |auto|브라우저가 너비를 계산|auto|
  |단위|px,em,cm 등 단위로 지정| |

### height

설명 : 요소의 세로너비를 지정

- auto = 0

* inline 요소는 가로 세로 값을 가질 수 없음
  text에 특화됨
  |값 | 의미 |기본값|
  |---|----|---|
  |auto|브라우저가 너비를 계산|auto|
  |단위|px,em,cm 등 단위로 지정| |

### max-width(height)

설명 : 요소의 최대 가로(세로) 너비를 지정

- 기본값이 none

| 값   | 의미                   | 기본값 |
| ---- | ---------------------- | ------ |
| 단위 | px,em,% 등 단위로 지정 | none   |
| auto | 브라우저가 너비를 계산 |        |

### min-width(height)

설명 : 요소의 최소 가로(세로) 너비를 지정

- 기본값이 0

| 값   | 의미                   | 기본값 |
| ---- | ---------------------- | ------ |
| 단위 | px,em,% 등 단위로 지정 | 0      |
| auto | 브라우저가 너비를 계산 |        |

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103406693-f1e27c00-4b9e-11eb-8563-88d02ec858ca.png)

### margin

설명 : 요소의 '외부(바깥) 여백'을 지정

- 음수 값 사용 가능

* %를 사용하면 부모 요소의 가로 너비를 따라감

| 값   | 의미                                | 기본값 |
| ---- | ----------------------------------- | ------ |
| 단위 | px,em,% 등 단위로 지정              | 0      |
| auto | 브라우저가 너비를 계산              |        |
| %    | 부모 요소의 너비에 대한 비율로 지정 |        |

- 위 에서 부터 시계 방향으로 해석
  margin : 위 우 아래 좌;
  margin : 위 [좌, 우], 아래;
  margin : [위 아래], [좌, 우];
  margin : [위,아래, 좌, 우];

#### 마진 중복(병합, Collapse)

설명 : 마진의 특정 값들이 중복되어 합쳐지는 현상

1. 형제 요소들의 margin-top과 margin-bottom이 만났을 때
2. 부모 요소의 margin-top과 자식 요소의 margin-top이 만났을 때
3. 부모 요소의 margin-bottom과 자식 요소의 margin-bottom이 만났을 때

- 마진중복은 버그가 아닌 현상을 우회 가능 또는 응용 가능

* 옆쪽으로는 중복이 안됨
* 위 아래의 margin은 중복됨
* 자식 요소의 margin-top 과 부모 요소의 margin-top이 만나면 margin이 중복이 된다.

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103433085-3f59fa00-4c2e-11eb-926b-243d7c38eb2c.png)

##### 마진 중복 계산법

설명 : 마진 중복 현상이 발생시, 중복 값 계산 법

| 조건             | 요소A 마진 | 요소 B 마진 | 계산법              | 중복값 |
| ---------------- | ---------- | ----------- | ------------------- | ------ |
| 둘 다 양수       | 30px       | 10px        | 더 큰 값으로 중복   | 30px   |
| 둘 다 음수       | -30px      | -10px       | 더 작은 값으로 중복 | -30px  |
| 각각 양수와 음수 | -30px      | 10px        | -30+10=-20          | -20px  |

### padding

설명 : 요소의 '내부(안) 여백'을 지정
단축

| 값   | 의미                                | 기본값 |
| ---- | ----------------------------------- | ------ |
| 단위 | px,em,cm 등 단위로 지정             | 0      |
| %    | 부모 요소의 너비에 대한 비율로 지정 |        |

- 위 에서 부터 시계 방향으로 해석
  padding : 위 우 아래 좌;
  padding : 위 [좌, 우], 아래;
  padding : [위 아래], [좌, 우];
  padding : [위,아래, 좌, 우];

```css
.box {
  padding: 10px 20px 30px 40px;
  padding: 10px 20px 40px;
  padding: 10px 40px;
  padding: 10px;
}
```

- 단축 속성과 개별 속성 존재

### padding 크기 증가

설명 : 추가된 padding 값 만큼 요소의 크기가 커지는 현상

- 자동 계산
  너비와 높이는 100으로 하면서 padding도 넣겠다
  content-box 내장하고 있음
  box-sizing: border-box; 추가

```css
div {
  width: 100px;
  height: 100px;
  background: tomato;
  padding: 10px 20px;
  box-sizing: border-box;
}
```

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103433178-16d2ff80-4c30-11eb-9eb4-556f6c0b292b.png)

### border

설명 : 요소의 '테두리 선'을 지정

속성 값

| 값           | 의미            | 기본값 |
| ------------ | --------------- | ------ |
| border-width | 선의 두께(너비) | medium |
| border-style | 선의 종류       | none   |
| border-color | 선의 색상       | black  |

- border : 두께 종류 색상;

```css
.box {
  border: 1px solid red;
}
```

#### border&#45;width

속성 값

| 값     | 의미                      | 기본값 |
| ------ | ------------------------- | ------ |
| medium | 중간 두께                 | medium |
| thin   | 얇은 두께                 |        |
| thick  | 두꺼운 두께               |        |
| 단위   | px, em, cm 등 단위로 지정 |        |

- 위 에서 부터 시계 방향으로 해석
  border-width : 위 우 아래 좌;
  border-width : 위 [좌, 우], 아래;
  border-width : [위 아래], [좌, 우];
  border-width : [위,아래, 좌, 우];

```css
.box {
  border-width: 10px 20px 30px 40px;
  border-width: 10px 20px 40px;
  border-width: 10px 40px;
  border-width: 10px;
}
```

#### border&#45;style

속성 값

| 값     | 의미                               | 기본값 |
| ------ | ---------------------------------- | ------ |
| none   | 선없음                             | none   |
| hidden | 선 없음과 동일(table 요소에서 사용 |        |
| solid  | 실선(일반 선)                      |        |
| dotted | 점선                               |        |
| dashed | 파선                               |        |
| double | 두 줄선                            |        |
| groove | 홈이 파여있는 모양(선)             |        |
| ridge  | 솟은 모양(선, groove)의 반대       |        |
| inset  | 요소 전체가 들어간 모양(선)        |        |
| outset | 요소 전체가 나온 모양(선)          |        |

- 위 에서 부터 시계 방향으로 해석
  border-width : 위 우 아래 좌;
  border-width : 위 [좌, 우], 아래;
  border-width : [위 아래], [좌, 우];
  border-width : [위,아래, 좌, 우];

```css
.box {
  border-width: solid dotted double inset;
  border-width: solid dotted inset;
  border-width: solid inset;
  border-width: solid;
}
```

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103433541-f6a63f00-4c35-11eb-98ba-f52e985bdd92.png)

#### border&#45;color

설명 : 선의 색상을 지정

속성 값

| 값          | 의미                            | 기본값 |
| ----------- | ------------------------------- | ------ |
| 색상        | 선의 색상을 지정                | black  |
| transparent | 투명한 선(요소의 배경색이 보임) |        |

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103433598-3f122c80-4c37-11eb-9143-dc1db27bbbdb.png)

기타 속성

| 속성                | 의미             | 사용값         |
| ------------------- | ---------------- | -------------- |
| border-top          | 위쪽 선          | 두께 종류 색상 |
| border-top-width    | 위쪽 선의 두께   | 두께           |
| border-top-style    | 위쪽 선의 종류   | 종류           |
| border-top-color    | 위쪽 선의 색상   | 색상           |
| border-bottom       | 아래쪽 선        | 두께 종류 색상 |
| border-bottom-width | 아래쪽 선의 두께 | 두께           |
| border-bottom-style | 아래쪽 선의 종류 | 종류           |
| border-bottom-color | 아래쪽 선의 색상 | 색상           |
| border-left         | 왼쪽 선          | 두께 종류 색상 |
| border-left-width   | 왼쪽 선의 두께   | 두께           |
| border-left-style   | 왼쪽 선의 종류   | 종류           |
| border-left-color   | 왼쪽 선의 색상   | 색상           |
| border-right        | 오른쪽 선        | 두께 종류 색상 |
| border-right-width  | 오른쪽 선의 두께 | 두께           |
| border-right-style  | 오른쪽 선의 종류 | 종류           |
| border-right-color  | 오른쪽 선의 색상 | 색상           |
