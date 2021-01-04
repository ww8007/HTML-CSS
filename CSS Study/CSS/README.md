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

**속성 값**

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

**속성 값**

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

**속성 값**

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

**속성 값**

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
![image](https://user-images.githubusercontent.com/54137044/103433783-bbf2d580-4c3a-11eb-9e0a-756067ea47b6.png)

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

설명 : 요소의 크기 계산 기준을 지정

- 주의사항
  border 도 동일하게 두꼐이므로 padding, margin과 동일하게 크기에 영향을 끼침
  -> box-sizing : border-box; 추가 함으로써 해결

```css
.box {
  box-sizing: border-box;
}
```

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103434056-2279f280-4c3f-11eb-8032-59bbdaff362c.png)

### box&#45;sizing

| 값          | 의미                                                                                       | 기본값      |
| ----------- | ------------------------------------------------------------------------------------------ | ----------- |
| content-box | 너비(width, height)만으로 요소의 크기를 계산                                               | content-box |
| border-box  | 너비(width, height)에 안쪽 여백(padding)과 테두리 선(border)를 포함하여 요소의 크기를 계산 |             |

### display

설명 : 요소의 박스타입(유형)을 설정

**속성 값**

| 값     | 의미                                   | 기본값 |
| ------ | -------------------------------------- | ------ |
| block  | 블록 요소( &#60;div&#60; 등)           |        |
| inline | 인라인 요소(&#60;span&#62;등)          |        |
| inline | 인라인-블록 요소(&#60;input&#62; 등)   |        |
| 기타   | table,table-cell,flex 등               |        |
| none   | 요소의 박스 타입이 없음(요소가 사라짐) |        |

- inline-block
  기본 요소는 inline 이지만 inline이 가지지 못하는 가로 세로 값을 가지도록 함
- none 화면에서 사라지게 함
  존재하지 않도록 함
  -> opacity = 0;와는 다른 개념

[example]
![image](https://user-images.githubusercontent.com/54137044/103434200-450d0b00-4c41-11eb-8001-e771f8058c10.png)

- display : none

[normal]<br>
![image](https://user-images.githubusercontent.com/54137044/103434284-8651ea80-4c42-11eb-8ba4-24b31fa47230.png)
<br>
[none]<br>
![image](https://user-images.githubusercontent.com/54137044/103434356-b8b01780-4c43-11eb-9993-eaf05da41bbc.png)

### overflow

설명 : 요소의 크기 이상으로 내용(자식요소)이 넘쳤을 때, 내용의 보여짐을 제어

**속성 값**

| 값      | 의미                                                                  | 기본값  |
| ------- | --------------------------------------------------------------------- | ------- |
| visible | 넘친 부분을 자르지 않고 그대로 보여줌                                 | visible |
| hidden  | 넘친 부분을 잘라내고, 보이지 않도록 함                                |         |
| scroll  | 넘친 부분을 잘래나고, 스크롤바를 이용하여 볼 수 있도록 함             |         |
| atuo    | 넘친 부분이 있는 경우만 잘라내고, 스크롤바를 이용하여 볼 수 있도록 함 |         |

- scroll - 강제로 스크롤 바 생성
  [scroll]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103434482-3aed0b80-4c45-11eb-87e3-936e4a4aa5bd.png)

- auto - 자동으로 스크롤 바 생성
  [auto]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103434491-5821da00-4c45-11eb-93ff-e4c536ebbc55.png)

### opacity

설명 : 요소의 투명도를 지정

**속성 값**

| 값   | 의미                        | 기본값 |
| ---- | --------------------------- | ------ |
| 숫자 | 0 부터 1 사이의 소수점 숫자 | 1      |

opacity : 투명도;

- opacity와 display : none 차이는
- opacity - 존재하지만 보이지 않음
  [opacity0]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103434601-1abe4c00-4c47-11eb-8d22-669ee28f0acc.png)
- display : none - 존재 자체를 소멸
  [none]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103434586-f9f5f680-4c46-11eb-8d16-88f43e9748f7.png)

### font

설명 : 글자 관련 속성들을 지정

**속성 값**

| 값          | 의미                 | 기본값                           |
| ----------- | -------------------- | -------------------------------- |
| font-style  | 글자 기울기 지정     | normal                           |
| font-weight | 글자 두께 지정       | normal                           |
| font-size   | 글자 크기 지정       | medium(16px)                     |
| line-height | 줄 높이(줄 간격)지정 | normal(Reset.css적용시 1)        |
| font-family | 글꼴(서체)지정       | 운영체제(브라우저)에 따라 달라짐 |

- font : 기울기 두께 크기 / 줄높이 글꼴
- /붙는 이유는 크기 와 줄높이 구분하기 위해서
- 단축 속성 사용하기 위해 font-size와 font-family는 필수
  크기와 글꼴

```css
.box {
  font: italic bold 20px / 1.5 'Arial', sans-serif;
}
```

### font&#45;style

설명 : 글자 스타일(기울기) 지정

**속성 값**

| 값      | 의미           | 기본값 |
| ------- | -------------- | ------ |
| normal  | 스타일 없음    | normal |
| italic  | 이텔릭체(활자) |        |
| oblique | 기울어진 글자  |        |

- 보통의 경우에는 italic 활용

![image](https://user-images.githubusercontent.com/54137044/103450466-32a2d800-4cfa-11eb-9e89-1ac337502f7e.png)

### font-weight

설명 : 글자의 두께(가중치)를 지정

| 값      | 의미                                                                                              | 기본값      |
| ------- | ------------------------------------------------------------------------------------------------- | ----------- |
| normal  | 기본 글자 두께, 400과 동일                                                                        | normal(400) |
| bold    | 글자 두껍게, 700과 동일                                                                           |             |
| bolder  | 부모(상위)요소보다 더 두껍게(bold 보다 두껍다의 개념은 x)                                         |             |
| lighter | 부모(상위) 요소보다 더 얇게                                                                       |             |
| 숫자    | 100부터 900 까지의 100 단위 숫자 9개, normal과 bold 이외의 두께를 제공하는 글꼴(서체)를 위한 설정 |             |

- 가장 많이 입력하는 것은 숫자
  normal : 400
  bold : 700

**일반적인 두께의 이름**

font-weight의 각 값은 일반적으로 다음과 같은 글꼴의 이름으로 표현됨

| 값  | 일반적인 두께 이름       |
| --- | ------------------------ |
| 100 | Thin(Hairline)           |
| 200 | Extra Light(Ultra Light) |
| 300 | Light                    |
| 400 | Normal                   |
| 500 | Medium                   |
| 600 | Semi Bold(Demi Bold)     |
| 700 | Bold                     |
| 800 | Extra Bold(Ultra Bold)   |
| 900 | Black (Heavy)            |

**상대적 두께**

bolder 나 lighter를 사용할 경우 부모(상위) 요소에게 상속받은 값에서 다음과 같이 계산됨

| 상속값 | bolder | ligther |
| ------ | ------ | ------- |
| 100    | 400    | 100     |
| 200    | 400    | 100     |
| 300    | 400    | 100     |
| 400    | 700    | 100     |
| 500    | 700    | 100     |
| 600    | 900    | 400     |
| 700    | 900    | 400     |
| 800    | 900    | 700     |
| 900    | 900    | 700     |

**숫자 값과 두께의 불일치**

글꼴(서체)의 정확한 두께를 숫자로 표현할 수 없는 경우

1. 400이 주어지면 500 사용, 500이 불가하면 500미만 다른 두께 사용
2. 500이 주어지면 400을 사용, 400이 불가하면 400 미만 다른 두께 사용
3. 400미만 값이 주어지면, 가장 가까운 얇은 두께 사용
4. 500 초과 값이 주어지면, 가장 가까운 숫자의 두꺼운 두께 사용

### font-size

설명 : 글자의 크기를 지정

| 값       | 의미                          | 기본값 |
| -------- | ----------------------------- | ------ |
| 단위     | px, em, cim 등 단위로 지정    | 16px   |
| %        | 부모(상위) 요소의 비율로 지정 |        |
| xx-small | 가장 작은 크기                |        |
| x-small  | 더 작은 크기                  |        |
| small    | 작은 크기                     |        |
| medium   | 중간 크기                     | medium |
| large    | 큰 크기                       |        |
| x-large  | 더 큰 크기                    |        |
| xx-large | 가장 큰 크기                  |        |
| smaller  | 부모(상위)요소보다 작은 크기  |        |
| larger   | 부모(상위)요소보다 큰 크기    |        |

- %는 em으로 대체 해서 쓰는 것이 좋음
- %밑의 값들은 불명확 함으로 크기가 지정된 단위를 사용하는 것이 더 좋음

body tag의 font-size 변경 시 모든 문서의 기본 폰트 크기 변경 됨

### line-height

설명 : 줄 높이(줄 간격 지정)

| 값     | 의미                               | 기본값 |
| ------ | ---------------------------------- | ------ |
| normal | 브라우저의 기본 정의를 사용(1~1.4) | normal |
| 숫자   | 요소 자체 글꼴 크기의 배수로 지정  |        |
| 단위   | px,em,cm 등 단위로 지정            |        |
| %      | 요소 자체 글꼴 크기의 비율로 지정  |        |

- line-height는 글자 크기 + 글자 위, 아래 여백이다.
- 숫자 개념의 배수로 들어가는 것이 더 효과적인 부분도 존재
  1.4 ~ 1.7 (보통) -> font의 종류에 따라 바뀔 수 있음

```css
div {
  font-size: 20px;
  line-height: 1.4;
}
```

### font-family

설명 : 글꼴(서체) 지정

**속성 값**

| 값         | 의미                        | 기본값 |
| ---------- | --------------------------- | ------ |
| 글꼴이름   | 글꼴(서체) 후보 목록을 지정 |        |
| serif      | 글꼴 이름을 지정            |        |
| sans-serif |                             |        |
| monospace  |                             |        |
| cursive    |                             |        |
| fantasy    |                             |        |

```css
.box {
  font-family: Arial, 'Open Sans', '돋움', dotum, sans-serif;
}
```

- 폰트의 경우 용량이 웹 치고는 크다 -> 해당 폰트가 사용자 기기에 있는지 확인하고
  쓰는 형식으로 한다.
- 계열을 넣는 이유는 앞 글꼴 후보 중 아무것도 없을 시 계열을 쓰도록 함

**글꼴 계열**

| 계열       | 의미                                           |
| ---------- | ---------------------------------------------- |
| serif      | 바탕체 계열                                    |
| sans-serif | 고딕체 계열                                    |
| monosapce  | 고정너비(가로폭이 동등한)글꼴 계열             |
| cursive    | 필기체 계열                                    |
| fantasy    | wkdtlr(재미있는 문자 표현을 포함하는)글꼴 계열 |

- sans-serif 가장 많이 사용
- monospace -> 개발환경에서 많이 사용

![image](https://user-images.githubusercontent.com/54137044/103451053-713c9080-4d02-11eb-8d22-8bbaed0e538f.png)

## 문자(Text)관련 속성

### color

설명 : 문자의 색상을 지정

**속성 값**

| 값   | 의미               | 기본값     |
| ---- | ------------------ | ---------- |
| 색상 | 문자의 색상을 지정 | rgb(0,0,0) |

**색상 표현**

|표현|의미|예시|
|색상이름|브라우저에서 제공하는 색상의 이름|red,blue|
|Hex색상코드|16 진수 색상(Hexadecimal Colors)|#000000|
|RGB|빛의 삼원색|rgb(255,255,255)|
|RGBA|빛의 삼원색, 투명도|rgba(255, 0, 0, .5)|
|HSL|색상, 채도, 명도|hsl(120, 100%, 50%)|
|HSLA|색상, 채도, 명도, 투명도|hsla(120, 100%, 50%, .3)|

- 색상이름으로 하는 것은 피하는게 좋음

### text-align

설명 : 문자 정렬 방식 지정

**속성 값**

| 값      | 의미        | 기본값 |
| ------- | ----------- | ------ |
| left    | 왼쪽 정렬   |        |
| right   | 오른쪽 정렬 |        |
| center  | 가운데 정렬 |        |
| justify | 양쪽 맞춤   |        |

- justify - 두 줄 이상
  br 테그를 이용한 의도적인 줄바꿈에서는 적용되지 않음

### text-indent

설명 : (첫번째 줄의)둘여쓰기를 지정

- 음수 값 사용 가능
- 음수 값 사용 시 왼쪽으로 들여쓰기 됨

### text-decoration

설명 : 문자의 선에 대한 장식을 설정

**속성 값**

| 값           | 의미                       | 기본값 |
| ------------ | -------------------------- | ------ |
| none         | 선 없음                    | none   |
| underline    | 밑줄을 지정                |        |
| overline     | 윗줄을 지정                |        |
| line-through | 중앙 선(가로지르는)을 지정 |        |

[example]
![image](https://user-images.githubusercontent.com/54137044/103451507-2160c800-4d08-11eb-8529-696f156d8d9c.png)

### letter-spacing

설명 : 문자의 자간(글자 사이 간격)을 설정

**속성 값**

| 값     | 의미                        | 기본값 |
| ------ | --------------------------- | ------ |
| normal | 단어 사이의 일반 간격       | normal |
| 단위   | px, em, cm 등의 단위로 지정 |        |

### word-spacing

설명 : 단어 사이(띄어쓰기)의 간격을 설정

| 값     | 의미                        | 기본값 |
| ------ | --------------------------- | ------ |
| normal | 단어 사이의 일반 간격       | normal |
| 단위   | px, em, cm 등의 단위로 지정 |        |

- 띄어쓰기 기본에 +하기 개념으로 적용
  띄어쓰기 간격을 설정하는 개념이 아님

### float

설명 : 요소를 좌우 방향으로 띄움(수평 정렬)

css3 flexbox 적용

**속성 값**

| 값    | 의미            | 기본값 |
| ----- | --------------- | ------ |
| none  | 요소 띄움 없음  | none   |
| left  | 왼쪽으로 띄움   |        |
| right | 오른쪽으로 띄움 |        |

- 요소에 float 속성을 적용하면 적용된 요소 주변으로 문자가 흐름
- 기본의 경우 box 형식으로 쌓임

* clear: left 적용함으로서 밑의 단에 새로 시작하게 할 수 있음
  [example]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103451664-1f980400-4d0a-11eb-9ed3-b9370bd2e248.png)

1. none<nr>
   ![image](https://user-images.githubusercontent.com/54137044/103451712-a1882d00-4d0a-11eb-8904-455cfc845e0e.png)
2. left<br>
   ![image](https://user-images.githubusercontent.com/54137044/103451719-b82e8400-4d0a-11eb-8180-573ea9d8d4c1.png)
3. right<br>  
   순서도 뒤바뀜(우측부터 쌓음)
   ![image](https://user-images.githubusercontent.com/54137044/103451725-caa8bd80-4d0a-11eb-8311-fe9fac9d2b23.png)

#### float 해제

float 속성이 적용된 요소의 주위로 다른 요소들이 이를 방지하기 위해 속성을 해제 해야 함

1. 형제 요소에 clear: (left,right, both)추가하여 해제
   - 문제점 : 항시 다음 형제 요소를 만들어줘야 함
2. 부모 요소에 overflow: (hidden, auto)추가하여 해제

- 에전에 유행했던 방법
- 부모요소 rapping
- 문제점 : overflow와 float은 아무 상관이 없는데 편법

3. 부모 요소에 clearfix 클래스 추가하여 하제(추천!)

- clear를 통한 초기화를 꼭 해줘야 함
- clear-fix가 존재하는 자식 요소들은 float이 무조건 존재 해야함
  ![image](https://user-images.githubusercontent.com/54137044/103451788-69cdb500-4d0b-11eb-8860-4fe4510b0347.png)

```html
<div class="parent clearfix">
  <div class="child"></div>
  <div class="child"></div>
</div>
```

```css
.clearfix::after {
  content: '';
  clear: both;
  display: block;
  /* (or table) */
}
.child {
  float: left;
}
```

### float - display 수정

설명 : float 속성이 추가된 요소는 display 속성 값이 대부분 block으로 수정

- float 추가 시 자연스레 display : block 되기 때문에 명시 필요 x

| 지정값             | 변화값                            |
| ------------------ | --------------------------------- |
| inline             | block                             |
| inline-block       | block                             |
| inline-table       | block                             |
| table-row          | block                             |
| table-row-group    | block                             |
| table-column       | block                             |
| table-column-group | block                             |
| table-cell         | block                             |
| table-caption      | block                             |
| table-header-group | block                             |
| table-footer-group | block                             |
| flex               | flex /float 속성 효과 없음        |
| inline-flex        | inline-flex/ float 속성 효과 없음 |
| 그외               | 변화없음                          |

- css3 display-flex, display-inline-flex
- 많은 경우에 float 들어가면 block으로 바뀜

### clear

설명 : float 속성이 적용되지 않도록 해제

**속성 값**

| 값    | 의미                              | 기본값 |
| ----- | --------------------------------- | ------ |
| none  | 요소 띄움 허용                    | none   |
| left  | 왼쪽 띄움 해제                    |        |
| right | 오른쪽 띄움 해제                  |        |
| both  | 양쪽(왼쪽, 오른쪽) 모두 띄움 해제 |        |

- left, right 따로 명시 할 필요 없이 both를 통한 해제

### position

설명 : 요소의 위치 지정 방법의 유형(기준) 설정

**속성 값**

| 값       | 의미                              | 기본값 |
| -------- | --------------------------------- | ------ |
| static   | 유형(기준) 없음/ 배치 불가능      | static |
| relative | 요소 자신을 기준으로 배치         |        |
| absolute | 위치 상 부모 요소를 기준으로 배치 |        |
| fixed    | 브라우저(뷰포트)를 기준으로 배치  |        |
| sticky   | 스크롤 영역 기준으로 배치         |        |

- relative는 전과 후의 값에 영향을 받기 때문에 주의해서 써야함
  -> absolute를 쓰는 편이 더 나음

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103473024-6acc1880-4dd7-11eb-9941-a9dafa880fa0.png)

---

1. relative
   ![image](https://user-images.githubusercontent.com/54137044/103473161-bb904100-4dd8-11eb-8f83-92f019afcce1.png)

---

2. absolute

- 부모 요소의 position이 무조건 적으로 존재 해야함
- static의 경우는 해당 x
  -> 보통의 경우는 position : relative
- 바로 상위 부모 요소가 아니더라도 position이 존재 하는 경우까지 올라감
  모두 없을 경우는 뷰포트 까지 올라가게됨
  ![image](https://user-images.githubusercontent.com/54137044/103473324-9b618180-4dda-11eb-941b-7a1d669233b4.png)

---

3. fixed

- 브라우저의 상단 배너 같은 느낌으로 어느 위치에 계속 고정
  ![image](https://user-images.githubusercontent.com/54137044/103473427-b8e31b00-4ddb-11eb-93e1-2231fb8b15b3.png)

---

4. sticky

- 스크롤 영역 기준으로 배치
- position과 같이 사용되는 값
- 원래는 javascript를 이용하여 구현하여야 하지만 간단하게 sticky로 사용 가능
  ![image](https://user-images.githubusercontent.com/54137044/103473695-c2ba4d80-4dde-11eb-8b4d-13e1d5574e73.png)

  1. top
  2. bottom
  3. left
  4. right

  ## position 이 지정 되어 있을 때만 속성 사용가능

  ### top

  설명 : 요소의 position 기준에 맞는 '위쪽' 에서의 거리(위치)를 설정
  | 값 | 의미 | 기본값 |
  | -------- | --------------------------------- | ------ |
  |auto|브라우저가 계산|auto|
  |단위|px, em, cm 등 단위로 지정|**0**|
  |%|부모(위치 상의 부모(조상))요소의 세로 너비의 비율로 지정, **음수** 값 허용|

  ### bottom

  설명 : 요소의 position 기준에 맞는 '아래쪽' 에서의 거리(위치)를 설정
  | 값 | 의미 | 기본값 |
  | -------- | --------------------------------- | ------ |
  |auto|브라우저가 계산|auto|
  |단위|px, em, cm 등 단위로 지정|**0**|
  |%|부모(위치 상의 부모(조상))요소의 세로 너비의 비율로 지정, **음수** 값 허용|

  ### left

  설명 : 요소의 position 기준에 맞는 '왼쪽' 에서의 거리(위치)를 설정
  | 값 | 의미 | 기본값 |
  | -------- | --------------------------------- | ------ |
  |auto|브라우저가 계산|auto|
  |단위|px, em, cm 등 단위로 지정|**0**|
  |%|부모(위치 상의 부모(조상))요소의 가로 너비의 비율로 지정, **음수** 값 허용|

  ### right

  설명 : 요소의 position 기준에 맞는 '오른쪽' 에서의 거리(위치)를 설정
  | 값 | 의미 | 기본값 |
  | -------- | --------------------------------- | ------ |
  |auto|브라우저가 계산|auto|
  |단위|px, em, cm 등 단위로 지정|**0**|
  |%|부모(위치 상의 부모(조상))요소의 가로 너비의 비율로 지정, **음수** 값 허용|

  ### 요소 쌓임 순서(Stack order)

  설명 : 요소가 쌓여 있는 순서를 통해 어떤 요소가 사용자와 가깝게 있는지 (더 위에 쌓이는지)를 결정(Z축)

  1. stactic을 제외한 position 속성의 값이 있을 경우 가장 위에 쌓임 값은 무관
  2. position이 모두 존재한다면 z-index 속성의 숫자 값이 높을 수록 위에 쌓임
  3. position 속성의 값이 있고 z-index 속성의 숫자 값이 같다면 'HTML' 마지막 코드 일 수록 위에 쌓임(나중에 작성한 코드(요소))

  - z-index
    position이 있을 때만 효력 발생
    기본값 0
    [example]<br>
    ![image](https://user-images.githubusercontent.com/54137044/103473873-825bcf00-4de0-11eb-8a3a-ac2271195850.png)

  ### display 수정

  설명 : absolute, fixed 속성 ㄱ밧이 적요오딘 요소는 displya 속성의 값이 대부분 block으로 수정됨
  | 지정값 | 변화값 |
  | ------------------ | --------------------------------- |
  | inline | block |
  | inline-block | block |
  | inline-table | block |
  | table-row | block |
  | table-row-group | block |
  | table-column | block |
  | table-column-group | block |
  | table-cell | block |
  | table-caption | block |
  | table-header-group | block |
  | table-footer-group | block |
  | flex | flex /float 속성 효과 없음 |
  | inline-flex | inline-flex/ float 속성 효과 없음 |
  | 그외 | 변화없음 |

### background

설명 : 요소의 배경을 설정
background : 색상 이미지경로 반복 위치 스크롤특성;

**속성 값**

| 값                    | 의미                            | 기본값      |
| --------------------- | ------------------------------- | ----------- |
| background-color      | 배경 색상                       | transparent |
| background-image      | 하나 이상의 배경 이미지         | none        |
| background-repeat     | 배경 이미지의 반복              | repeat      |
| background-position   | 배경 이미지의 위치              | 0 0         |
| background-attachment | 배경 이미지의 스크롤 여부(특성) | scroll      |

### background-color

설명 : 요소의 배경 색상을 지정

**속성 값**

| 값          | 의미             | 기본값      |
| ----------- | ---------------- | ----------- |
| 색상        | 요소의 배경 색상 |             |
| transparent | 투명             | transparent |

- 기본적으로 배경색은 투명
- 계속 작성해왔던 background : tomato 의 단축속성으로 사용했던 것 임

[background-color]<br>
![image](https://user-images.githubusercontent.com/54137044/103473979-3d389c80-4de2-11eb-8604-e2fcf0181b8e.png)

### background-image

설명 : 요소의 배경에 하나 이상의 이미지를 삽입

**속성 값**
| 값 | 의미 | 기본값 |
| ----------- | ---------------- | ----------- |
|none|이미지 없음|none|
|url("경로")|이미지 경로)(URL)| |

- 하나 이상의 배경 이미지 삽입 경우 ,(콤마)로 구분
- 먼저 작성된 이미지가 더 위에 쌓이게 됨
- IE8 이하 버전 사용 불가

[background-image]<br>
![image](https://user-images.githubusercontent.com/54137044/103474228-0a43d800-4de5-11eb-9a72-6b3d7e128192.png)

### background-repeat

설명 : 배경 이미지의 반복을 설정

**속성 값**

| 값        | 의미                            | 기본값 |
| --------- | ------------------------------- | ------ |
| repeat    | 배경 임지를 수직, 수평으로 반복 | repeat |
| repeat-x  | 배경 이미지를 수평으로 반복     |        |
| repeat-y  | 배경 이미지를 수직으로 반복     |        |
| no-repeat | 반복 없음                       |        |

### background-position

**속성 값**

| 값   | 의미                                                       | 기본값 |
| ---- | ---------------------------------------------------------- | ------ |
| %    | 왼쪽 상단 모서리는 0% 0%, <br>오른쪽 하단 모서리는 100%    | 0% 0%  |
| 방향 | 방향을 입력하여 위치 설정 top, bottom, left, right, center |        |
| 단위 | px,em,cm 등 단위로 지정                                    |        |

- center는 한번만 입력해도 됨
- backround-position은 아래나 오른쪽 부터의 거리는 설정 불가

**사용법**

값이 방향

```css
background-position: 방향1 방향2;
```

값이 단위(%, px등)일 경우

```css
background-position: x축 y축;
```

[example]<br>
![image](https://user-images.githubusercontent.com/54137044/103475401-30bb4080-4df0-11eb-8d38-24284dd24122.png)

### background-attachment

설명 : 요소가 스크롤될 때 배경 이미지의 스크롤 여부(특성) 설정

**속성 값**

| 값     | 의미                                                                   | 기본값 |
| ------ | ---------------------------------------------------------------------- | ------ |
| scroll | 배경 이미지가 요소를 따라서 같이 스크롤 됨                             | scroll |
| fixed  | 배경 이미지가 뷰포트(Viewport)에 고정되어, 요소와 같이 스크롤되지 않음 |        |
| local  | 요소 내 스크롤 시 배경 이미지가 같이 스크롤 됨                         |        |

[example] <br>
![image](https://user-images.githubusercontent.com/54137044/103476090-1ab07e80-4df6-11eb-8324-5d31fa50367b.png)

- local로 설정하면 스크롤 바에 따라서 같이 움직임
  -> 이렇게 사용하는 경우는 많이 없음
  [example]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103476291-ba224100-4df7-11eb-855a-84c8ca16cb30.png)

### background-size

| 값      | 의미                                                                                                                           | 기본값 |
| ------- | ------------------------------------------------------------------------------------------------------------------------------ | ------ |
| auto    | 배경 이미지가 원래의 크기로 표시됨                                                                                             | auto   |
| 단위    | px, em, %등 단위로 지정<br> width, height 형태로 입력가능(E.g. 120px 270px)<br>width만 입력하면 비율에 맞게 지정됨(E.g. 120px) |        |
| cover   | 배경 이미지의 크기 비율을 유지하며, 요소의 더 넓은 너비에 맞춰짐<br>이미지가 잘릴 수 있음                                      |        |
| contain | 배경 이미지의 크기 비율을 유지하며, 요소의 더 짧은 너비에 맞춰짐<br> 이미지가 잘리지 않음                                      |        |

- 정확한 size의 값을 알고 있는 것이 아니라면 비율에 맞게 가로 사이즈만 입력하는 것도 좋은 방법이다.
- cover 긴 너비에 맞춤
- contain 짧은 너비에 맞춤

### Transitions

설명 : css 속성의 시작과 끝을 지정 (전환 효과)하여 중간 값을 애니메이션

| 값                         | 의미                        | 기본값 |
| -------------------------- | --------------------------- | ------ |
| transition-property        | 전환효과를 사용할 속성 이름 | all    |
| transition-duration        | 전환 효과의 지속시간을 설정 | 0s     |
| transition-timing-function | 타이밍 함수 지정            | ease   |
| transition-delay           | 전환 효과의 대기시간 설정   | 0s     |

- transition은 바뀌기 전 상태에 입력

* 타이밍 함수
  빠르기를 정함

  #### transition-property

  설명 : 전환 효과를 사용할 속성 이름을 설정

  |값|의미|기본값|
  |all|모든 속성에 적용|all|
  |속성이름|전환 효과를 사용할 속성 이름 | |

  #### transition-duration

  설명 : 전환 효과의 지속시간을 설정

  |값|의미|기본값|
  |시간|전환 효과가 지속되는 시간|0s|

  #### transition-timing-function

  설명 : 타이밍 함수(애니메이션 전환 효과를 계산하는 방법)지정

  | 값                    | 의미                    | 기본값 | Cubic Bezier 값               |
  | --------------------- | ----------------------- | ------ | ----------------------------- |
  | ease                  | 빠르게-느리게           | ease   | cubic-bezier(.25, .1, .25, 1) |
  | linear                | 일정하게                |        | cubic-bezier(0, 0, 1, 1)      |
  | ease-in               | 느리게-빠르게           |        | cubic-bezier(.42, 0, 1, 1)    |
  | ease-out              | 빠르게-느리게           |        | cubic-bezier(0, 0, .58, 1)    |
  | ease-in-out           | 느리게-빠르게-느리게    |        | cubic-bezier(0, 0, .58, 1)    |
  | cubic-bezier(n,n,n,n) | 자신만의 값을 정의(0~1) |        |                               |
  | steps(n)              | n 번 분활된 애니메이션  |        |                               |

  - cubic-bezier 사용자 보다 브라우저가 더 편리하게 알아들을 수 있음

  ### transition-delay

  설명 : 전환 효과가 몇 초 뒤에 시작할지 대기시간을 설정

  | 값   | 의미                        | 기본값 |
  | ---- | --------------------------- | ------ |
  | 시간 | 전환 효과의 대기시간을 설정 | 0s     |

### transform

설명 : 요소의 변환 효과(변형)를 지정

transform: 변환함수1 변환함수2 변환함수3...;
transform : 원근법 이동 크기 회전 기울임;

```css
.box {
  transform: rotate(20deg) translate (10px, 0);
}
```

- 변형 효과에는 2d와 3d 개념 존재

#### transform 2D 변환 함수

| 값(변환함수)        | 의미             | 단위       |
| ------------------- | ---------------- | ---------- |
| translate(x, y)     | 이동(X축, Y축)   | 단위       |
| translate(x)        | 이동(X축)        | 단위       |
| translate(y)        | 이동(Y축)        | 단위       |
| scale(x, y)         | 크기(X축, Y축)   | 없음(배수) |
| scaleX(x)           | 크기(X축)        | 없음(배수) |
| scaleY(y)           | 크기(Y축)        | 없음(배수) |
| rotate(degree)      | 회전(각도)       | deg        |
| skew(x-deg, y-deg)  | 기울임(X축, Y축) | deg        |
| skew(x-deg)         | 기울임(X축)      | deg        |
| skew(y-deg)         | 기울임(Y축)      | deg        |
| matrix(n,n,n,n,n,n) | 2차원 변환 효과  | 없음       |

- matrix() -> 일반적으로 사용하기에는 어려움이 있음
  -> translate, scale, rotate, skew를 사용해서 명시적으로 사용

* 배치하고 끝내는 상황이면 **position** 적용
  이동하면서 계속 상호작용 필요하다면 **transform**

#### transform 3D 변환 함수

| 값(변환함수)                          | 의미                            | 단위       |
| ------------------------------------- | ------------------------------- | ---------- |
| translate3d(x, y, z)                  | 이동(X축, Y축, Z축)             | 단위       |
| translatZ(z)                          | 이동(Z축)                       | 단위       |
| scale3d(x, y, z)                      | 크기(X축, Y축, Z축)             | 없음(배수) |
| scaleZ(z)                             | 크기(Z축)                       | 없음(배수) |
| rotate3d(x, y, z, a)                  | 회전(X벡터, Y벡터, Z벡터, 각도) | 없음, deg  |
| rotateX(x)                            | 회전(X축)                       | deg        |
| rotateY(y)                            | 회전(Y축)                       | deg        |
| rotateZ(z)                            | 회전(Z축)                       | deg        |
| perspective(n)                        | 원근법(거리)                    | 단위       |
| matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n) | 2차원 변환 효과                 | 없음       |

- rotateX, rotateY
  3차원 변환 함수임
- Z축은 우리 눈에는 보이지 않음

* perspective는 transform 맨 앞부분에 있어야함
  값이 커질수록 가까이서 보는 느낌
  [example]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103497799-f13f3380-4e85-11eb-8a7f-3969ec6bf4ad.png)

### transform 변환 속성

| 속성                | 의미                                              |
| ------------------- | ------------------------------------------------- |
| transform-orgin     | 요소 변환의 기준점을 설정                         |
| transform-style     | 3D 변환 요소의 자식요소도 3D 변환을 사용할지 설정 |
| perspecitve         | 하위 요소를 관찰하는 원근 거리를 설정             |
| perspective-origin  | 원근 거리의 기준점을 설정                         |
| backface-visibility | 3D 변환으로 회전된 요소의 뒷면 숨김을 설정        |

#### transform-origin

설명: 요소 변환의 기준점을 설정

| 값  | 의미                     | 기본값 |
| --- | ------------------------ | ------ |
| X축 | left,right,center,%,단위 | 50%    |
| Y축 | top,bottom,center,%,단위 | 50%    |
| Z축 | 단위                     | 0      |

[right,bottom]<br>
![image](https://user-images.githubusercontent.com/54137044/103498224-53e4ff00-4e87-11eb-9a9b-4787dd9ba436.png)

#### transform-style

설명 : 3D 변환 요소의 자식요소도 3D 변환을 사용할지 설정

| 값          | 의미                                | 기본값 |
| ----------- | ----------------------------------- | ------ |
| flat        | 자식 요소의 3D 변환을 사용하지 않음 | flat   |
| preserve-3d | 자식 요소의 3D 변환을 사용함        |        |

- perspective의 width와 부모 요소의 사이즈 일치 시키는게 좋음
- preserve-3d - 자식 요소에서도 3d 사용하겠다
  -> 바로 아래 자식만 적용이 되기 때문에 다른 곳에도 사용하면 부모 요소에 계속적인 선언이 필요함
  [example]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103498721-09fd1880-4e89-11eb-8295-f0528e9fa778.png)

### perspective

설명 : 하위 요소를 관찰하는 원근 거리를 설정

| 값   | 의미                      | 기본값 |
| ---- | ------------------------- | ------ |
| 단위 | px, em, cm 등 단위로 지정 |        |

- 선언 하는 곳이 관찰하려는 곳의 상위 부분에 선언

  #### perspective 속성과 함수의 차이점

  | 속성/함수                | 적용대상              | 기준점 설정        |
  | ------------------------ | --------------------- | ------------------ |
  | perspective              | 관찰 대상의 부모 요소 | perspective-origin |
  | transform: perspective() | 관찰 대상             | perspective-origin |

  - 속성은 관찰 대상의 부모(조상) 요소에 적용하여 하위 요소들을 관찰하는 원근 거리를 설정
  - 함수는 관찰 대상에 직접 적용하여 그 대상을 관찰하는 원근 거리를 설정

  ### perspective-origin

  설명 : 원근 거리의 기준점을 설정

  | 값  | 의미                         | 기본값 |
  | --- | ---------------------------- | ------ |
  | X축 | left, right, ceter, %, 단위  | 50%    |
  | Y축 | top, bottom, center, %, 단위 | 50%    |

  [exaple]<br>
  ![image](https://user-images.githubusercontent.com/54137044/103499185-90662a00-4e8a-11eb-95b3-d26aef3e405c.png)

### backface-visibility

설명 : 3D 변환으로 회전된 요소의 둣면 숨김을 설정

| 값      | 의미             | 기본값  |
| ------- | ---------------- | ------- |
| visible | 뒷면 숨기지 않음 | visible |
| hidden  | 뒷면 숨김        |         |

### matrix(a,b,c,d,e,f)

설명 : 요소의 2차원 변환(Transforms)효과를 지정

scale(), skew(), translate() 그리고 rotate()지정

- 일반적인 경우에는 일반 변환 함수를 사용하면 됨
- 일반함수가 matrix 함수로 변환되어서 브라우저에는 적용

![image](https://user-images.githubusercontent.com/54137044/103499563-e12a5280-4e8b-11eb-9bb8-609a41a6b830.png)

### example

[card]<br>
![image](https://user-images.githubusercontent.com/54137044/103501004-4122f800-4e90-11eb-868d-fc20798b3c42.png)
[hover]
![image](https://user-images.githubusercontent.com/54137044/103501041-59931280-4e90-11eb-978e-3ae4bd5ee79f.png)

### animation

설명 : 요소에 애니메이션을 설정/제어

| 값                        | 의미                              | 기본값  |
| ------------------------- | --------------------------------- | ------- |
| animation-name            | @keyframes 규칙의 이름을 설정     | none    |
| animation-duration        | 애니메이션의 지속 시간 설정       | 0s      |
| animation-timing-function | 타이밍 함수 지정                  | ease    |
| animation-delay           | 애니메이션의 대기 시간 설정       | 0s      |
| animation-iteration-count | 애니메이션의 반복 횟수 설정       | 1       |
| animation-direction       | 애니메이션의 반복 방향 설정       | normal  |
| animation-fill-mode       | 애니메이션의 전후 상태(위치) 설정 | none    |
| animation-play-state      | 애니메이션의 재생과 정지 설정     | running |

animation : 애니메이션이름 지속시간 [타이밍함수 대기시간 반복횟수 반복방향 전후상태 재생/정지]

#### @keyframes

설명 : 2개 이상의 애니메이션 중간 상태(프레임)을 지정

```css
@keyframes move-box {
  0% {
    left: 100px;
  }
  100% {
    right: 200px;
  }
}
```

### animation-name

설명 : @keyframes규칙(애니메이션 프레임)의 이름을 지정

| 값             | 의미                                                | 기본값 |
| -------------- | --------------------------------------------------- | ------ |
| none           | 애니메이션을 지정하지 않음                          | none   |
| @keyframes이름 | 이름이 일치하는 @keyframes 규칙의 애니메이션을 적용 |        |

### animation-duration

설명 : 애니메이션의 지속 시간 설정

| 값   | 의미             | 기본값 |
| ---- | ---------------- | ------ |
| 시간 | 지속 시간을 설정 | 0s     |

- ms 사용가능

### animation-timing-function

설명 : 타이밍 함수(애니메이션 효과를 계산하는 방법)지정
| 값 | 의미 | 기본값 | Cubic Bezier 값 |
| --------------------- | ----------------------- | ------ | ----------------------------- |
| ease | 빠르게-느리게 | ease | cubic-bezier(.25, .1, .25, 1) |
| linear | 일정하게 | | cubic-bezier(0, 0, 1, 1) |
| ease-in | 느리게-빠르게 | | cubic-bezier(.42, 0, 1, 1) |
| ease-out | 빠르게-느리게 | | cubic-bezier(0, 0, .58, 1) |
| ease-in-out | 느리게-빠르게-느리게 | | cubic-bezier(0, 0, .58, 1) |
| cubic-bezier(n,n,n,n) | 자신만의 값을 정의(0~1) | | |
| steps(n) | n 번 분활된 애니메이션 | | |

### animation-delay

설명 : 애니메이션의 대기 시간 설정

| 값   | 의미             | 기본값 |
| ---- | ---------------- | ------ |
| 시간 | 대기 시간을 설정 | 0s     |

- 음수값 허용 - 바로 시작 되지만 그 만큼 애니메이션 앞서 시작(주기 도중)

* delay가 duration보다 앞에만 있지 않으면 순서 바뀌어도 무관

### animation-iteration-count

설명 : 애니메이션 반복 횟수를 설정

| 값       | 의미             | 기본값 |
| -------- | ---------------- | ------ |
| 숫자     | 반복 횟수를 설정 | 1      |
| infinite | 무한 반복        |        |

### animation-direction

설명 : 애니메이션의 반복 방향을 설정

| 값                | 의미                             | 기본값 |
| ----------------- | -------------------------------- | ------ |
| normal            | 정방향만 반복                    | normal |
| reverse           | 역방향만 반복                    |        |
| alternate         | 정방향에서 역방향으로 반복(왕복) |        |
| alternate-reverse | 역방향에서 정방향으로 반복(왕복) |        |

- 횟수를 소비해서 방향으로 가는데 alternate나 reverse는 횟수를 1회 더 설정해 줘야 함

### animation-fill-mode

설명 : 애니메이션의 전후 상태(위치)를 설정

| 값        | 의미                                                                             | 기본값 |
| --------- | -------------------------------------------------------------------------------- | ------ |
| none      | 기존 위치에서 시작->애니메이션 시작 위치로 이동->동작->기존위치에서 끝           | none   |
| forward   | 기존 위치에서 시작->애니메이션 시작 위치로 이동->동작->애니메이션 끝 위치에서 끝 |        |
| backwards | 애니메이션 시작 위치에서 시작->동작->기존 위치에서 끝                            |        |
| both      | 애니메이션 시작 위치에서 시작->동작->애니메이션 끝 위치에서 끝                   |        |

### animation-play-state

설명 : 애니메이션의 재생과 정지를 설정

| 값      | 의미                   | 기본값  |
| ------- | ---------------------- | ------- |
| running | 애니메이션을 동작      | running |
| paused  | 애니메이션 동작을 정지 |         |

### Mulit-Columns

설명 : 일반 블록 레이아웃을 확장하여 여러 텍스트 다단으로 쉽게 정리하며 가독성 확보

![image](https://user-images.githubusercontent.com/54137044/103506839-0d040300-4ea1-11eb-9610-5e52ac0088c0.png)

#### columns

설명 : 다단을 정의

| 값           | 의미                               | 기본값 |
| ------------ | ---------------------------------- | ------ |
| auto         | 브라우저가 단의 너비와 개수를 설정 | auto   |
| column-width | 단의 최적 너비를 설정              | auto   |
| column-count | 단의 개수를 설정                   | auto   |

```css
.text {
  columns: 100px 2;
}
```

#### column-width

설명 : 단의 최적 너비를 설정

| 값   | 의미                        | 기본값 |
| ---- | --------------------------- | ------ |
| auto | 브라우저가 단의 너비를 설정 | auto   |
| 단위 | px,em,cm등 단위로 지정      |        |

- 각 단이 줄어들 수 있는 최적 너비(최소 너비)를 설정하며, 요소의 너비가 가변하여 하나의 단이 최적 너비보다 줄어들 경우 단의 개수가 조정

#### column-count

설명 : 단의 개수를 설정

| 값   | 의미                        | 기본값 |
| ---- | --------------------------- | ------ |
| auto | 브라우저가 단의 개수를 설정 | auto   |
| 숫자 | 단의 개수를 설정            |        |

#### column-gap

설명 : 단과 단 사이의 간격 설정

| 값     | 의미                                       | 기본값 |
| ------ | ------------------------------------------ | ------ |
| normal | 브라우저가 단과 단 사이의 간격을 설정(1em) | normal |
| 단위   | px,em,cm 등 단위로 지정                    |        |

#### column-rule

설명 : 단과 단 사이의 (구분)선을 지정

| 값           | 의미             | 기본값               |
| ------------ | ---------------- | -------------------- |
| column-width | 선의 두께를 지정 | medium               |
| column-style | 선의 종류를 지정 | none                 |
| column-color | 선의 색상을 지정 | 요소의 글자색과 동일 |

- 구분선은 단과 단 사이의 중간에 위치
- 구분선의 기본 색상은 글자색의 영향을 받음

## Flex

---

Flex는 요소의 크기가 불분명하거나 동적인 경우에도, 각 요소를 정렬할 수 있는 효율적인 방법을 제공합니다.

1. Container
   Items를 감싸는 부모 요소이며 각 Item을 정렬하기 위해선 Container가 필수
   display, flex-flow, justify-content 적용 가능
2. Item
   order, flex, align-self 사용 가능

![image](https://user-images.githubusercontent.com/54137044/103508830-1db67800-4ea5-11eb-92ed-6f5fd25bc9bf.png)

### Flex Container

| 속성            | 의미                                                  |
| --------------- | ----------------------------------------------------- |
| display         | Flex Container를 정의                                 |
| flex-flow       | flex-direction와 flex-wrap의 단축 속성                |
| flex-direction  | Flex Items의 주 축(main-axis)을 설정                  |
| flex-wrap       | Flex Items의 여러 줄 묶음(줄 바꿈) 설정               |
| justify-content | 주 축(main-axis)의 정렬 방법을 설정                   |
| align-content   | 교차 축(cross-axis)의 정렬 방법을 설정(2줄 이상)      |
| align-items     | 교차 축(cross-axis)에서 Items의 정렬 방법을 설정(1줄) |

### display

| 값          | 의미                                | 기본값 |
| ----------- | ----------------------------------- | ------ |
| flex        | Block 특성의 Flex Container를 정의  |
| inline-flex | Inline 특성의 Flex Container를 정의 |

- block으로 될지 inline으로 될지 정함

![image](https://user-images.githubusercontent.com/54137044/103509146-cb298b80-4ea5-11eb-98c3-9dd10f0323e6.png)

### flex-flow

설명 : 단축 속성으로 Flex Items의 주 축 (main-axis)을 설정, items의 여러 줄 묶음(줄 바꿈)도 설정

```css
.flex-container {
  flex-flow: row-reverse wrap;
}
```

| 값             | 의미                               | 기본값 |
| -------------- | ---------------------------------- | ------ |
| flex-direction | Items의 주 축(main-axis)을 설정    | row    |
| flex-wrap      | Items의 여러 줄 묶음(줄 바꿈) 설정 | nowrap |

#### flex-direction

설명 : Items의 주 축(main-axis)을 설정
|값 |의미| 기본값|
|---|---|---|
|row| Itmes를 수평축(왼쪽에서 오른쪽으로)으로 표시 |row|
|row-reverse| Items를 row의 반대 축으로 표시 | |
|column| Items를 수직축(위에서 아래로)으로 표시| |
|column-reverse |Items를 column의 반대 축으로 표시| |

![image](https://user-images.githubusercontent.com/54137044/103509642-f1036000-4ea6-11eb-82b0-44e1e26e2b34.png)

#### 주 축(main-axis)과 교차 축(cross-axis)

row는 items를 수평축으로 표시
주 축 : 수평
교차 축 : 수직
column은 items 수직으로 표시
주 축 : 수직
교차 축 : 수평

- 주 축이 바뀌면 교차 축도 바뀜
  ![image](https://user-images.githubusercontent.com/54137044/103509796-48a1cb80-4ea7-11eb-81ac-b4fec9b22e54.png)

#### 시작점(flex-start)과 끝점(flex-end)

- reverse에 따라 변경되는 값이 아님

![image](https://user-images.githubusercontent.com/54137044/103509926-856dc280-4ea7-11eb-9d5c-d4ebe20dde63.png)

![image](https://user-images.githubusercontent.com/54137044/103510033-bf3ec900-4ea7-11eb-809c-8c06c2d2f9dd.png)

### flex-wrap

설명 : items의 여러 줄 묶음(줄 바꿈)을 설정

| 값           | 의미                                           | 기본값 |
| ------------ | ---------------------------------------------- | ------ |
| nowrap       | 모든 Itmes를 여러 줄로 묶지 않음(한 줄에 표시) | nowrap |
| wrap         | Items를 여러 줄로 묶음                         |        |
| wrap-reverse | Items를 wrap의 역 방향으로 여러 줄로 묶음      |        |

![image](https://user-images.githubusercontent.com/54137044/103510534-c9ad9280-4ea8-11eb-9dc5-9b57b80d3644.png)

[example]
![image](https://user-images.githubusercontent.com/54137044/103514582-442de080-4eb0-11eb-9dc9-1e2402c8f0b1.png)

### justify-content

설명 : 주 축(main-axis)의 정렬 방법을 설정

| 값            | 의미                                                                                    | 기본값     |
| ------------- | --------------------------------------------------------------------------------------- | ---------- |
| flex-start    | Items를 시작점(flex-start)으로 정렬                                                     | flex-start |
| flex-end      | Items를 끝점(flex-end)으로 정렬                                                         |            |
| center        | Items를 가운데 정렬                                                                     |            |
| space-between | 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨 |            |
| space-around  | Items를 균등한 여백을 포함하여 정렬                                                     |            |

justify-content: 정렬방법

![image](https://user-images.githubusercontent.com/54137044/103514762-a7b80e00-4eb0-11eb-83b1-9799c6e8a833.png)

### align-content

설명 : 교차 축(cross-axis)의 정렬 방법을 설정
flex-wrap 속성을 통해 items가 여러줄 이상이고 여백이 있을 경우 사용 가능

| 값            | 의미                                                                                    | 기본값     |
| ------------- | --------------------------------------------------------------------------------------- | ---------- |
| strech        | Container의 교차 축을 채우기 위해 itmes 늘림                                            | stretch    |
| flex-start    | Items를 시작점(flex-start)으로 정렬                                                     | flex-start |
| flex-end      | Items를 끝점(flex-end)으로 정렬                                                         |            |
| center        | Items를 가운데 정렬                                                                     |            |
| space-between | 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨 |            |
| space-around  | Items를 균등한 여백을 포함하여 정렬                                                     |            |

![image](https://user-images.githubusercontent.com/54137044/103515324-db476800-4eb1-11eb-9d07-d30094cdf80d.png)
