# Study

### 1. table 2. tr 3. th 4. td

    데이터 표 (<table>)의 행(줄/ <tr>)거ㅣ 열(칸, 셀(Cell) /)th ,td 생성
    Table Row, Table Header, Table Data
    블록 요소와 되게 비슷한 특성을 가짐
    table은 td의 부모 요소
    th : header
    td : data

```css
table {
   display: table;
}
tr {
   display: table-raw;
}
th,
td {
   display: table-cell;
}
```

#### th

설명 : 머리글 칸을 지정

| 속성       | 의미                                         | 값                                                                                     | 기본값 |
| ---------- | -------------------------------------------- | -------------------------------------------------------------------------------------- | ------ |
| abbr       | 열에 대한 간단한 설명                        |                                                                                        |        |
| headers    | 관련된 하나 이상의 다른 머리글 칸 id 속성 값 |                                                                                        |
| colspan    | 확장하려는(병합) 열의 수                     |                                                                                        | 1      |
| rowsapn    | 확장하려는(병합)행의 수                      |                                                                                        | 1      |
| scope      | 자신이 누구의 '머리글 칸'인지 명시           | col : 자신의 열<br/> colgroup : 모든 열 <br/> row : 자신의 행 <br/> rowgroup : 모든 행 |
| <br/> auto | auto                                         |

![image](https://user-images.githubusercontent.com/54137044/103164529-e403c280-484f-11eb-9362-63ed1acb69d5.png)

### td tag

설명 : 일반 칸을 지정

1. headers
   설명 : 관련된 하나 이상의 다른 머리글 칸 id 속성 값
   td 에서 사용하지만 th에 연결하는 것(혼동)
2. colsapn
   설명 : 확장하려는(병합) 열의 수
3. rowsapn
   설명 : 확장하려는 (병합) 행의 수

### caption

설명 : 표의 제목을 설정

-  열리는 TABLE 태그 바로 다음에 작성해야 함
-  table 하나 당 하나의 caption만 사용 가능

```css
caption {
   display: table-caption;
}
```

![image](https://user-images.githubusercontent.com/54137044/103164629-211c8480-4851-11eb-8351-fe2a1dafba46.png)

### colgroup, col

설명 : 표의 열들을 공통적으로 정의하는 컬럼(col)과 그의 집함(colgroup)
(Column, Colum Group)

| 속성 | 의미           | 값           | 기본값 |
| ---- | -------------- | ------------ | ------ |
| span | 연속되는 열 수 | 숫자(NUMBER) | 1      |

col은 caption 위에 적으면 안됨(caption 밑)
col을 이용하여 열 부분의 모든 속성을 제어 가능함
col이 많아질 경우 span 속성 추가 하여 사용

```css
colgroup {
   display: table-column-group;
}
col {
   display: table-column;
}
```

![image](https://user-images.githubusercontent.com/54137044/103164956-051ae200-4855-11eb-859f-a1403aee89d6.png)

### thead, tbody, tfoot

설명 : 표의 머리글(thead), 본문(tbody), 바닥글(tfoot)

-  기본적으로 테이블의 레이아웃에 영향을 주지 않음

형식적으로 나눠주기 위함

```css
thead {
   display: table-header-group;
}
tbody {
   display: table-row-group;
}
tfoot {
   display: table-footer-group;
}
```

![image](https://user-images.githubusercontent.com/54137044/103165001-8b372880-4855-11eb-8d86-b8bee804e450.png)

## 양식

### form

설명 : 웹서버에 정보를 제출하기 위한 양식 범위를 정의

-  from 이 다른 from의 자식 요소로 포함할 수 없음

| 속성         | 의미                                                              | 값        | 기본값 |
| ------------ | ----------------------------------------------------------------- | --------- | ------ |
| action       | 전송할 정보를 처리할 웹페이지의 URL                               | URL       |        |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | on, off   | on     |
| method       | 서버로 전송할 HTTP 방식                                           | GET, POST | GET    |
| name         | 고유한 양식의 이름                                                |           |        |
| novalidate   | 서버로 전송시 양식 데이터의 유효성을 검사하지 않도록 지정         |           |        |
| target       | 서버로 전송 후 응답받을 방식을 지정                               |           |        |

-  action : 서버 쪽 URL
-  autocomplete : 자동완성 기능
-  method : GET(보안성 저하 주소부분에 노출), POST(보안성이 높아짐)
   POST 방식을 사용하면 주소 부분에는 사용자 정보가 보이지는 않지만 결국 Form Data 부분에 노출이 됨 -> 완벽히 숨길 수 없음(암호화 해서 전송)
-  name : 이름
-  novalidate : 유효성 검사 제거(test) : bool 방식
-  target : a 테그와 비슷하게 self(현재), blank(새로) 띄울지 설정

![image](https://user-images.githubusercontent.com/54137044/103165358-000c6180-485a-11eb-81fe-ff9cb6488907.png)

### input

| 속성         | 의미                                                              | 값           | 기본값 | 특징                                                         |
| ------------ | ----------------------------------------------------------------- | ------------ | ------ | ------------------------------------------------------------ |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | on, off      | on     |                                                              |
| autofocus    | 페이지가 로드될 때 자동으로 포커스                                | bool         |        | 문서 내 고유해야 함                                          |
| checked      | 양식이 선택되었음을 표시                                          | bool         |        | type 속성 값이 radio, checkbox 경우 일때만 적용              |
| disabled     | 양식을 비활성화                                                   | bool         |        |                                                              |
| form         | &#60;form &#62;의 id 속성 값                                      |              |        | 해당 &#60;form &#62;의 후손이 아닐 경우만                    |
| list         | 참조할 &#60;datalist &#62;의 id 속성 값                           |              |        |                                                              |
| max          | 지정 가능한 최대 값                                               | 숫자(Number) |        | type 속성 값이 number 일 경우만, min 속성보다 큰 값만 허용   |
| min          | 지정 가능한 최소 값                                               | 숫자(Nuber)  |        | type 속성 값이 number 일 경우만, max 속성보다 작은 값만 허용 |
| maxlength    | 입력 가능한 최대 문자 수                                          | 숫자(Number) | 524288 | type 속성 값이 ext, email, password, tel, URL일 경우만 사용  |
| muliple      | 둘 이상의 값을 입력 할 수 있는지 여부                             | bool         |        | type 속성 값이 email, file일 경우만, email 일 경우 ,로 구분  |
| name         | 양식의 이름                                                       |              |        |                                                              |
| placeholder  | 사용자가 입력할 값의 힌트                                         |              |        | type 속성 값이 text, search, tel, ulr, email일 경우만        |
| readonly     | 수정 불가한 읽기 전용                                             | bool         |        |                                                              |
| step         | 유효한 증감 숫자의 간격                                           | 숫자(Nuber)  | 1      | type 속성 값이 number, range인 경우만 해당                   |
| src          | 이미지의 URL                                                      | URL          |        | type 속성 값이 image 일 경우만                               |
| alt          | 이미지의 대체 텍스트                                              |              |        | type 속성 값이 image 일 경우만                               |
| type         | 입력 받을 데이터의 종류                                           | 별도 정리    | text   |                                                              |
| value        | 양식의 초기 값                                                    |              |        |                                                              |

-  autocomplete : 자동완성 기능 on, off
-  autofocus : 하나 밖에 사용 못함
-  checked : radio, checkbox만 적용
-  form : form 테그 밖에서 form 양식을 사용 가능
-  readonly, disabled
   readonly는 focus는 가능
   disabled는 focus조차 불가

```html
<body>
   <form action="/login" id="login-form"></form>

   <input type="text" form="login-form" />
</body>
```

-  name : 양식의 이름
-  type : 입력 받을 데이터의 종류

#### type 입력 가능 데이터 값

| 값       | 데이터종류                | 특징                                    |
| -------- | ------------------------- | --------------------------------------- |
| button   | 일반 버튼                 | &#60;button&#62;처럼 사용               |
| checkbox | 체크박스                  |                                         |
| color    | 색상                      | IE 지원 불가                            |
| email    | 이메일                    |                                         |
| file     | 파일                      |                                         |
| hidden   | 보이지 않지만 전송할 양식 | value 속성으로 값을 지정                |
| image    | 이미지 제출 버튼          | &#60;img /&#62;처럼 사용                |
| number   | 숫자                      |                                         |
| password | 비밀                      | 가려지는 양식                           |
| radio    | 라디오 버튼               | 같은 name 속성 그룹 내 하나만 선택 가능 |
| range    | 범위 컨트롤               | min, max, step, value(기본값)속성 사용  |
| reset    | 초기화                    | 해당 &#60;form&#62; 범위 내 모든 양식   |
| search   | 검색                      |                                         |
| submit   | 제출 버튼                 | 해당&#60;form&#62; 범위 내 고유한 양식  |
| tel      | 전화번호                  |                                         |
| text     | 일반 텍스트               |                                         |
| url      | 절대 URL                  |                                         |

-  button , submit : 둘 다 동일하게 버튼 형식이지만 submit 을 써야 전송을 해줌
-  input image를 사용해서 image 테그를 사용하지 않고도 이미지를 삽입하거나 링크로 작동하게 할 수 있음

![image](https://user-images.githubusercontent.com/54137044/103202674-6a92cf80-4936-11eb-8ace-7c0d724ef95c.png)

```html
<body>
   <input
      type="number"
      placeholder="숫자를 입력하세요!"
      max="8"
      min="1"
      id="1"
   />
   <input type="number" step="4" id="2" />
   <div>
      체크박스
      <input type="checkbox" checked id="3" />
   </div>
   <input type="file" multiple />
   <form action="/login">
      <input type="image" src="/20201227_142855.png" alt="my" />
   </form>
   <input type="radio" name="radio1" />
   <input type="radio" name="radio1" checked />
   <input type="radio" name="radio1" />
   <input type="radio" name="radio1" />
   <form action="/login">
      <input type="text" name="id" />
      <input type="password" name="pw" />
      <input type="submit" value="로그인" />
      <input type="reset" value="초기화" />
   </form>
   <input type="text" />
</body>
```

```css
input {
   display: inline-block;
}
```

### label

라벨 가능 요소(labelable)의 제목(Caption)

-  for 속성으로 라벨 가능 요소를 참조하거나 콘텐츠로 포함
-  라벨 가능 요소 : &#60;button&#62;&#60;input&#62;&#60;progress&#62;&#60;select&#62;&#60;textarea&#62;

| 속성 | 의미                               |
| ---- | ---------------------------------- |
| for  | 참조할 라벨 가능 요소의 id 속성 값 |

![image](https://user-images.githubusercontent.com/54137044/103203550-839c8000-4938-11eb-80ed-5de147732296.png)

```css
label {
   display: inline;
}
```

### button

선택 가능한 버튼을 지정

| 속성      | 의미                                  | 값                    | 특징                                         |
| --------- | ------------------------------------- | --------------------- | -------------------------------------------- |
| autofocus | 페이지가 로드될 때 자동으로 포커스    | bool                  | 문서 내 고유해야 함                          |
| disabled  | 버튼을 비활성화                       | bool                  |                                              |
| form      | &#60;form&#62;의 id 속성 값           |                       | 해당&#60;form&#62;의 후손이 아닐 경우만 해당 |
| name      | 폼 데이터와 함께 전송되는 버튼의 이름 |                       |                                              |
| type      | 버튼의 타입                           | button, reset, submit |                                              |

-  일반 버튼 같은 경우는 type을 명시하지 않아도 됨

![image](https://user-images.githubusercontent.com/54137044/103204217-26a1c980-493a-11eb-9e0a-30680acd7bbd.png)

```css
button {
   display: inline-block;
}
```

### textarea

설명 : 여러줄의 일반 텍스트 양식

| 속성         | 의미                                                              | 값           | 기본값                                   | 특징 |
| ------------ | ----------------------------------------------------------------- | ------------ | ---------------------------------------- | ---- |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | on, off      | on                                       |      |
| autofocus    | 페이지가 로드될 때 자동으로 포커스                                | bool         | 문서 내 고유해야 함                      |
| disabled     | 양식을 비활성화                                                   | bool         |                                          |
| form         | &#60;form&#62;의 id 속성 값                                       |              | 해당 &#60;form&#62;의 후손이 아닐 경우만 |
| maxlength    | 입력 가능한 최대 문자수                                           | 숫자(Number) | 무한                                     |      |
| name         | 양식의 이름                                                       |              |                                          |      |
| placeholder  | 사용자가 입력할 값의 힌트                                         |              |                                          |      |
| readonly     | 수정 불가한 읽기 전용                                             | bool         |                                          |      |
| rows         | 양식의 줄 수                                                      | 숫자(Number) | 2                                        |      |

![image](https://user-images.githubusercontent.com/54137044/103205249-7d100780-493c-11eb-8669-ac08ea627706.png)

### &#60;fieldsetform&#62;,&#60;legendform&#62;

설명 : 같은 목적의 양식을 그룹화(fieldset)하여 제목(legned)를 지정

#### fieldset

설명 : 같은 목적의 양식을 그룹화

| 속성     | 의미                                                | 값   |
| -------- | --------------------------------------------------- | ---- |
| disabled | 그룹 내 모든 양식 요소를 비활성화                   | bool |
| form     | 그룹이 속할 하나 이상의 &#60;form&#62;의 id 속성 값 |      |
| name     | 그룹의 이름                                         |      |

![image](https://user-images.githubusercontent.com/54137044/103205805-c3b23180-493d-11eb-835c-ca09dfc73f9f.png)

```css
fieldset,
legend {
   display: block;
}
```

### select, datalist, optgroup, option

설명 : 옵션(option, optgroup)의 선택 메뉴(select)나 자동완성(datalist)을 제공

#### select

설명 : 옵션을 선택하는 메뉴

| 속성         | 의미                                                              | 값           | 기본값      |
| ------------ | ----------------------------------------------------------------- | ------------ | ----------- |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | on, off      | on          |
| disabled     | 선택 메뉴를 비활성화                                              | bool         |             |
| form         | 선택 메뉴가 속할 하나 이상의 &#60;form&#62;의 id 속성 값          |              |             |
| multiple     | 다중 선택 여부                                                    | bool         |             |
| name         | 선택 메뉴의 이름                                                  |              |             |
| size         | 한 번에 볼 수 있는 행의 개수                                      | 숫자(Number) | 0(1과 같음) |

![image](https://user-images.githubusercontent.com/54137044/103206512-69b26b80-493f-11eb-865f-3dc13a7680dd.png)

#### datalist

설명 : input 에 미리 정의된 옵션을 지정하여 자동완성(Autocomplete) 기능을 제공하는 데 사용

-  input의 list 속성 바인딩
-  option 을 포함하여 정의 된 옵션을 지정

리스트의 값과 datalist의 id 값이 동일 해야함

![image](https://user-images.githubusercontent.com/54137044/103207311-53a5aa80-4941-11eb-8997-2ef7373c61ea.png)

#### optgroup

설명 : option을 그룹화

| 속성     | 의미                   | 값   |
| -------- | ---------------------- | ---- |
| label    | (필수)옵션 그룹의 이름 |      |
| disabled | 옵션 그룹을 비활성화   | bool |

![image](https://user-images.githubusercontent.com/54137044/103207096-c9f5dd00-4940-11eb-8823-d217fe235541.png)

#### option

선택 메뉴(select)나 자동완성(datalist)에서 사용될 옵션

-  선택적 빈(Empty)태그로 사용 가능

| 속성     | 의미                     | 값   | 특성                                 |
| -------- | ------------------------ | ---- | ------------------------------------ |
| disabled | 옵션을 비활성화          | bool |                                      |
| label    | 표시될 옵션의 제목       |      | 생략되면 포함된 텍스트를 표시        |
| selected | 옵션이 선택되었음을 표시 | bool |                                      |
| value    | 양식으로 제출될 값       |      | 생략되면 포함된 텍스트를 값으로 사용 |

### progress

설명 : 작업의 완료 진행률을 푯

| 속성  | 의미          | 값           | 특징                                          |
| ----- | ------------- | ------------ | --------------------------------------------- |
| max   | 작업의 총량   | 숫자(Number) |                                               |
| value | 작업의 진행량 | 숫자(Number) | max 속성을 생략할 경우 0~1 사이의 숫자여야 함 |

![image](https://user-images.githubusercontent.com/54137044/103207453-b39c5100-4941-11eb-8e47-4e4685254aad.png)
