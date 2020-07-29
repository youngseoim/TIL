

#### Background-img에 text없애는 방법 

1. padding -left 
   1. 이방법은 padding 속성으로 왼쪽에 여백을줘서 텍스트를 박스밖으로 밀어내는 방법이다
   2. Over-flow:hidden속성을 이용해서 밀려난 텍스트를 숨김처리 할 수 있다.
   3. 영역을 차지하는 방식이기때문에 부모요소에 height값을 고정해주는 추가적인 작업이 필요할 수 있다 .
   
2. 내가선택한 방식은 text-indent  >> 얘를 쓸 수 있는 박스모델
   1. block
   2. inline-block
   3. Table-cell
   4. inline.   --나머지는 block 박스모델인데 inline박스는 text-indent속성을 사용할 수 없다 
   5. Table.  

   
   
3. position트릭 

   1. 숨기려는 요소에 가상요소 선택자로 background-img를 넣어주고 width,height값을 100%로 준후에 absolute처리해서 텍스트를 가려준다  
   2. button::after (before보단 after인이유는 둘다 레이어가 됐을때 before는 뒤로깔려서 한번더 위로 올려줘야하기때문에 after를 사용한다)

### background-size : contain, cover의 차이

- Contain - 이미지가 잘리거나 찌그러지지 않는 한도 내에서 제일 크게 설정.
- Cover  - 이미지가 찌그러지지 않는 한도 내에서 제일 크게 설정. 이미지의 가로세로비가 요소와 다르다면 이미지를 세로 또는 가로방향으로 잘라내어 빈 공간이 생기지 않도록 설정합니다.
- Auto - 배경 이미지의 원본 크기를 유지.

### Display:contents

- 부모로부터 자식으로 인식되지 않는다 .
- 하지만 자신의 자식은 유지한다 .
- 부모의 호적에서 파여서 자기가 낳은 자식이랑만 지낸다 

### Grid

- Grid - template - row, column

  - 속성값

    - Track-size (그리드에서 사용 사능한 공간의 길이) / line-name ( 사용자가 설정한 임의의 선 이름)

    - ```css
      .grid-container {
        grid-template-rows: 25% 100px auto;
        grid-template-columns: 40px 50px auto 50px 40px;
      }
      ```

    - <img width="760" alt="스크린샷 2020-07-29 오후 8 56 27" src="https://user-images.githubusercontent.com/68043654/88797592-860a7a80-d1de-11ea-9fe8-bf7a6fa75a5d.png">

    - ```css
      .grid-container {
        grid-template-rows: [row-1] 100px [rows-1-end row-2-start] 30% [row-2-end];
      }
      ```

      - 위와 같이 [ ] 괄호안에 이름으로 명시해줘도 되고 띄어쓰기로 구분한다 

    - 설정이 반복되는 경우에는 repeat 함수를 사용한다 

      - ```css
        .grid-container {
          grid-template-rows: repeat(3, 80px [row-start]) 5%;
          /* 결과: 80px [row-start] 80px [row-start] 80px [row-start] 5% */
          grid-template-columns: repeat(2, 15% 30px) auto;
          /* 결과: 15% 30px 15% 30px auto */
        }
        ```

      - 

- Grid -template- areas 

  - grid item에게 grid-area 속성으로 이름일 지어준다
    - Grid-area: 영서;
  - Grid-template-areas: "영서 영서 영서 " ; 따옴표 안에 이름으로 배치해주고 띄어쓰기로 구분한다
  - column,row 의 개수만큼 이름을 적어줘야 한다 12column이면 이름을 12번 적어야 적용된다
  - 위치를 바꾸거나 할 때 편리하지만 열이나행이 많아지면 일일히 다 써줘야하는 불편함이있다





### 모바일 화면 네비게이션 메뉴

<img width="171" alt="스크린샷 2020-07-29 오후 9 36 24" src="https://user-images.githubusercontent.com/68043654/88800869-c8828600-d1e3-11ea-992a-938d6b498122.png">

- 왼쪽의 메뉴를 오른쪽의 메뉴처럼 애니메이션 효과
  - 전체 position: absolute를 지정해준 상태

```css
.positionTop{
  top: 0; 			  버거바의 제일상단에 위치시키기 위해 top:0 
}
.positionMiddle{
  top: 50%; 				
  버거바의 중간에 위치시켜야하나는데 top:50%만 주면 50%부터 시작하는거라 중간에서 아래로 좀 밀려가기 떄문에 
  transform: translateY(-50%); - - - tranlate Y축을 -50%로 지정해준다
}
.positionBottom{
  top:100%;
  transform: translateY(-100%);    middle과 똑같이 배치 
}
--- > transition 효과 주기 전


.isAct .positionTop{
  top: 50%;   
  transform: translateY(-50%) rotate(45deg);
}
.isAct .positionMiddle{
  transform: translateX(-100%) translateY(-50%);
}
.isAct .positionBottom{
  top:50%;
  transform: translateY(-50%) rotate(-45deg);
}
--> 애니메이션 효과를 주기위해 중간 버거바는 x좌표 -100%를 줘서 바깥으로 내보낸 후에 over-flow:hidden처리
--> top, bottom은 top , translate Y좌표를 50%로 줘서 중간에서 시작해서 rotate를 45,-45deg를 줘서 x자 처럼 만들어줬다

--- > transition 효과 주고 난 후
```