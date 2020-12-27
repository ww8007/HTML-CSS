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

| 속성         | 의미                                                              | 값           | 기본값                                    | 특징                                                         |
| ------------ | ----------------------------------------------------------------- | ------------ | ----------------------------------------- | ------------------------------------------------------------ | ----------------------------------------------------------- |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | on, off      | on                                        |                                                              |
| autofocus    | 페이지가 로드될 때 자동으로 포커스                                | bool         |                                           | 문서 내 고유해야 함                                          |
| checked      | 양식이 선택되었음을 표시                                          | bool         |                                           | type 속성 값이 radio, checkbox 경우 일때만 적용              |
| disabled     | 양식을 비활성화                                                   | bool         |                                           |                                                              |
| form         | &#60;form &#62;의 id 속성 값                                      |              | 해당 &#60;form &#62;의 후손이 아닐 경우만 |
| list         | 참조할 &#60;datalist &#62;의 id 속성 값                           |              |                                           |
| max          | 지정 가능한 최대 값                                               | 숫자(Number) |                                           | type 속성 값이 number 일 경우만, min 속성보다 큰 값만 허용   |
| min          | 지정 가능한 최소 값                                               | 숫자(Nuber)  |                                           | type 속성 값이 number 일 경우만, max 속성보다 작은 값만 허용 |
| maxlength    | 입력 가능한 최대 문자 수                                          | 숫자         | Number                                    | 524288                                                       | type 속성 값이 ext, email, password, tel, URL일 경우만 사용 |
| muliple      | 둘 이상의 값을 입력 할 수 있는지 여부                             | bool         |                                           | type 속성 값이 email, file일 경우만, email 일 경우 ,로 구분  |
| name         | 양식의 이름                                                       |              |                                           |                                                              |
| placeholder  | 사용자가 입력할 값의 힌트                                         |              |                                           | type 속성 값이 text, search, tel, ulr, email일 경우만        |
| readonly     | 수정 불가한 읽기 전용                                             | bool         |                                           |                                                              |

-  autocomplete : 자동완성 기능 on, off
-  autofocus : 하나 밖에 사용 못함
-  checked : radio, checkbox만 적용
-
