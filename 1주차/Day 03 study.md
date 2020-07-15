## HTML 구조

* Node = 가장 작은 단위 , 노드들이 모여서 전체 document를 구성한다 
* Passing 할때 DOM트리가 생긴다

## UI제작툴 sketch / figma

- 크로스 플랫폼이 가능하고, 클라우드 버젼이 있다
- UI 제작 툴을 어느정도 알아야 하는 이유는 디자인 시안을 분석할줄 알아야되기 때문에

## BOX MODEL

- 랜더링시 박스모델의 크기를 결정하는 요인 (width,boder,padding,margin)
- Box-sizing = content-box / boded box
- content box는 css에서 height와 width 속성을 설정할 때 그 크기가 가르키는 부분을 content(내용) 부분만을 대상으로한다
- border box는 css에서 height와 width 속성을 설정할 때 그 크기가 가르키는 부분을width,margin,padding, border를 다 포함한 영역을 대상으로 한다 
- content 영역만을 대상으로하기때문에 content-box 는 margin의 상하가 겹치는 현상이 있다
- content-box는 누가 먹이면 커지고 Border-box는 컨테츠가 추가되도 

## FLOAT

* Float 속성은 요소를 공중에 띄워서 정렬을 하는 방식

1. float의 하위 요소에 css로 clear속성으로 left,right,both를 하면 띄움요소를 취소시킨다
   -  clear 속성이 구형문법이라 잘 사용하지 않는데 그 이유가 띄움요소를 취소시키면서 내려온 블럭들이 서로 밀리고 자리를 잡는 과정에서
   - 겉으로 보기에는 이상이 없을 수 있지만, 중첩되는 margin값이 생겨나면서 구조적인 오류를 만들어낸다 

2. 부모요소인에 Overflow : hidden(auto,scroll) = 을 주면 독립적인생성하는건데 overflow속성을 이용함으로써  부모요소의 너비와 높이를가져오는데 이를 읽는 과정에서 읽어버렸던 자식요소를  다시 읽는 방식으로 응용을 한거다 ,영역밖으로 벗어날시 콘텐츠가 요소에따라 감춰지거나 , 잘리거나 , 스크롤형식이 생겨난다 
3. 2중 float을 사용해야 할때는 박스모델을 한번더 감싸는 개념을 생각해라.

3. 가상요소선택자 ::after 

   - Content: ""   >>::after 가상요소에 content 가 없으면 객채 생성이 안된다

   - 가상요소를 주면 인라인 박스를 생성한다

   - clear :both는 블럭에만 허용되기 때문에 Display :block을 선언한다.

   - after가상요소 선택자는 메인의 마지막 자식요소를 부여한다

   - 그리고 html의 선택자를 main clearfix로 선언해준다

   - css의 선택자는 clearfix ::after 로 선언해준다 이때 main clearfix로 선택자를 지정하지 않는이유는

     html의 부모요소의 클래스이름에 clearfix를 주면 css가 재사용이 가능하기때문에 반복작업 하지 않아도 된다 .

#### 그 외 css를 html 문서에 Link 태그로 연결하지 않고 @import url 을 쓰는이유는  sass나 프레임워크에서 사용할 때import를 하나의 파일로 만들어서 훨씬 좋은성능으로 유지보수를 하기 위함이고 배포와 개발을 분리하는 모듈 시스템에 익숙해 지자 

----

## FLEX

Flex -direction : column,row (reverse) // auto 값은 row

Flex - wrap : wrap, wrap-reverse //auto 값은 nowrap

Flex - flow : direction 값 wrap값 의 단축속성 

- Flex-direction 의 값이 row가 주축이면 그 안의 flex-items 들의 배치를 justify-content로 정렬하고

- Flex-direction 의 값이 column이 주축이면 align - items로 정렬한다

-  효율적인 배치 방법중에 하나는 flex-flow의 값을 row로 주고 nowrap을 주게되면 여러상황에서 좀더 유기적인 컨텐츠 이동이 가능하다 

  --->> 이유를 잘 모르겠다 내일 더 찾아봐야겠다

Justify-content :space -evenly = 두 항목 사이의 간격 (가장자리 간격)이 동일하도록 항목이 분산된다 (IE 11 이후 지원)

Flex-shrink: item의 감소 너비 비율을 설정한다

Flex-basis :item의 기본 너비를 설정한다

Flex-grow :shrink,basis을 함께 사용하는 축약속성 , item의 증가 너비 비율을 설정한다 

만약 Flex : 1; 로 작성했다면 shrink,basis의 auto 값이 적용되는데 shirink는 1 , basis의 기본값이 auto 이지만 축약 속성에서는 0이된다 

* Flex -grow 속성을 쓰면 화면이 줄어들거나 늘어날때 그 비율대로 움직이기때문에 따로 값을 지정해주지않아도 되서 편리하다

 ### Css tricks flex를 검색하면 flexbox 를 직관적으로 확인 할 수 있다.


