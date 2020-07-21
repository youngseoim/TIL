```css
.login-form div{
  margin-bottom : 5px 
  width :150px ---> widht 값이 왜 필요한가요 ?
}
```

--> 어제 예제중 button tag에 position이 아닌 float를 사용할경우 label과 input 요소의 width값을 지정해줘서 오른쪽에 버튼이 들어갈 공간을 만들어 주기 위해서 필요하다, 예제를 보여줄때 써놨던 width값을 지우지 않아서 생긴 착각!

```css
.login-button{
  background-color: #db5629;
  float:right;
  position: absolute;  --- 배치를 position으로 할 경우 
  top: 0px;
  right: 0px;
  width: 50px;
  height: 52px;
  border-radius: 3px;
  border: 0;
  color: #fff;
  cursor: pointer;
  font-size: 1.3rem;
}
```



## html / css 목록을 만드는 <dl><dt><dd> 태그

<dl> 
  <dt>정의되는 용어의 제목</dt>
  <dd>용어 설명</dd>
</dl>

- dl 태그는 definition liost (정의 목록)의 약자, 용어를 설명하는 목록을 만들때 사용
- dt 태그는 definition term (정의 용어)의 약자, 정의되는 용어의 제목을 넣을때 사용
- dd 태그는 definition description (정의 설명)의 약자, 용어를 설명하는데 사용

- html5.2 ver 부터 dl 안에 div태그는 허용 ,단 div 안에 dt,dd 둘다 포함되야 한다 

```html
<dl>
  <div>
    <dt></dt>
    <dd></dd>    == 허용되는 형태
  </div>
</dl>
```

```html
<dl>
  <div>
    <dt></dt>
  </div>
  <div>                == 허용하지 않는 형태
    <dd></dd>
  </div>
</dl>
```





버튼에 패딩을 준이유는 안에 텍스트가 박스에 꽉차지 않도록 배치하기 위해서

- 지금 당장 눈으로 보기에는 패딩값이 있나 없나 변화가 없겠지만 
- 텍스트가 1글자이상 늘어나게됐을때 패딩값이 있다면 박스에 꽉차지 않는다 



### validation 영역

- 첫 시작 태그를 section이아닌 h2를 줌으로써 기계적인 아웃라인을 알린다
  -  문서의 윤곽을 자동으로 생성하는 작업은 매우 중요하며, 특히나 보청기 같은 보조 기술에선 더욱 그러한데, 이를 이용해서 파악된 문서의 구조를 바탕으로 사용자에게 정보를 전달해 주게 된다는 것을 고려하면 그 중요성은 더욱 명확해집니다. 

### A태그 내부 

- href="" 이외 추가하면 좋은 속성들
- target 
  -  _self ;  기본값으로 현재페이지를 이동시킴 
  - _black ; 새로운 창을 띄워서 브라우저를 띄움
  - _parent ; 
  - _top
- target을 사용할 때,rel="noreferrer"를 추가해 window.opener의 악의 적인 사용할 방지하는걸 고려해야한다 (설명을 봐도 아직은 이해가 안되는부분 )
  - window.opener란 윈도우 a에서 window.opener를 통해서 윈도우b를 열었다면  window.opner를 통해 윈도우 B에서 윈도우 A를 제어할 수 있다. 라고 써있는걸로 봐서 해킹관련 이슈가 있는것같다 .

- Title = "새소식" 넣어주면 >>링크에 커서를 올려놓을시 "새소식 더 보기 링크" 라는 설명이 추가된다
  - title 태그를 추가해주게되면 보이스오버같은 보조장치가 접근할때 이 링크가 어떤링크인지 설명이 된다.

### width: calc (100% - 5px);

- 부모요소의 width값 100%에서 -5px 만큼을 계산해준다
- 100%,5px 은 -와 한칸씩 공백을 넣어줘야 한다 

### img 밑에 배경이 삐져나오는 현상 해결법

-<img width="398" alt="스크린샷 2020-07-21 오후 8 02 34" src="https://user-images.githubusercontent.com/68043654/88047853-3cda7b00-cb8d-11ea-9e9b-96945e27d970.png">

- 이렇게 될 경우 img가 들어있는 태그에 display:block 이미지태그에 display:block을 주면안되는경우
- vertical align:값을 주면 해결된다
- 이미지는 텍스트취급, line-height속성때문에 텍스트의 바텀라인이 삐져나오면서 배경이 넘치게 보인다 .

### Flex로 배치할 때

- flex로 배치할 경우 수직정렬 align item 쓰고 align item은 수직이 stretch 니까 line height 로 조절



#### 자잘자잘

- visibility hidden 영역은존재하지만 비주얼상 안보인다 

- float 를 할떈 width,height 값을 명확하게 계산할것

- 바깥레이 아웃은 오토마진 을 많이쓰고, 안에 레이아웃엔 플렉스를 쓰면 편하다



#### 주말에 해볼거

- form ,button 태그같은거 css 재사용 하게끔 작성해보고

- position , float , flex 등 여러가지 예제로 몇개 만들어보기

- 버튼,폼 예제 찾아보기 

