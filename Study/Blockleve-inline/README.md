# HTML
-------------------------------
## 블록 레벨(BLOCK LEVER), 인라인(INLINE)으로 구성
1. 블록요소(tag)
    1. 종류
        1.DIV 
        2.H1
        3.P
    2. 사용가능한 최대 가로 너비를 사용한다.
    3. 크기를 지정할 수 있다.    
    4. 초기값 widht : 100%, height : 0;로 시작
    5. 수직으로 쌓임
    6. margin, padding 위,아래,좌,우 사용 가능
    7. 레이아웃 작업용도
2.인라인 요소(tag)
    1. 종류
        1.SPAN
        2.IMG
    2. 필요한 만큼의 너비만 사용한다.
    3. 크기를 지정할 수  없다.
    4. 초기값 width : 0; height = 0;로 시작
    5. 수평으로 쌓임
        * 띄어쓰기가 눈에 보임 -> 블록요소와 다른 점
    6. margin, padding 위, 아래 사용불가 -> 좌, 우만 가능
        * 인라인 요소에서 margin, padding은 위, 아래는 사용안하는게 맞다.
    7. TEXT 작업용도
## 기본 html 개념
### css 호출 
<link rel="stylesheet" href="./(호출할css)">
### 기본 css 개념
1. hegith = 20px; 쓸 시 상하좌우 여백 남음
    -> margin : 0;
    -> padding : 0;
2. div 가 값을 가지진 않음
    기본값 
    widht : auto;
    height : auto;
    별도로 설정하지 않았을 경우 이렇게 설정 됨
    * 인라인 요소와 블록 요소 다른점
        1. 블록요소 
            height : 글자크기 만큼
            widht : 끝까지(margin 제외)
        2. 인라인 요소
            height : 글자크기 만큼
            width : 글자크기 만큼
3. margin, padding
    * margin : 바깥쪽 여백
    - div  블록 : 상, 하, 좌, 우
    - span 인라인 : 좌, 우
    * padding : 안쪽 여백
    - div  블록 : 상, 하, 좌, 우
    - span 인라인 : 좌, 우
4. block 
    인라인 요소   ->   block
    block        ->   인라인 요소
