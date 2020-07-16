#### 새로 알게된 태그

- fieldset = 그룹으로 묶어줄때 사용하고 legend 요소로 설명할 수 있다.

- label = for 속성에 연결할 id 값을 입력해 줘야한다 

- Input 태그

  - placeholder = 사용자가 무엇을 입력해야 하는지 알려주는 보조도구 
  - Placeholder 에는 유효성검사를위해 required태그가 필요하다 

  

복습 

box model boder 마진은 더해지고 나머지는 포함한다 

Content box 다 포함한다 

margin nomal 플로우 상태일떄 마진의 상하가 겹친다 auto 키워드 가지고 , 음수값도 가진다

padding 음수 값 못가진다 

네거티브 마진 음수값에대한 내용

 float 부유시켜서 배치 레이아웃용도로나온게아니라서 문제점이있고 다양한 해결방법을 고민해야한다

flex  = display 의 값 



----

position 

btn 같은 거 랜더링하는 순서를 생각해서 마크업을 해라 어느정보를 읽고난다음에 버튼을 눌러서 submit 이되야하는지 

#### 이미지넣을때 고려할 내용

- Accessibility = a11y (접근성) -alt 를 부여한다 

- seo -alt를 부여

- 해상도



k-wcag

static positio 기본속성 정적인 

border -radius 를 랜더링 하는 방식 

Display : inline block 을 사용하면 인라인 블록 사이에 공백 문자가 생긴다 (이것도 옛날문법)

- ​	html 을 작성할때 가독성을 위해 엔터키를 누른것이 랜더링 시 인라인블럭 에서는 공백요소로 해석이됐다 

li tag 는 상속을 활용해라 

  text-transform: uppercase; >> 상속된거 모두대문자 , 

Font-variant : small- caps = 폰트가 작은 대문자로 바꾸는속성 

a 태그가 걸린경우 클릭하기 편하도록 사이즈를 키워준다 

inline block으로 만든거  flex , float 이용해보기 



po:a 

w,h : 1px >>최소 1px을 줘야 개체로 인식을한다 

Overflow:hidden >>

Top:-9999px >>를 주면 안되는 이유는 = 보이스오버 기능을 사용할때 문서를 읽어들이다가 top좌표로 스크롤이 올라가버린다

m: -1px; / clip-path : 함수 polygon (0 0, 00, 00 ) 마스크 처리를해서 화면에서 감춘다 clip path maker search



List -style : 머지

a태그에서 lole " button "도 가능



#### Float 속성에 영향을 받는 하위요소에 position 값을 주지 않았을 때 벌어질 수 있는 문제

![스크린샷 2020-07-16 오후 7.32.33](/Users/young/Library/Application Support/typora-user-images/스크린샷 2020-07-16 오후 7.32.33.png)



menu-item 들을 float : left 속성 값을 줬을때  menu-item 의 자식 요소인 list들이 float:left 속성이 같이 먹어서 list들의 가로너비를 인식 이런식으로 원하는 menu-item들의 정렬이 이루어 지지 않고 오른쪽으로 밀려 최대 width 값을 벗어나 아래로 내려오는 현상이 생겼는데 이때 li 요소들한테 position absolute 값을 주면 

![스크린샷 2020-07-16 오후 7.50.25](/Users/young/Library/Application Support/typora-user-images/스크린샷 2020-07-16 오후 7.50.25.png)

이런 식으로 상위요소인 menu-item에 주는 영향이 사라지면서 정상적인 float : left 지정이 된다 그 후에는 absolute의 속성인 절대위치를 지정하는 left나 top 등 아무런 값이 지정되지 않았기때문에 그 자리에 그냥 남는다 . 

