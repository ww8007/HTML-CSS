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

[capture]![image](https://user-images.githubusercontent.com/54137044/103164529-e403c280-484f-11eb-9362-63ed1acb69d5.png)

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

-   열리는 TABLE 태그 바로 다음에 작성해야 함
-   table 하나 당 하나의 caption만 사용 가능

```css
caption {
    display: table-caption;
}
```

[capture]![image](https://user-images.githubusercontent.com/54137044/103164629-211c8480-4851-11eb-8351-fe2a1dafba46.png)
