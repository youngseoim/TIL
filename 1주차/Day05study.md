### Float과 Negative margin기법 

음수 마진은 문서 내의 정상적인 흐름(document flow) 를 건들이지 않는다 

다시말해, 요소를 이동하기 위해 음수 마진을 사용하면, 그 뒤에 오는 모든 요소들도 같이 이동하게 된다

Float 이 적용되면 다르게 동작하므로 음수 마진을 사용할 경우에 좀 더 주의를 기울여야 합니다.



### 부모요소에 width 값이 지정되어있는 기본적인 상태 

<img width="443" alt="스크린샷 2020-07-17 오전 10 27 10" src="https://user-images.githubusercontent.com/68043654/87738396-3c9e5080-c818-11ea-9735-5a3483c9e194.png">

위 그림과 같이 A,B,C 가 있을때  B에 레프트마진값을 음수로 주면 A쪽으로 가서 겹쳐진다 B가 올라오고 A가 가려진 이유는 html구조가 뒤로 올수록 올라오기 때문이다 그리고 그상태에서 B에 음수 margin-right값을 추가로 주게되면  다음그림과 같이

<img width="443" alt="스크린샷 2020-07-17 오전 10 29 55" src="https://user-images.githubusercontent.com/68043654/87738521-8edf7180-c818-11ea-941b-c6551373b1cf.png">

 A,B는 멈춰있는 상태에서 C 를 B쪽으로 끌어오는 것처럼 보이게 브라우저를 속이는 것이 음수 마진의 특성이다 

이때 margin - bottom값도 음수로 줄경우 이미지상은 아무 변화 없어지지만 margin-right 를 끌어들이는 속성처럼 

구조상으로는 밑에있는 요소를 끌어오는 것처럼 적용된다 . 

- 음수 마진 값을 준 박스를 기준으로 생각해야 된다 float값을 right로 줬을땐 그 반대로 작동하기 때문에 기준이 가는지, 기준쪽으로 끌어당기는지

---> https://github.com/youngseoim/Code-example 코드로 확인하기 (파일명 : negative.html)



어제꺼 수업 복습

### Postition -Normal Flow 일반 흐름 , 마크업한 순서대로 흘러간다 / Position는 Normal Flow 를 벗어나게한다

- absolute는 주변배치에 영향을 준다,  top,left,right,bottom 값이 있으면 offset parents 값 을 찾아간다  지정된 값이 없으면 컨텐츠 		

  크기에 맞게 줄어들어서 배치된다 

### Float

- Float 을 사용하면 어떤값을 가지던 block 박스가된다  >>인라인 요소가 아니기 때문에  width , height 값을 가질 수 있게된다 

### Button

<img width="962" alt="스크린샷 2020-07-17 오후 7 32 21" src="https://user-images.githubusercontent.com/68043654/87777387-582f4880-c864-11ea-842b-e5c369f24f0c.png">

위와 같은 배치를 하기위한 마크업구조는 다음과 같다

```html
<li class="menu-item menu-act">
            <button type="button" class="btn-menu">HTML에 대해</button>
            <ul class="sub-menu sub-menu1">
              <li><a href="#">HTML 5소개</a></li>
              <li><a href="#">레퍼런스 소개</a></li>
              <li><a href="#">활용 예제</a></li>
            </ul>
          </li>
```

여기에 css 속성을 아래와 같이 준다 

```css
.btn-menu{
  background-color: transparent;	-- 부모의 컬러를 상속 받는다 
  color: #fff;
  font-size: 1.6rem;
  font-weight: 700;
  border:0;- semantic button태그의 기본속성으로 들어있는 border 값을 없애준다 안쪽의 흰색 border만 설정하기 위해
  cursor: pointer;
  border-left: 2px solid rgba(255,255,255,.5);
  text-shadow:   ---- 윤곽이 드러나게 text-shadow 효과를 준다 
  1px 0 0 #000,
  0 1px 0 #000,
  -1px 0 0 #000,
  0 -1px 0 #000;
  line-height: 48px;  -- 아래 가상 선택자 after가 line-heigh속성으로 메인메뉴의 크기랑 일치시켜서 마치 밑줄인것 같은 효과를 준다
  padding: 0 20px;
}
.menu-act .btn-menu{    -- 노란색 속성을 부여해놓고 나중에 마우스 클릭했을때만 효과가 나오도록 조정해준다 
  color: #ff0;
}
.menu-act .btn-menu::after{  --- after 요소로 block 박스를 생성해주고 2px #000의 효과로 메인메뉴에 밑줄영역을 생성해준다 
  content: "";
  display: block;
  background-color: #000;
  height: 2px;
}
```

- 혹시 btn 메뉴에 :hover를 사용하게 될 경우에는 마우스를 사용하지 못하는 유저를 위해 :focus 값도 같이 부여해 준다 (접근성)



## Background

### linear-gradient() 

-  백그라운드 이미지에 그라데이션 효과를 주는 속성 

- Gradient속성은 image의 한 종류로서 image를 사용하는 곳에만 적용할 수 있다.
  - 그렇기 때문에 Linear-gradient()함수는 color속성에는 사용할 수 없다.

### Background - position

- pixel과 %로 원하는 위치만큼 이동시켜 줄 수 있다. 둘간의 차이는 아래와 같다.

  -  (이미지 출처:https://github.com/kym123123/TIL/blob/master/2ndweek/2020-07-17.md)

  [![image](https://user-images.githubusercontent.com/51959017/87777572-b3613b00-c864-11ea-97f6-fa2e06870107.png)](https://user-images.githubusercontent.com/51959017/87777572-b3613b00-c864-11ea-97f6-fa2e06870107.png)

  

  - 레이어 관점과 백그라운드 이미지의 관점 

    - 이미지는 먼저 마크업된 요소가 가장 위로 올라온다
    - 레이어는 먼저 마크업된 요소가 가장 아래로 깔린다

  - 또 background 단축 속성을 사용할 때 주의해야할점은 아래 그림의 #fff color가 앞으로 지정되면 흰배경이 가장 위로 올라오기때문에

    이미지 출력이 안된다 , 그렇기 때문에 색깔은 반드시 나중에 선언해줘야한다 (순서의 중요성)

  [![image](https://user-images.githubusercontent.com/51959017/87777851-34203700-c865-11ea-8d7d-7224c810a071.png)](https://user-images.githubusercontent.com/51959017/87777851-34203700-c865-11ea-8d7d-7224c810a071.png)

## Font

- Font-family : 글꼴 serif or san serif
  - 이때 글꼴의 값은 콤마로 구분하여 작성한 순서대로 구분하여 대체가 될 수 있다
  - 여러개를 쓰는이유 = 브라우저가 해당 폰트를 인식하지 못하는 경우 그다음 인식할 수 있는 폰트를 제공하기 위해서



## Animation

<img width="943" alt="스크린샷 2020-07-17 오후 9 11 07" src="https://user-images.githubusercontent.com/68043654/87784902-21f8c580-c872-11ea-94dc-8e05cb81c525.png">

<img width="943" alt="스크린샷 2020-07-17 오후 9 11 36" src="https://user-images.githubusercontent.com/68043654/87784938-32a93b80-c872-11ea-835a-ae22fe4a01e9.png">

위 그림처럼 Visual 영역의 폰트를 위에서 아래로 위치시키는 애니메이션을 아래에 Css로 효과를줬다

- @Keyframes 규칙은 개발자가 애니메이션 중간중간 특정 지점을 거쳐갈 수 있는 키프레임들을 설정함으로써 애니메이션 과정의 중간 절차를 제어할 수 있다
- 자동으로 브라우저가 애니메이션을 처리하는 것 보다 세밀하게 중간동작을 제어할 수 있는 장점이 있다.
- Animation(단축속성 입력 순서) :
  - name : 키프레임의 이름
  - duration : 완료에 걸리는 시간 (초 또는 밀리초) 지정
  - timing-fuction : 애니메이션의 속도 곡선을 지정
  - Delay : 시작 전 지연 지정
  - Iteration-count : 재생 횟수 지정 
  - direction : 반복 주기에서 역방향 재생 여부 지정
  - Fill-mode : 실행시간 이외의 시간에 애니메이션에 적용되는 값 지정 
  - Play-state : 실행 여부 또는 일시 중지 여부를 지정 
  - Initial : 이속성을 기본값으로 설정 / inherit : 부모 요소에서 이속성을 상속

```css
/* 비쥬얼 영역 에니메이션 */
@keyframes textAni{     --- keyframe의 이름을 textAni로 지정 
  0%{	
    font-size: 12px;					
    color: rgba(0, 0, 0, 0);	 ------ 점점 선명해지는 효과를 주기 위해서 마지막 값을 0으로 지정해줬다
    transform: translate(0,0); ------ 이 속성은 translate 함수를 사용해서 x,y축을 따라 지정된 거리만큼 요소를 이동 시킨다

  }
  100%{
    font-size: 24px;	-- 점점 요소가 커지는 효과를 주기 위해서 시작지점과 폰트 사이즈를 다르게 지정했다		
    color: rgba(0, 0, 0, 1);  -- 점점 선명해지는 효과를 주기 위해서 시작지점의 값은 0,마지막 지점은 1로 지정해줬다(앞에 3개는 컬러)
    transform: translate(400px, 75px); ---시작지점 (0,0) 에서 400px, 75px 값 만큼 이동시키는 효과
  }
}
@keyframes bgAni{
  0%{ opacity: 1;}
  100%{ opacity: 0;}
}

.visual{
  height: 120px;
  position: relative;
}
.visual::before,
.visual::after{    
  animation: bgAni 2000ms ease-in-out infinite alternate; 
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;                     
  height: 100%;
  background-repeat: no-repeat;
}
  --- position값을 absolute로 줌으로써 분리되며 top,left 값이 주어졌으니 offset parents값을 찾아가고 부모요소
visual에 relative가 있으니 그 루트를 기준으로 0,0값인 가장 왼쪽 위로 요소가 붙어서 애니메이션이 시작된다,부모 요소 크기
가 작아지거나 커질때 같이 움직이게 해주기 위해서 width, heigh 값에는 100%를 줬다

.visual::before{
  background-image: url(./images/ani_flower_01.png), url(./images/ani_flower_02.png);
  background-position: 0 -10px, 670px 0;
}
.visual::after{
  background-image: url(./images/ani_flower_03.png), url(./images/ani_flower_04.png);
  background-position: 300px 0, 800px 20px;
  animation-delay: 1000ms;
}
.visual-text{
  font-family: Georgia, 'Times New Roman', Times, serif;
  font-size: 2.4rem;
  width: 500px;
  animation: textAni 500ms ease-in-out forwards; 
}
```



## 트렌지션과 애니메이션의 차이

### 트렌지션

- 요소의 변화를 일정기간 동안 일어나게 한다
- 자동으로 발동되지 않고 hover나 onclick 같은 이벤트 트리거에 의해 작동한다 



### 애니메이션

- 트렌지션보다 할 수 있는 것이 많다
- 트렌지션은 시작하기 위해 이벤트가 필요하지만 애니메이션은 시작,정지, 반복까지 제어가능하다 



## 애니메이션기능과 관련해서

### CPU, GPU 가동성능을 고려해야하는 이유 관련 링크 

- https://www.slideshare.net/wsconf/css-animation-wsconfseoul2017-vol2?qid=e782ae94-ac81-4ce3-bf9a-1e5a4a2d7e57&v=&b=&from_search=3