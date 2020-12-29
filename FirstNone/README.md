# 절대경로, 상대 경로

![image](https://user-images.githubusercontent.com/54137044/103299003-ec6e2000-4a3e-11eb-8a5e-387638804978.png)

## 상대 경로

./(생략가능)
img src="assets/images/xxx.jpg"
확실하게 상대경로 보여주고 싶다면 ./ 붙여줌
../(밖으로 나가는 행위)
background:url("../assets/images/xxx.jpg");

-  경로가 달라질 수 있음 -> 상대경로

## 절대 경로

http(https)
img src="https://naver.com/assets/images/xxx.jpg"
background:url("https://naver.com/assets/images/xxx.jpg");
/(//)

-  경로가 어디서 호출하든 같음
-  만약 호출하려는 주소와 작업 주소가 같은 경우 /로 주소 생략 가능

### 주석

프로그램의 설명을 메모리를 차지 하지 않으면서 명시 가능

```html
<!-- 이 링크는 구글 홈페이지로 이동합니다. -->
```

```javascript
// const a = NULL;
```

### 특수 기호

HTML의 띄어쓰기는 한 번만 인식이 되도록 되어 있음
&nbsp; (띄어 쓰기)
&lt;div&gt;

| 기호 | 영어(발음)                               | 한글                    |
| ---- | ---------------------------------------- | ----------------------- |
| `    | Grave(그레이브)                          | -                       |
| ~    | Tilde(틸드)                              | 물결표시                |
| !    | Exclamation(엑스클러메이션) mark         | 느낌표                  |
| @    | At(엣) sign                              | 골뱅이                  |
| #    | Number(넘버) sign, Sharp(샵)             | 샵, 우물 정             |
| $    | Dollar(달러) sign                        | 달러                    |
| %    | Percent(퍼센트) sign                     | 퍼센트                  |
| ^    | Caret(캐럿)                              | -                       |
| &    | Ampersand(엠퍼센드)                      | -                       |
| \*   | Asterisk(에스터리스크)                   | 별표                    |
| -    | Hyphen(하이픈), Dash(대쉬)               | 마이너스                |
| \_   | Underscore(언더스코어), Low dash(로대쉬) | 밑줄                    |
| =    | Equals(이퀄) sign                        | 이꼬르                  |
| “    | Quotation(쿼테이션) mark                 | 큰 따옴표               |
| ‘    | Apostrophe(아포스트로피)                 | 작은 따옴표             |
| :    | Colon(콜론)                              | 땡땡이                  |
| ;    | Semicolon(세미콜론)                      | 털 달린 땡땡이          |
| ,    | Comma(콤마)                              | 쉼표                    |
| .    | Period(피리어드), Dot(닷)                | 점, 마침표              |
| ?    | Question(퀘스천) mark                    | 물음표                  |
| /    | Slash(슬래쉬)                            | -                       |
|      |                                          | Vertical bar(버티컬 바) |
| \    | Backslash(백슬래쉬)                      | -                       |
| ()   | Parenthesis(퍼렌서시스)                  | (소)괄호                |
| {}   | Brace(브레이스)                          | 중괄호                  |
| []   | Bracket(브래킷)                          | 대괄호                  |
| <>   | Angle Bracket(앵글 브래킷)               | 꺽쇠괄호                |

[특수기호링크](https://www.freeformatter.com/html-entities.html)

```html
<body>
   Hello&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;world!
   <h1>&lt;div&gt;&lt;/div&gt;</h1>
</body>
```
