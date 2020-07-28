```javascript
{let name = "apple"
console.log(name);    ==> apple 출력
 name = 'hello'				==> 변수로 이름 재 할당
console.log(name) }   ==> hello출력
```

- 중괄호 안의 내용은 안에서만 값이 불러지고 중괄호 밖에 선언된 내용은 Global요소로써 중괄호 안에서도 밖에서도 호출이 가능하다.
- 그렇기 때문에 global을 남용하면 안된다

### var의 호이스팅 문제

- Var를 어디에 선언했냐랑 상관없이 제일위로 끌어올려지는 현상
- 값은 선언이 된 후에 할당을 해야하는데 var같은 경우에는 값을 할당하고 선언해도 실행이 되는 오류가 있다
- 또 중괄호안에있는 내용은 그안에서만 작동해야하는데 var는 그런 블럭스코프를 무시하고 할당된다 .
- ES6부터는 let이

```javascript
{var age;
 age = 4
cosole.log(age) }   var가 age라는걸 선언하고 age는 4라는걸 할당했을때의 결과값이 4가 나와야하고
 
 {age = 4;
  var = age;
  console.log(age) } 값을 먼저 할당하고 선언을하면 에러가 나와야하는데 4라는 값이 출력된다
```



Contants

-  값을 한번 선언하고 할당하면 다시 값을 변경할 수 없다.
  - Immutable data type = 변하지 않는 데이터 타입 
  - 보안같은 민감한 정보를 바꿀수 없도록 미리 방지할때 사용

Let

- 값을 선언하고도 계속 값을 선언해서 바꿔줄 수 있다.
  - mutable daty type = 변하는 데이터 타입
  

---



### Grid justify, align - content와 item의 차이 

![Grid Justify,align Content와 Item의 차이-4](https://user-images.githubusercontent.com/68043654/88611971-279da900-d0c5-11ea-83af-a765837c68bb.jpeg)

### 반응형 웹디자인

-  메타태그

  -   <meta name="viewport" content="width=device-width, initial-scale=1.0">

  - viewport(보여지는화면)의 width값을 device의 width값으로 할당 , initial-scale(초기 줌 레벨)은 = 1배율설정

  - 그외에 maximum, minimum, user scale등이있고 유저스케일은 유저가 화면을 키우고 줄이는 옵션을 말한다

- 반응형 Flex 배치시 고려할 점
  무조건적인 정답은아니지만 수직 정렬을 할때도 coulmn보단 row로 배치를한다
  flex-flow : row wrap으로 바꾼상태에서 width값을 지정해줘서 요소들을 넘치게해서 줄바꿈으로 수직정렬 시켜준다 
  이 방법이 더 나은 이유는 반응형으로 작업을 할때 viewport가 줄어들면서 넘치는 요소를 떨어뜨리는 형식으로작업을하면 더 직관적인데 column으로 작업을하면 세로로 배치된 요소의 위치를 order같은 속성으로 움직여줘야하기 때문에 row로 작업하는편이 더 나은 방법인것같다 .

### 반응형 작업시 네비게이션 처리

<img width="571" alt="스크린샷 2020-07-28 오후 7 57 45" src="https://user-images.githubusercontent.com/68043654/88657358-c39ed300-d10c-11ea-9ec7-e699000c5b00.png">

- 처음에 생각한 방법은 애초에 데스크탑부분에서는 접근성을 고려할 필요없이 없는부분이기때문에

   nav 부분을 display:none을 해놓고 모바일크기에 나타나는  메뉴 아이콘을 눌렀을때 

   none을 block 처리하는 방식으로 배치하려고 생각했는데 display:none을 할 경우 버튼에 애니메이션이 적용되지 않는단점이 있다

- 강사님이 말씀해주신 2번째 방법은

  - ```css
    .appNavigation{
      position: fixed;  fixed는 viewport를 기준으로 배치된다 
      top: 0;
      left: 0;
      width: 70vw;
      height: 100vh;
      transform: translateX(-100%);
    }
    ```

  - nav 메뉴에 Position값을 fix해주고 top,left값을 0을 줘서 왼쪽 상단에 위치시킨다, 그 후에 

  - transform 속성의 translateX좌표값을 -100%로 선언해줘서 화면 밖으로 위치시켜준다 

  - 그 후에 속성으로 메뉴 버튼을 눌렀을때 translate의 좌표값을 0이나 none으로 바꿔줘서 화면에 출력해준다 



### 반응형 웹페이지 header영역 (모바일부분만)

- <img width="802" alt="스크린샷 2020-07-28 오후 8 49 01" src="https://user-images.githubusercontent.com/68043654/88661715-eed8f080-d113-11ea-8bbe-9fd9f96326ff.png">



- 레이아웃 마크업

- ```html
  <body>
    <div class="container">
      <header class="appHeader">
        <h1 class="brand resetMargin">
          <a href="index.html">
            <img src="./images/rwd-logo.png" alt="Web Cafe">
          </a>
        </h1>
        <ul class="memberOnly resetList">
          <li><a href="/">로그인</a></li>
          <li><span class="divider" aria-hidden="true">ㅣ</span><a href="/">회원가입</a></li>
          <li><span class="divider" aria-hidden="true">ㅣ</span><a href="/">커뮤니티</a></li>
        </ul>
        <h2 class="a11yHidden">검색</h2>
        <form action="https://formspree.io/xyyzgpvy" method="POST" class="searchForm">
          <fieldset class="resetBox">
            <legend>검색</legend>
            <input type="search" required placeholder="검색어를 입력하세요." name="search" aria-label="검색어">
            <button type="submit" class="button buttonSearch">검색</button>
          </fieldset>
        </form>
      </header>
      <nav class="appNavigation">네비게이션</nav>
      <main class="appMain">메인 콘텐츠</main>
      <footer class="appFooter">푸터</footer>
    </div>
  </body>
  ```

  

- ```css
  초반에 헷갈리지 않기위해 
  공통부분은 common.css
  데스크탑 부분은 large.css
  모바일 부분은 small.css로 묶어서 따로 작업해줬다
  
  
  /* 공통 레이아웃 */
  .container{
    display:  flex;
    flex-flow: wrap;
  }
  .appFooter{
    width: 100%;
  }
  /* 공통 헤더 */
  .appHeader{
    display: grid;
   -- 헤더영역을 그리드로 설정해주고 brand, memberOnly, buttonSearch 부분을 그리드아이템으로 묶어준다 
  }
  /* 공통 멤버 링크 */
  .memberOnly{
    display: flex;
    flex-flow: row nowrap;
    justify-content: flex-end;
  }
  --- grid로 묶게되면 그안에 아이템들을 배치하기위해서 grid-template로 1행 3열을만들어 주고 속성으로 배치를 해줘야하는데 Display=flex를 주게되면 바로 가로배치가 가능하기때문에 flex 사용
  보통 작업을 할 때는 grid나 flex를 그렇게 많이 섞어서 사용하지않는다고 한다(유지보수관점에서 효율이 떨어짐)
  
  /* 모바일 레이아웃 */
  .appHeader, 
  .appMain {
    width: 100%;
  }
  /* 모바일 헤더 */
  .appHeader{
    width: 100vw;
    background-color: #38302e;
    grid-template: auto / 1fr;
    
    --그리드 아이템을 수직으로는 auto값을 줘서 컨텐츠가 늘어나면 grid박스를 늘어나게하고 박스의 높이는 컨텐츠 크기만큼을 가진다, 수평으로는 1fr을 줘서 1:1의 비율을 가지는데 애초에 100vw가 선언되어있으니까 큰 의미는 없다
  
    align-items: center;
  }
  
  .brand, .memberOnly, .searchForm{
    padding: 10px 20px;
  }
  
  /* 모바일 브랜드 */
  .brand *{
    display: block;
  }
  
  /* 모바일 멤버 링크 */
  .memberOnly{
    order: -1;
    background-color: #988574;
    color: #fff;}
  
  /* 모바일 검색폼 */
  
  input[type="search"]{
    border: 1px solid #aaa;
    border-radius: 5px;
    padding: 2px 5px;
    height: 35px;
    width: calc(100% - 45px);   
    
  --input과 button은 Inline-block이기때문에 서로 옆으로 배치되는데 이때 버튼이 인풋에 밀려서 줄바꿈이 되지 않게 하기위해 calc함수로 전체 100%에서 버튼의 Width 값인 35px와 좀더 여유공간을 주기위해 10px을 더 빼준다, 그렇게 하면 그영역을 뺀 나머지 영역에 input창이 배치된다
    margin-right: 5px;
  }
  
  .buttonSearch{
    width: 35px;
    height: 35px;
    border: 0;
    padding: 0;
  }
  ```

```css

/* 플랙스 */    --위에 grid와 flex가 섞인 요소를 flex만 사용해서 배치해줬다 

/* 공통 레이아웃 */
.container{
  display:  flex;
  flex-flow: row wrap;
}
.appFooter{
  width: 100%;
}
/* 공통 헤더 */
.appHeader{
  display:flex;
 -- 헤더영역을 그리드로 설정해주고 brand, memberOnly, buttonSearch 부분을 그리드아이템으로 묶어준다 
}
/* 공통 멤버 링크 */
.memberOnly{
  display: flex;
  flex-flow: row nowrap;
  justify-content: flex-end;
}

/* 모바일 레이아웃 */
.appHeader, 
.appMain {
  width: 100%;
}
/* 모바일 헤더 */
.appHeader{
  width: 100vw;
  background-color: #38302e;
  display: flex;
  flex-flow: row wrap;
}
.brand, .memberOnly, .searchForm{
  width: 100%;
}
.memberOnly{
  display: flex;
  flex-flow: row wrap;
  justify-content: flex-end;
  order: -1;
}
.resetBox input{
  height: 35px;
  border: 1px solid #aaa;
  border-radius: 5px;
  width: calc(100% - 45px);
  padding: 2px 5px;
  margin-right: 5px;
}
.buttonSearch{
  width: 35px;
  height: 35px;
  border: 0;
  padding: 0;
}
```

