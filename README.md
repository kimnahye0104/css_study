f# CSS (Cascading Style Sheet)
## CSS 작성 전 준비사항
* html 문서 준비 (태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles으로 css 파일 배치
* ex) index.html, index.css
## CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부스타일 시트**
* html 파일 내에서 head 태그 안에 style태그로 구분해서 작성하는 **내부 스타일 시트**
* 외부 스타일 시트의 장단점 :
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다.
* 내부 스타일 시트의 장단점 :
- 장점 : html파일 내에 작성하여 태그와 한꺼번에 보기 편하다.
- 단점 : 2개 이상의 html 파일을 동시에 디자인 관리하는 것이 불가능하다.
## CSS 선택자
1. 태그 선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. class 선택자 : `<h1 class="a"></h1>` -> `.a {속성:값;}`
3. id 선택자 : `<h1 id="b"></h1>` -> `#b {속성:값;}`
4. 자손선택자 : `<h1><em><span></span></em></h1>` -> `h1 em span {속성:값;}`
5. 자식선택자 : `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## CSS 디자인하기
* css 작성 전 html이 미리 디자인이 되어 있으면 안된다.
* **html을 디자인 초기화 하는 작업이 css 디자인 전 반드시 선행되어야 한다.!!!**
* 초기화 css : `reset.css` 공통파일(날짜,프로젝트명 표기 금지)
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹글꼴(추천)을 연결할 수 있다.
* "메인 글꼴", "후보 글꼴", (후보제한없음 sans-serif)
* 후보글꼴은 메인글꼴과 비슷한 글꼴으로 연결해야 한다.
* 글꼴에 한글, 공백이 있으면, 따옴표가 필요하다.
## font-size
* 웹글꼴 평균 16px
* 사용 단위 px, %, em, rem
* 절대값: px, 상대값: %, em, rem (권장-사용하는 디바이스에 따라 크기를 조정하겠다.)
## 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1)
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {}` : 3+2+2+1 = 8점
* `#box #a .b p {}` : 3+3+2+1 = 9점
* `#wrap #box .a {}` : 3+3+2 = 8점
* `#wrap .a .b p {}` : 3+2+2+1 = 8점
2. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#wrap #top .top_left .btn a{}`
* `#wrap .mainimg .btn a{}`
* `#wrap .top_left .icon1 p a{}`
* `#wrap .top_left #icon p a img{}`
## color
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은색을 사용한다.
* auqa, lime, yellow, coral, 등등
* 헥사코드 입력 최소값 0 ~ 최대값 f RGB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #Hex #000000 == #000, #ff00cc -> #f0c
* rbga(red,green,blue,alpha) => rbga(0,0,255,0.6) : 블루 색상으로 alpha 투명도 60%
## box css
* **width, height, display, box-sizing, box-shadow**
### display
`block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* 디자인을 위해서 필요할때 display속성을 활용해 inline과 block을 설정해준다.
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기 인식, (그외 크기인식 불가능)
* `inline-block` : 내용만큼 크기 인식, (크기 추가설정가능), 옆으로 정렬
### box-sizing
* `box-sizing : border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 안쪽여백(padding)까지 포함해서 계산하는 속성
* 속성 미적용시 : w100 + h100 + padding-top20 = 100x120
* 속성 적용시 : w100 + h100 + padding-top20 = 100x100
### width, height
* 요소의 너비와 높이
* 절대값 px, 상대값 %, 화면 상대값 vw, vh
* 상대값 처리는 0~100% 사이 값만 사용한다.
### box-shadow
* `box-shadow : x축 y축 blur값 색상;`
* 그림자를 넣어주는 속성
* 색상은 `rgba(red,green,blue,alpha값);`로 하면 투명도까지 미세하게 조정 가능.
### border-radius
* `border-radius: 값(px, %);`
* 둥근 테두리를 만들어주는 속성
* 원을 만드려면, 절대값 = 가로세로(100px)의 1/2인 50px
* 원을 만드려면, 상대값 = 가로세로(100px)의 50% (절반값%)
## table (block tag)
* **가로 한줄 1행, 입력 칸 1개 1열**
### tr, th, td
* tr = 행, td = 내용 열
* `td` 는 반드시 행(tr) 안에 존재해야 함.
### thead, tbody, tfoot
* 표 태그 table 관련 태그로, 표의 header, body, footer
### line-height
* 높이 값만큼 주면, 글자 위 아래 여백이 들어간다. (따라서 한줄일 때만 line-height를 쓴다.)
### colspan, rowspan
* 행과 열을 병합해주는 속성
* `colspan="Num"`: Num에 자신을 포함해 수평(행)으로 합칠 칸의 개수 적기 
* `rowspan="Num"`: Num에 자신을 포함해 수직(열)으로 합칠 칸의 개수 적기
## form 요소와 속성'
### `<form action="#" method=""></form>`
* action :
* method :
* fieldset :
* legend :
## input 태그
### `<input type="" name="">`
* type
* name
* readonly
* ㄴ ex) `value="초기화 숫자" readonly` : 읽기용이라 수정이 안된다.
* disabled
* ㄴ ex) `value="초기화 숫자" disabled` : 선택 자체가 활성화가 되지 않는다. (주로, 자바스크립트 동적 기능과 연결할 때 사용)
* autofocus, autocomplete
* value
* placeholder
* value와 placeholder
* maxlength
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접입력가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* ex) `name` : 입력양식(데이터구분용) /  선택양식( 데이터구분,(개별데이터X, 그룹데이터구분용) )
* `value` : 입력양식(초기값) / 선택양식(개별데이터구분용)
### input 속성 적는 법
* 속성선택자(form 관련 주로 사용)
* `태그[속성]` : 태그에 속성이 **있을 때**
* `태그[속성=값]` : 속성의 **값이 이것일 때**
* `태그[속성^=값]` : 속성값이 이것으로 **시작할 때**
* `태그[속성$=값]` : 속성값이 이것으로 **끝날 때**
* `태그[속성*=값]` : 속성값이 **이것을 포함할 때**
* `a`와 `input`의 차이점 : `input 태그`는 사용자 별로 고유한 화면(ex 로그인 접속 페이지)이나 효과가 나타나야 할 때 주로 사용한다. (`a태그`는 사용자가 모두 동일한 페이지를 보게끔 할 때 주로 사용한다.)
* `autofocus` : 보통 검색기능은 "검색창"이 활성화되어 있다.
* `autocomplete="on"` : 검색 기록이 있을때 자동으로 검색어가 뜨게 함.
### `<textarea></textarea>`
* `textarea` : 여러 줄의 글자가 들어가야 할 때. ex) 리뷰 쓰는 창.
* `row=""`
* `cols=""`
* 사용용도 및 주의사항
### input type="" 입력 필드 속성
* `input type="" name="" value="..."`
## float
**블록 요소의 흐름(flow)을 변경하기 위해 사용하는 레이아웃 배치 속성**
* 장점 : 오래 사용해서 호환성이 좋다
* 단점 1 : center는 할 수 없고, left와 right만 가능하다.
* 단점 2 : float적용시, `width` 값을 인식 못하는 경우 발생.
* 2번 이상 중복해서 쓸 경우, float는 역순이 된다. (ex-4,3,2,1)
### float 부유개념 이해
* 부모는 자식의 크기만큼 크기를 인식 (따라서 자식의 높이 만큼 부모 높이가 달라짐)
* 자식이 float를 가지게 되면, 자식이 떨어지므로(=float=부유하다) 부모가 크기를 인식하지 않게 됨.
### 부모가 크기를 인식 못하게 될 경우, 해결 방법
**자식에 float를 적용함으로써 생기는 부모인식오류 해결**
* 1) 부모 스스로 값을 가지게 함. 해결법 1. 크기를 직접 적용한다. (비추천)
* 2) 가상 요소를 만들어준다. 2. 자식포함 크기 재인식 속성
* 3) 해결법 3. 가상 공간 설정 (추천) `선택자(float준자식의 부모)::after`