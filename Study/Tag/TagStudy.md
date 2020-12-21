# TAG

---

### header

    속성 : 전역
    설명 : 일반적으로 소개나 탐색에 사용
    사이트 가장 위
    로고, 메뉴, 로그인, 로그아웃 등 여러 정보
    header는 후손이 될 수 없다
        address 테그 안 header 선언 불가
    header { display: block; }

[사이트 주소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/header)

### footer

    속성 : 전역
    설명 : 작성자 구획, 저작권 데이터, 관련된 문서의 링크
    사이트 가장 아래
    footer { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)

### h1~h6

    속성 :전역
    설명 : 6단계의 문서 제목 지정
    화면에는 크기가 지정되어있게 나와있지만 제목당의 크기는 별도로 지정해야 한다
        -> 초기화를 해놓고 지정을 해야함
    크기 지정 -> CSS font-size
    시작은 무조건 h1 부터 시작해야 하고 제목단계를 건너 뛰는 것은 하지 말아야함
        -> 브라우저나 기기에서 건너 뛰기를 해야하는데 이는 비효율적
        -> 메모리 낭비
    처음의 대제목을 h1으로 정하고 h2를 사용해서 다른 제목들을 사용하는게 편리함
    Nesting 중첩
        h1은 중복해서 사용하지 않도록 하고 중복을 한다면 h2를 통함
    h1, h2, h3, h4, h5, h6 { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)

### Labeling

    hearder footer 제목을 나누는 느낌이라 생각하면 됨

### main

    *** IE 사용 불가 ***
    속성 : 전역
    설명 : 페이지의 핵심 정보가 들어감
    hidden 속성 없이는 main 테그는 여러개 존재 할 수 없음
    main { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main)

### article

    *** 독립성 ***
    속성 : 전역
    설명 : 독립적으로 구분되거나 재사용 가능한 영역을 설정
        매거진, 신문, 기사, 블로그
    의미적으로 강조가 필요한 부분에서 사용
    독립적이고 재사용이 가능
    일반적 h1 ~ h6 포함하여 식별
    작성 일자와 시간을 <time>의 datetime 속성으로 작성
    article { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)

### section

    설명 : 문서의 일반적인 영역을 설정
        제목을 포함한다 -> h1 ~ h6
    div와의 차이점이라고 볼 수 있음
    div는 의미를 가지지 않지만 section은 의미를 가짐 -> 제목
    section 안 article 반대로도 가능
    section { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)

### aside

    설명 : 문서의 별도 콘텐츠를 설정
        광고, 기타 링크 -> 핵심 컨텐츠와는 별개되는 내용
    aside { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)

### nav

    설명 : 다른 페이지 링크를 제공하는 영역
        메뉴, Home, About, Contact, 목차, 색인
    ol, ul과 엮어서 사용
    nav { display: block; }
    항상 헤더 안에 존재하지는 않아도 됨

[사이트주소](https://www.w3schools.com/tags/tag_nav.asp)

### address

    설명 : body, article, footer 등에서 연락처 정보를 제공하기 위해 사용
    address { display: block; }
    href와 엮어서 사용
        <a href = "mailto:wshmin@naver.com">wshmin@naver.com</a><br>
        <a href ="tell:+082xxxxxxx">(010)xxx-xxxx</a><br>
    address { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address)

### div

    설명 : 본질적 아무것도 나타내지 않는 영역
        특별한 의미를 가지지 않음 -> 꾸미는 목적으로 사용
    div { display: block; }

[사이트주소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)

### <ol> <ul> <li>

    설명 : 각 항목 <li>의 정렬된 목록 <ol> 이나 정렬되지 않은 목록 <ul>을 설정
    ol : Ordered List
        1. 2. 3.
    ul : Unordered List
        * * * 점으로 표현
    li 는 무조건 ol 이나 ul로 꼭 감싸야한다(자식으로 포함되어야 함)
    ol, ul { display: block; }
    li { display: list-item; } -> ol ul 이 block 이기 때문에 부모로써 block으로 생각
    <ol type="I" reversed>
    ol -> reversed
        역순
        IE 지원불가
        -> start
            시작값
        -> type
        번호 유형
            1 숫자
            A 대문자 A
            a 소문자 a
            i 로마 i
            I 로마 I

### <dl> <dt> <dd>

    설명 :
        1. <dt> Definition Term
            용어
        2. <dd> Definition Details
            정의, 설명
        3. <dl>  Description List
            영역 묶음
    <dl>은 <dd>, <dt>만을 포함해야 함
    # python dic 같은 개념으로 생각
    key = value
    dl dt dd { display: block; }

[테그 보는 곳](https://www.w3schools.com/)
