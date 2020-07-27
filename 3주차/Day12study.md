 

#### @media 미디어쿼리

속성 값 all screen print

특성 

- width,height ( max,min), 
- orientation 뷰포트 방향(portrait, landscapte) 



#### 간단한 자바스크립트 개념 (하루에 조금씩 예습)

값을 만들어내는 간단한 코드를 표현식 expression 

true 라는 표현식은 true라는 값을 만들어낸다 

26이라는 숫자는 26이라는 값을 만들어내기 때문에 표현식 이라고 한다

1000+900+90+4 = 1994 라는 값을 만들어내기 때문에 표현식이다 

"anna " / "hello" + "javascript "  = hello javascript 문자열도 표현식이다 



하나 혹은 여러개의 표현식이 모여 문장을 이룬다 statement 

모든표현식은 문장이 될 수 있다 

한줄에 문장이 하나인경우에는 세미콜론을 붙이지 않아도 되지만 관례적으로 붙인다

한줄에 여러문장을 적을 경우 세미콜론으로 문장을 구분해야합니다 .



조건문 if 와 반복문 for 도 문장 입니다

이경우는 중괄호 뒤에 세미 콜론을 붙이지 않습니다 .



키워드와 예약어 (keywords & reserved words)

-  키워드
  - 자바스크립트에서 특정한 목적을 위해 사용하는 단어
  - 이러한 키워드들은 예약어로 지자ㅓㅇ되어있다 .
  - var = 변수를 선언 할 때 사용하는 키워드
- 예약어
  - 프로그램을 작성할 때 변수명,함수명 등 이름으로 사용할 수 없는 단어 
  - reture  = 예약어이 기때문에 변수명으로 사용할 수 없다
  - for =  예약어이기 때문에 함수명으로 사용할 수 없다
- Future reserved keywords 
  - 앞으로 특정한 목적을 위해 사용할 가능성이 있어서 사용할 수 없는 예약어

### Q 태그

- 짧은 인용문에 사용하고 긴 인용문의 경우 blockquote를 사용한다 

- q의 태그에는 quotes속성이 기본으로 들어있다 
  -  태그안에 있는 내용은 겹따옴표 안에 담기게 되는데 이때
  -  겹따옴표는 가상요소클래스 before, after로 생성되고
  - 겹따옴표에 css효과를 주려면 q 클래스 이름에 before,after가상요소 선택자로 지정해줘야한다 

```css
.slogan-brief q::after{
  content:"";
} 
```

- 위에 태그는 before에있는 겹따옴표만 남기고 after에있는 겹따옴표는 삭제해주기 위해 컨텐츠 값을 null로 부여해줬다

### Small 태그

- 덧붙이는 글이나 ,저작권과 법률표기등 작은 텍스트를 나타낸다.
- Default 값은 small 더 작은글자는 x-small을 지정해주면 된다

### Display:Grid

- 그리드 컨테이너(container)는 행(rows)과, 열(columns)을 가지며 그리드 아이템(items)을 배치할 수 있다
- Grid line 
  - 그리드를 그리는 가로/세로 선을 말한다 
- Grid track
  - 그리드 트랙은 그리드 라인 사이의 행 또는 열 공간을 말한다.
  - row,coulmn의 연속된 공간
- Grid cell
  - 그리드 셀은 4개의 그리드 라인이 묶여 그려지는 가장 작은 단위(유닛)다.
  - <img width="304" alt="스크린샷 2020-07-27 오후 8 04 34" src="https://user-images.githubusercontent.com/68043654/88535238-8d961c00-d044-11ea-8b70-12ebf382b027.png">
- Grid area
  - 그리드 에어리어는 그리드 유닛이 묶인 영역으로 고유한 식별자를 가지며, 식별자를 통해 요소를 배치할 수 있다.
  - 그리드 라인이 모여 묶여지는 공간을 그리드 에어리어 라고 한다.
- Grid gutters
  - row, coulmn 사이의 간격(gap)을 말한다
  - Grid gap 속성으로 제어

### 요약 (출처:https://uid.gitbook.io/css-grid/css-grid-term) 

<img width="760" alt="스크린샷 2020-07-27 오후 8 09 21" src="https://user-images.githubusercontent.com/68043654/88535618-380e3f00-d045-11ea-9e12-e2674c0cfb9c.png">

### 오늘 배운 Grid 배치 방법 두가지

1.Grid-template-area를 이용한 직관적인 배치 

- Grid-template: 열과 행, 열과 행의 사이즈 
- Grid-template-areas: 로 grid-items 위치 배정하는 방식 

``` css
.container{
  background-color: silver;
  height: 100vh;  --높이를 100%사용 
  display: grid;
  grid-template:repeat(5, 100px)/repeat(4, 1fr); --- 5행(100px),4열(1fr는 아이템들이 1:1의 비율로 배치)
  grid-template-areas: "header header header ."  -4열중에 3열까지만 아이템을 배치하고 4열은 .을찍어서 비워줌
                       ". slogan slogan slogan"  
                       "main main main visual"
                       "main main main sidebar"
                       "footer footer footer sidebar";
                       
  grid-column-gap: 20px;
}
```

- Areas에 직관적으로 보이는 저 위치대로 item들이 배치된다

#### 결과

<img width="766" alt="스크린샷 2020-07-27 오후 8 34 32" src="https://user-images.githubusercontent.com/68043654/88537556-bddfb980-d048-11ea-92f6-6bfe44f60808.png">

2. Grid-column, row값으로 배치해주기 

   ```css
   .container{
     background-color: silver;
     height: 100vh;  --높이를 100%사용 
     display: grid;
     grid-template:repeat(5, 100px)/repeat(4, 1fr); --- 5행(100px),4열(1fr는 아이템들이 1:1의 비율로 배치)
   .header{
     background-color: yellow;
     grid-column: 1/4; 행의 첫번째 라인부터 네번째 라인까지 , 총 3칸의 영역 차지
     grid-row: 1/2;    열의 첫번째 라인부터 두번째 라인까지 , 총 1칸의 영역 차지 
   }
   .visual{
     background-color: pink;
     grid-column: 4/5;
     grid-row: 3/4;
   }
   .main{
     background-color: aqua;
     grid-column: 1/4;
     grid-row: 3/5;
   }
   .sidebar{
     background-color: lightgreen;
     grid-column: 4/5;
     grid-row: 4/6;
   }
   .slogan{
     background-color: orange;
     grid-column: 2/5;
     grid-row: 2/3;
   }
   .footer{
     background-color: brown;
     grid-column: 1/4;
     grid-row: 5/6;
   }
   ```

   #### 결과

<img width="766" alt="스크린샷 2020-07-27 오후 8 41 21" src="https://user-images.githubusercontent.com/68043654/88538074-afde6880-d049-11ea-9be2-bdb5bd36ad64.png">



#### position 헷갈리는 부분 보충설명

- absolute의 offset 값이 있는 경우 찾아가는 부모의 요소는 꼭 relative가아니여도 된다
- static이 아닌 부모요소를 찾아가기때문에 absolute와 relative둘다 가능.



#### 자꾸 놓치는부분

-  a 태그에 패딩주기, 마우스 포인터의 영역을 넓혀주기위해(접근성)
-  tab키가 위치할때 박스의 아웃라인을 벗어나 보이지 않기위해 padding 값 여유주기