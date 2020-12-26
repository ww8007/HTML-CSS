# META
-------------------------------
### ISO 639-1
    국가별 언어 코드 ko -> 한국
    국가 코드 kr
    언어 표시 ko
### head tag and body tag
    범위를 나누는 용임 -> 어렵게 생각할 필요 x
    head 
        - 문서의 정보
        title <title>
        - 문서의 제목
        - 스타일 직접 입력
        - 스타일 외부에서 가져와서 연결
    body 
        문서의 구조
    !DOCTYPE html -> html5 
### meta
    [html 요소 레퍼런스 참고](https://developer.mozilla.org/ko/docs/Web/HTML/Element)
    닫히는 구조가 아닌 <meta> 단일로 사용
    1. <meta charset> -> 문자 인코딩 방식 
        "UTF-8"     :   조합형
        ex) ㅈ ㅏ ㅇ ㄷ ㅗ ㅇ ㅎ ㅕ ㄴ 
        -> 완성된 문자가 아니면 문자가 깨질 수 있음
        "EUC-KR"    :   완성형
        ex) 장동현
        -> 조합해서 만들기 때문에 안정성이 높아짐
        *문자 인코딩 방식이 가장 먼저 있는게 맞음
    2. <meta name="viewport" content="width=device-width, initial-scale=1.0">
        viewport -> 반응형 웹사이트 
        widht = device-widht -> 기기의 너비
        initial-scale -> 나중에
    3. <meta http-equiv="X-UA-compatible" content="IE=edge">
        인터넷 익스플로러 최신 버전 사용
    4. property 
        특정한 사이트에서 공유해서 체크할 때 og:titile
    5. type 생략 가능
    6. ./ -> 상대적 주소
    7. base href -> 상대 경로를 정해버려서 link테그에서 정해주지 않아도 된다.
        *** base 상대경로는 하나로만 사용가능 ***
    
### body 