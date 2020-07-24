### Labelledby와 label

```css
         <h2 class="favorite-heading" (레이블을 지정하는 주체)id="favoriteHeading">인기<span>사이트</span></h2>
<a href="" class="favorite-more icon-plus"(레이블을 지정하는 주체를 선택)aria-labelledby="favoriteHeading">더보기</a>
---->> 이 a태가의 주소가 h2에 입력된 인기사이트랑 연결된 정보라는걸 명시 

            <button type="button" class="btn-prev" aria-label="이전 이벤트 보기"></button>
---->> 	이 버튼이 이전이벤트보기에 대한 버튼이라는걸 명시, 버튼의 텍스트 컨텐츠가 있을경우에는 무시하고 aria - label이 적용된다 

```

- label 요소는 자신이 레이블을 지정하는 대상을 참조한다 
  - 위의 경우 이전 이벤트 보기같이 입력되어있는 값만을 참조한다
- labelledby 요소는 레이블을 지정하는 대상이 레이블을 지정하는 주체를 참조합니다.
  - id 값에 명시된 대상을 참조

## Css splite img 

-- >> 성능 관점 이점이 있어서 사용한다 .

-  웹사이트의 여러 이미지를 한장으로 압축해서 background position으로 배치만 해준다 텍스트는 히든처리 
- 이미지를 개별로 처리하는것보다 한장만 랜더링 하는것이 훨씬 효율적이기 때문에 사용한다.
- 여러가지 이미지를 배치하는 방식 
  - padding 트릭
  - text-indent 트릭
  - position 트릭



## 우선순위

```css
.btn-wrap button{
  background: #ccc url(./images/back_forward.png) no-repeat;
  border: 0;
  height: 100%;
  width: 19px;
  overflow: hidden;
  padding: 18px 0 0 0;
  cursor: pointer;
}
.btn-next{
  background-position:-35px 0;
}
```

- background 기본 속성에 position의 기본값이 0, 0 으로 명시되어있기때문에 우선순위의 점수가 낮은 상태로는 .btn-next의 position이 안먹는다
- 이럴경우 선택자의 점수를 좀 더 높게 주거나 위의 button의 선택자를 더 낮게 바꿔서 덮어씌워줘야 한다 



## Transition

- 트렌지션은 애니메이션보다 덜 복잡한 형태로 css만으로 애니메이션 효과를 준다 

- 마우스를 올려놓거나 클릭할때 발생하는 이벤트로 주로 사용한다 .

  - ```css
    .related-list{
      margin: 0;
      height: 27px;
      transition: all 200ms;
    }
    .related-list:hover{
      height: 147px;
      padding: 10px;
    }
    ```

  - 위 예제 처럼 처음 높이가 27px 인 상태에서 transition을 줘서 마우스를 hover 했을 시 높이를 147px로 바꿔서 컨텐츠가 늘어나도록 해줬다 

  - 단축속성 transition : (property , duration(시간), << 필수속성  ㅣㅣ   

  - timing-function(시간함수를 이용한 가속도처리), delay(시작지점을 지연시키는 속성 )



## counter reset 속성

- 카운터를 사용하려면 먼저 counter reset 속성의 카운터 이름과 시작값을 설정해야한다 . 

- ```css
  .favorite-list li{
    counter-increment: number;
  }
  .favorite-list li::before{
    content: counter(number); 
  }
  ```



### overflow hidden 사용할 때 주의할점

- Overflow hidden의 경우 그 박스의 크기를 넘어 설 때 hidden 처리를 하기때문에
- 원하는 사이즈의 박스 크기를 지정해 줘야한다.