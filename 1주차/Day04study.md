#### 새로 알게된 태그

- fieldset = 그룹으로 묶어줄때 사용하고 legend 요소로 설명할 수 있다.

- label = for 속성에 연결할 id 값을 입력해 줘야한다 

- Input 태그

  - placeholder = 사용자가 무엇을 입력해야 하는지 알려주는 보조도구 
  - Placeholder 에는 유효성검사를위해 required태그가 필요하다 

- text-transform: uppercase; = 상속된 내용 모두대문자로 변경 

  Font-variant : small- caps = 폰트가 작은 대문자로 바꾸는속성

   

#### 어제내용 복습 

padding과 margin의 차이 : padding 은내장지방 margin 내영역에 접근금지

## Box-sizing:border-box (auto값:content-box)

### content-box

<img width="665" alt="스크린샷 2020-07-16 오후 8 41 15" src="https://user-images.githubusercontent.com/68043654/87667157-d3c9c080-c7a4-11ea-83f0-64af83e00c01.png">

- 태그에 box-sizing 값을 할당해주지 않으면 auto 값은 content 박스가된다
- Content-box는  margin, padding,border 등 모든 값을 포함한다
- 위의 박스처럼 width,height 값을 100px을 지정해줬을때 border:2px의 값이 추가되니까 박스모델의 전체사이즈가 104px로 증가했다

### border-box

<img width="665" alt="스크린샷 2020-07-16 오후 8 44 37" src="https://user-images.githubusercontent.com/68043654/87667434-4b97eb00-c7a5-11ea-9818-30dcd28a9b2b.png">

- Border-box는 padding,border 어떤값을 줘도 100px에서 커지지 않고 영역을 지킨다 

  ### ㅡㅡㅡ >> content, border - box 둘다 margin은 바깥영역이니까 박스내부에는 영향 x 



#### 마크업시 고려해야 할 점 

- btn 같은 태그는 html이 랜더링하는 순서를 생각해서 배치를 해야 정보를 읽고 나서 submit이 어느정보를 읽고난다음에 버튼을 눌러서 submit 이되야하는지 

- a 태그에서 Lole = " button " 속성을 이용해서 버튼역할도 가능하다 .

- a 태그로 버튼 태그를 선택한 경우 클릭하기 편하도록 사이즈를 키워준다 (사용자 접근성)

- Overflow:hidden속성과 그 외 숨김요소 사용 방법 

  1. Text-decoration:none; 이나 Top:-9999px 를 주면 안되는 이유는 = 보이스오버 기능을 사용할때 문서를 읽어들이다가 top좌표로 스크롤이 올라가버리기 때문에

  2. m: -1px; / clip-path : 함수 polygon (0 0, 00, 00 ) 함수를 이용해 마스크 처리해서 화면에서 감춘다 clip path maker search

#### 이미지넣을때 고려할 내용

- Accessibility = a11y (접근성) -alt 를 부여한다 

- seo -alt를 부여

- 해상도



### Display : inline block 

- html 을 작성할때 가독성을 위해 엔터키를 누른것이 랜더링 시 인라인블럭 에서는 공백으로 해석이되기 때문에
- 요소들이 의도치 않게 떨어질 수 있다 



#### Float 속성에 영향을 받는 하위요소에 position 값을 줘서 배치를 시킬 때

````html
<ul class="menu clearfix">
          <li class="menu-item menu-act">
            <button type="button" class="btn-menu">HTML에 대해</button>
            <ul class="sub-menu sub-menu1">
              <li><a href="#">HTML 5소개</a></li>
              <li><a href="#">레퍼런스 소개</a></li>
              <li><a href="#">활용 예제</a></li>
            </ul>
          </li>
````

위의 코드와 같은 구성으로 menu clearfix 에 6가지 요소가 있고 

<img width="876" alt="스크린샷 2020-07-16 오후 7 32 33" src="https://user-images.githubusercontent.com/68043654/87664315-ff967780-c79f-11ea-924c-b05652b3a7ad.png">

```css
.menu-item{
  float: left;
}
```

menu-item에 float : left 속성 값을 줬을때  menu-item 의 자식 요소인 list들이 float:left 속성이 같이 먹어서 list들의 가로너비를 인식해서 이런식으로 인식해서 menu-item들의 정렬이 이루어 지지 않고 오른쪽으로 밀려 최대 width 값을 벗어나 아래로 내려오는 현상이 생겼는데 이때

```CSS
.sub-menu{
  position: absolute;
}
```

이런식으로 하위 요소에 absolute값을 부여해 주면 상위요소인 menu-item에 주는 영향이 사라지면서 아래그림 처럼

<img width="920" alt="스크린샷 2020-07-16 오후 7 50 25" src="https://user-images.githubusercontent.com/68043654/87664356-0e7d2a00-c7a0-11ea-9e78-19a00f3ffa16.png">

정상적인 float : left 지정이 된다 그 후에는 absolute의 속성인 절대위치를 지정하는 left나 top 등 아무런 값이 지정되지 않았기때문에 

그 자리에 그냥 남는다 . 



### Inline / Inline-block / box요소의 특성 

### (출처:https://github.com/kym123123/TIL/blob/master/2ndweek/2020-07-16.md)

#### 1. inline

:inline 요소는 위 아래 길이값(height,width)을 지정 해줄 수 없다. (지정해도 무시된다.) 또한, 위 아래로 패딩이나 마진 값을 지정해줘서 상자크기를 커보이게 만들 수는 있다. 그러나 inline요소 내부에 텍스트나 콘텐츠가 존재하는 영역이외에는 실제 inline영역의 값으로 인정받지 못하는 현상이 생긴다.

ex> 콘텐츠가 있는 부분 이외의 영역에는 다른 요소들과 겹쳐진다. 시각적으로만 영역이 커져보이지 사실은 영역이 커진것처럼 배치되지 못한다. 단 a태그로 링크를 설정해주고 padding과 margin을 설정해서 상자의 영역을 늘여놓은 영역은 클릭하면 링크로 연결되는 기능이 유효하다.

------

#### 2. Inline-block

:inline요소의 배치특성을 가지면서 영역특성은 block특성을 갖는다. 따라서 배치는 ㅁㅁㅁㅁ 처럼 옆으로 나란히 위치되면서 height,width를 지정 해줄 수 있다.

- inline-block으로 생기는 문제점: li태그를 inline-block으로 지정해주면, li태그간에 공백문자가 생겨서 원치 않는 공백이 발생하게 된다. 원래 li는 수직으로 배열되는 block요소 였기 때문에 수직으로 콘텐츠를 내려주던 줄바꿈 문자가 수평으로 변하면서 공백으로 처리되는 것이다. 또한 이 공백문자가 li와 함께 ul태그의 자식요소로 인식되면서 실제로 index도 공백문자의 수만큼 늘어나는 문제가 있다. css로 공백현상을 해결해 주기 위해서는 li의 부모요소ul의 font-size를 0으로 설정해준다. 이렇게 설정해주면 공백을 해결 할 수 있지만. ul의 font-size가 li에도 상속되면서 리스트의 내용도 보이지 않기 때문에 추가로 li태그에도 원하는 크기의 font-size를 지정해 주면 된다.

  `아래 그림으로 특성 이해하기`

  [![inline-block](https://user-images.githubusercontent.com/51959017/87670731-302fde80-c7ab-11ea-97d3-324001aba163.png)](https://user-images.githubusercontent.com/51959017/87670731-302fde80-c7ab-11ea-97d3-324001aba163.png)

------

#### 3. box요소의 특성

: content-box(기본value), border-box(*button태그의 기본value!*)

- margin은 auto와 음수값을 가질 수 있다. padding은 불가능 ->negative margin을 이용한 레이아웃을 과거에 많이 사용 했었다.
- float는 속성(property), flex는 display property의 value이다.


