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

| :속성:  | :의미:                                       | :값:            | :기본값: |
| ------- | -------------------------------------------- | --------------- | -------- |
| abbr    | 열에 대한 간단한 설명                        |                 |          |
| headers | 관련된 하나 이상의 다른 머리글 칸 id 속성 값 |                 |
| colspan | 확장하려는(병합) 열의 수                     |                 | 1        |
| rowsapn | 확장하려는(병합)행의 수                      |                 | 1        |
| scope   | 자신이 누구의 '머리글 칸'인지 명시           | col : 자신의 열 | auto     |
