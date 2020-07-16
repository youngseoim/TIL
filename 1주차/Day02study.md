#### 뜬금없이 궁금한 Canvas요소 vs SVG 요소 차이

- canvas 요소의 성능은 화면이 작거나 , 픽셀 수가 많을 경우에 좋습니다
- svg요소의 성능은 화면이 크거나, 픽셀 수가 적을경우 에 좋습니다 

![canvas와 svg 사이의 선택 기준](http://tcpschool.com/lectures/img_html5_canvas_svg.png)



#### 어제 강조한 HTML5에서 추가된 의미(semantic) 요소

* 디자인적 요소가 아닌 검색최적화 및 코드의 가독성을 위해서 semantic은 최대한 활용할 것  

| 의미 요소  | 설명                                                         |
| ---------- | :----------------------------------------------------------- |
| header     | HTML 문서나 섹션(section) 부분에 대한 헤더(header)를 정의함. |
| nav        | HTML 문서 사이를 탐색할 수 있는 링크(link)의 집합을 정의함.  |
| main       | HTML 문서의 주요 콘텐츠(content)를 정의함.                   |
| section    | HTML 문서에서 섹션(section) 부분을 정의함.                   |
| article    | HTML 문서에서 독립적인 하나의 기사(article) 부분을 정의함.   |
| aside      | HTML 문서에서 페이지 부분 이외의 콘텐츠(content)를 정의함.   |
| figure     | HTML 문서에서 그래픽과 비디오 등의 독립적인 콘텐츠(content)를 정의함. |
| figcaption | figure 요소를 위한 캡션을 정의함.                            |
| footer     | HTML 문서나 섹션(section) 부분에 대한 푸터(footer)를 정의함. |
| bdi        | 기본 출력방향과는 다른 방향으로 출력되는 텍스트를 정의함.    |
| mark       | 하이라이팅된 텍스트를 정의함.                                |
| details    | 사용자가 보거나 숨길 수 있는 추가적인 설명문을 정의함.       |
| summary    | details 요소에 나타날 내용을 정의함.                         |
| dialog     | 다이얼로그(dialog) 박스나 다이얼로그 윈도우를 정의함.        |
| menuitem   | 사용자가 팝업 메뉴(popup menu)를 통해 선택할 수 있는 메뉴의 아이템(menu item)을 정의함. |
| meter      | 정해진 범위 내의 스칼라 치수를 정의함.                       |
| progress   | 작업에 대한 진행 정도를 정의함.                              |
| ruby       | 루비(ruby) 문자를 선언함.                                    |
| rt         | 본문 위에 나타날 문자를 정의함.                              |
| rp         | 루비(ruby) 문자를 지원하지 않는 브라우저에서만 나타날 내용을 정의함. |
| time       | 날짜와 시간을 정의함.                                        |
| wbr        | br 요소와는 달리 긴 단어가 화면의 맨 끝에 오면 상황에 따라 줄 바꿈 할 곳을 미리 정의함. |

#### 웹 접근성과 웹표준 ( HTML5, CSS3 )

- Web 기술의 설정 값 
  - html = 건강한 신체 / css = 근사한 스타일링 / javascript =스마트한 두뇌 
- 웹 표준을 만드는곳 W3C
  - 추천 책 제프리 젤드만의 웹표준 가이드 
- Web accessibility(접근성)
  - 장애에 대한 이해 
  - 환경에 대한 이해
    -  다양한 Platform / Cross Browsing / SEO(search engine optimization) / 저사양 또는 저속회선 

### 새로운 표준 HTML5 - Markup

- w3c가 xhtml 1.0을 구체화 하기위해 xhtml2.0작업을 진행중이였으나 하위호환상에 치명적인 문제

  이를 본 브라우저 Vendor회사들이 협업하여 새로운 W3C와는 별개로 Web Application 1.0과 Web Forms 2.0을 만들어 냈고

  그이후에 W3C의 XHTML2.0을 공식적으로 실패를 인정한후 협업하여 현재의 HTML5를 탄생시켰습니다.

- HTML5 컨텐츠 모델 한눈에 보기 http://darum.daum.net/convention/html/html5_elements

#### HTML5 Outline

- 화면으로 보면 아무런 차이가 없어 보이지만 HTML5는 기존의 HTML 4.01나 XHTML 1.0과는 다른 점이 있습니다, 눈으로 보이지 않는 어떤 구조가 자동으로 생겨나고. 눈에 보이지 않기 때문에 '암묵적인 구조 생성'이라고 기존에도 존재했었는데 이것은 HTML5에서는  아웃라인(outline) 개념을 도입했기 때문에 나타나는 현상입니다.
- HTML5 Outliner 웹 서비스 페이지(http://gsnedders.html5.org/outliner/) ㅡㅡ 아웃라인구조 한눈에 확인하기
- HTML4.01과 XHTML1.0에서는 문서트리구조로 표현되고 html 에서 head,body로 가지가 뻗어 나가고 그 둘의 각자 영역에서 자식과 자손을 포함하는 관계도(model)을 만듭니다, 이러한 관계를 문서 객체 모델(Document Object Model) 줄여서 DOM으로 부릅니다 
- 이때문에 body안에 있는 태그들의 부모,형제,자식 요소들의 랜더링 방식이 HTML5와는 달라집니다.
- 주의 할 점은 Semantic 태그들의 목적이 분명하기 때문에  목적에 맞게 써야하고 각 섹션은 내부에 제목을 하나만 가집니다 두개를 가지게 된다면 제목의 레벨에 따라서 형제섹션 2개로 나눠 집니다.
-  Outline을 잘 지켜줘야 하는 이유는 웹접근성에도 필요하고, seo 관점으로 봤을때도 올바른 곳에 올바른 sementic 태그를 사용해야 검색최적화도 잘이루어지고 코드의 구조적으로도 무너지지않고 가독성이 올라가기 때문입니다 // 내가 알고 있는게 맞는지 추가로 더 알고 있어야 할 내용이 있는지 김데레사 강사님한테 물어보기 .

#### HTML5 API의 종류 

* HTML API란 자바스크립트 기술을 편리하게 이용할수 있도록 도와주는 도구 
  * Application cache, web storage ,web sql database/indexed database

### CSS

- 1996년 w3c 주도하에css lever1 발표
- 1998년 css level2
- css level 3 는 공식적으로는 존재 하지않고 모든 명세가 포함된게아니라 모듈단위로 개발되며, 최신기술을 통상 css3이라고 부릅니다 , 현재도 계속 추가되는 상태입니다.

#### css 네이밍 종류

p.c 파스칼 케이스 = MainContent =이름 앞에 대문자사용

c.c 카멜 케이스 = mainContent = 첫번째만 소문자 사용 

k.c 케밥 케이스 = main-content = 중간에 하이폰을 사용 

s,c 스네이크 케이스 = main_content = 중간에 언더바를 사용 

#### css 방법론

- OOCSS (Object Oriented CSS)
- BEM (Block Element Modifier)
- SMACSS (Scalable and Modular Architecture for CSS
- https://github.com/hohoya33/css-methodologies.  ㅡㅡ 방법론 정리 

#### 그 외에 배운 것

- CSS 배치 - HTML을 설계하고 난 후 바디라인의 설계를 꼭 먼저 구상한  후 전체적인 틀을 코딩할 것
  - Float / position(움직이지 않아야 하는곳,부모요소를 따라가야하는곳) / flex / grid 

* css 삽입 방법 3가지
  * external

    *  디자인과 데이터의 완전 분리된 방식으로 css 파일을 만들어서 사용
    * 스타일이 하나의 파일로 관리되므로 유지보수가 쉽고 가독성이 뛰어납니다 
    * 스타일이 하나성능 관점에서 효율 좋음 캐쉬에 저장해놓고 불러온다 

  * Embadded imternal

    * html문서에 body 제일상단이나 하단에 style/style을 지정해서 쓰는 방법

      inline보다 쉬운 유지보수, style 블럭이 별도로 있어서 코드 가독성이 쉽다

      단점은 전체적인 사이트 스타일 변경시 모든 페이지에 들어가서 일일이 수정해야 한다 

  * inline

    * html문서에 직접 스타일을 적용시켜서 사용 
    * 데이터와 디자인이 분리가 안되서 유지보수가 어렵기때문에 요즘엔 사용x 

* color grb = #rrggbb 16x 16 = 256 칼라,  2자리씩 중복이면 단축 가능 

* Font-size = 기본 16px;

* 단위

   rem = Root 값을 기준으로 계산

  em  = 부모에게서 상속을 받기 때문에 원치않게 크기가 커지거나 작아질 수 있다, 상속 관련 이슈가 있다, 

   고려해야 할 사항 1.상속 2.겹침 3. 우선순위 

#### Normalize.css

- 브라우저마다 다른 스타일들을 하나로 통일 시켜주기 위한 것 (일관성)