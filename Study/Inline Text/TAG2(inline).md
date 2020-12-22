# TAG2(inilne)

### a

    설명 : 다른 페이지, 같은 페이지 위치, 파일, 이메일, 전화번호 등 다른 ULR 연결 할 수 있는 하이퍼 링크 설정
    ** 중요 **
    ex )    1. download         다운로드 용(힌트용 실제 다운로드 아님)
                value : bool
            2. **href**             링크 URL(생략가능)
                value :
            3. hreflang         링크 URL 언어
                value : ko, en
            4. rel              링크 URL과의 관계
                value : license, prev, next
            5. **target**           링크 URL 표시 위치
                value   : _self(현재창), _blank(새로)
                default : _self
            6. type             링크 URL MIME 타입
                value : text/html
                링크를 보낼 때 자동으로 명시되기 때문에 사용하지는 않아도 됨
    <img> src = "경로" alt " " 동일하게
    <a> href "경로"

```css
a {
  display: inline;
}
```
