# 정리

### img tag

    src
        설명 : 이미지 url(필수속성)
        값   : URL
    alt
        설명 : 이미지의 대체 텍스트
    widht
        설명 : 이미지의 가로 너비
        크기를 줄이는 용도로 쓰면 가로 세로 하나만 지정해도 이미지 지정의 비율
        을 따라서 들어감
        css 를 통한 수정도 가능함
    height
        설명 : 이미지의 세로 너비
        크기를 줄이는 용도로 쓰면 가로 세로 하나만 지정해도 이미지 지정의 비율
        을 따라서 들어감
        css 를 통한 수정도 가능함
    srcset
        IE 는 srcset과 sizes 지원 x
        *** srcset과 sizes 사용 못하는 곳은 src, alt가 대체***
        *** 이미지의 원본 크기를 지정해야 함 ***
            2장 이상 준비 -> 아니면 사용할 의미 없음
            px 단위가 아닌 w 단위 또는 x의 단위 사용
        *** 뷰포트의 크기에 따라서 이미지를 다르게 출력해줌 ***
            픽셀 단위를 늘려서 사용하면 이미지가 깨지기 때문
        * 간혹 x단위를 사용하는데 w단위가 x의 상위호환*
        설명 : 브라우저에 제시할 이미지 URL과 크기의 목록을 정의
        값   : w(가로), x(세로)
        일반적 반응형 웹에서 이미지 지원(css)하기 위해서 미디어 쿼리(CSS Media Rule)-> @media에서 background-image 속성을 많이 사용
        반응형 이미지를 처리하기 위해 뷰포트(viewprot)의 크기부터 사용자의 해상도 등 많은 환경을 고려해야함
        -> HTML IMG의 srcset과 sizes를 통해 크기를 설정만 해도 대부분의 고려사항을 사용자 브라우저가 처리해줌
        width를 사용하여서 고정 값을 사용할 수 있음 -> size와 다른 개념
        반응형에 맞게 여러 이미지들 중 최적 이미지를 보여줌
        출력될 이미지 목록(후보)
    sizes
        설명 : 미디어의 조건과 해당 조건일 때 이미지 최적화 크기의 목록을 정의
        최적화된 조건을 표시하는 영역
        sizes ="(min-width : 1000px) 700px"
            최소 길이가 1000이상 일 때 의미 -> 700px로 변환
        *** 이미지의 "출력크기+최적크기" 함께 지정하는 개념 ***
        *** sizes 와 width 같이 사용하면 width가 우선 ***
    crossorigin
        설명 : 가져오기가 CORS를 사용하여 수행되어야하는지 여부
        값   : anonymous, use-credentials
    ismap
        설명 : 서버측 이미지 맵으로 지정해 클릭하여 좌표를 쿼리스트링으로 서버에 전송할지 여부
        값    : bool
        특징  : <img />가 유요한 href 속성을 가진 <a>의 하위 요소인 경우에만 적용

### audio

    설명 : 소리 콘텐츠(MP3)를 삽입
    html 만으로는 몇초부터 재생이나 세부적인 속성은 수정 불가
        -> js를 통한 제어
    auto play
        설명    : 준비되면 바로 재생
        값      : bool
    controls
        설명    : 제어 메뉴를 표시
        값      : bool
    loop
        설명    : 재생이 끝나면 다시 처음부터 재생
        값      : bool
    preload
        설명    : 페이지가 로드될 때 파일을 로드할지의 지정(힌트제공)
        값      : 1. none(로드 x)
                  2. metadata(metadata만 로드)
                    사용자가 설정 하지 않아도 preload
                  3. auto(전체 로드)
    src
        설명    : 콘텐츠 URL
        값      : URL
    muted
        설명    : 음소거 여부
        값      : bool

### video

    설명 : 동영상 콘텐츠(mp4)

    auto play
        설명    : 준비되면 바로 재생
        값      : bool
    controls
        설명    : 기본 설정 제어메뉴
        값      : bool
    crossorigin
        설명    : 가져오기가 외부에서 인지 판단
        값      : anonymous, use-credentials
    loop
        설명    : 재생이 끝나면 다시 처음부터(무한루프)
        값      : bool
    poster
        설명    : 동영상 썸네일 이미지 URL
        값      : URL
    preload
        설명    : 페이지가 로드될 때 파일을 로드할지의 지정(힌트제공)
        값      : 1. none(로드 x)
                  2. metadata(metadata만 로드)
                    사용자가 설정 하지 않아도 preload
                  3. auto(전체 로드)
    src
        설명    : 콘텐츠 URL
    width
        설명    : 가로너비
    height
        설명    : 세로너비

### figure, figcaption

    figure
        설명 : 이미지나 삽화, 도표 등의 영역을 설정
    figcaption
        설명 : figure에 포함되어 있는 이미지나 삽화 등의 설명을 표시

    figure로 감싸고 figcaption으로 설명

```html
<figure>
  <img src="/images/heropy.png" alt="HEROPY" />
  <figcaption>HEROPY 이미지 입니다!</figcaption>
</figure>
```

### iframe

    설명 : 다른 HTML 페이지를 현재 페이지에 삽입
    1. name
        설명    : 프레임의 이름
    2. src
        설명    : 포함할 문서의 URL
        값      : URL
    3. width
        설명    : 프레임 가로 너비
    4. heith
        설명    : 프레임 세로 너비
    5. allowfullscreen
        설명    : 전체 화면 모드 사용 여부
        값      : bool
    6. frameborder
        설명    : 프레임 테두리 사용 여부
        값      : 0,1
        기본값  : 1
    7. sandbox
        설명    : 보안을 위한 읽기 전용으로 삽입
        값      : 1. bool
                  2. allow-form        : 양식제출 가능
                  3. allow-scripts     : 스크립트 실행 가능
                  4. allow-same-origin : 같은 출처(도메인)의 리소스 사용 가능
        보안성으로는 높아질 수 있지만 js 코드가 동작 안하거나 페이지 문제가 생길 수 있음
    페이지 연결거부 뜨면 아래와 같은 코드로 작성

```html
<div class="video-container" style="text-align: center; margin-top: 25px;>

<object
  type="text/html"
  width="100%"
  height="500"
  data="//www.youtube.com/embed/k9_XH1YibcY"
></object>
```

### canvs

    *** 영역 만을 설정하는 것이지 그리는 것은 js를 활용 ***
    설명 : Canvas API , WebGL API 사용 하여 그래픽이나 애니메이션 랜더링(범위)
    1. width
        설명 : 캔버스의 가로 너비
    2. height
        설명 : 캔버스의 세로 너비

### script

    설명 : 스크립트 코드를 문서에 포함하거나 참조(외부 스크립트)

    1. async
        설명    :   스크립트의 비동기적 실행 여부
        값      :   bool
    2. async
        설명    :   변도의 도메인을 사용하는 사이트(CORS)의 오류 로깅을     허용하기 위해 사용
        값      :   anonymous, use-credentials
    3. deffer
        설명    :   문서 파싱(구문 분석)후 작동 여부
        값      :   bool
        html 모든 내용 파싱 한뒤 실행
        실무에서는 deffer를 사용 한뒤 전체 파싱 한뒤 사용하거나
        script를 script가 필요한 구문 밑에 사용하기도 한다.
    4. src
        설명    :   참조할 외부 스크립트 URL
        값      :   URL
        src를 이용한 외부 스크립트 참조하면
        console log의 구문은 무시 됨
    5. type
        설명    : MIME 타입

### noscript

    설명 : 스크립트를 지원하지 않는 경우에 삽입할 HTML 정의
    sandbox를 통해 자바 스크립트를 지원하지 않는 환경 구현 가능
