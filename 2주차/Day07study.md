## 	IMG 태그와 SVG 태그의 다른점 (IMG form)

- svg는 백터 이미지로 사이즈를 바꿔도 이미지가 깨지지 않으면서 작은 용량을 유지

- font 형식의 아이콘을 사용할 때 필요한 아이콘만 받으면 되기때문에 트래픽의 장점이 생긴다 

- jpg 확장자는 는 svg확장자 보다 상대적으로 용량이 크고 반응형 같은 경우 사이즈 별로 이미지를 따로따로

  준비해야되기때문에 보통 svg 를 많이 사용한다 

- 고해상도 사진의 경우 svg로 코드화를 시키는게 어려울 수 있고 또 그냥 그 이미지 자체를 사용는경우가 많다 

## Input 태그

- action : 양식 데이터를 처리할 프로그램의 URI(Uniform Resource Identifier)  ㅡㅡ> 서버의 주소
  - input type "button"  ==> 요즘엔 이런형식보단 html의 button 태그로 많이 사용된다 value값을 할당해 주지 않으면 빈버튼이된다
    - 버튼이 뭐라도 하게하려면 javascript가 필요하다 
  - Input type "submit" ==> 엑션으로 보낸다  
  - Input type "image" ==> 버튼의 이미지가 씌워진다 
- mathod : 양식을 제출할 때 사용할 HTTP 메소드 --post, get 차이 더 찾기 
  - Post: 양식데이터를 요청 본문으로 전송  
  - get :  action URL과 ? 구분자 뒤에 이어 붙여서 전송합니다 . 
    - post와 get의 디테일한 차이 (https://im-developer.tistory.com/166) 
    - 아직은 이해가안되는 내용, post가 get보다 안전하다 
  - dialog : 양식이 Dialog 안에 위치한 경우, 제출과 함께 대화상자를 닫는다 
- input태그의 placeholder (label 값과는 다르게 힌트를 주도록 하자) / 논리속성 required를 주면 true  xml 은 지원 하지 않음 

예제

```html
<!-- Form which will send a GET request to the current URL -->
<form>
  <label>Name:
    <input name="submitted-name" autocomplete="name">
  </label>
  <button>Save</button>
</form>

<!-- Form which will send a POST request to the current URL -->
<form method="post">
  <label>Name:
    <input name="submitted-name" autocomplete="name">
  </label>
  <button>Save</button>
</form>

<!-- Form with fieldset, legend, and label -->
<form method="post">
  <fieldset>
    <legend>Title</legend>
    <label><input type="radio" name="radio"> Select me</label>
  </fieldset>
</form>
```

​																								결과 값 

<img width="668" alt="스크린샷 2020-07-20 오후 7 52 35" src="https://user-images.githubusercontent.com/68043654/87930240-ac376880-cac2-11ea-825f-223c89965fae.png">



## 아래 예제의 마크업 순서

<img width="288" alt="스크린샷 2020-07-20 오후 7 57 40" src="https://user-images.githubusercontent.com/68043654/87930630-6202b700-cac3-11ea-9ebe-1cce5a6b8781.png">

- ### 선형화 (하드코딩 하지말고 손으로 그려가면서 해볼것)

  - 로그인
  - 아이디
  - 인풋텍스트
  - 비밀번호
  - 인풋텍스트 비밀번호
  - 로그인 버튼
  - 링크목록 이냐 버튼이냐 판단 

- ### 시멘틱 마크업

  - section이나 article로 나눌 경우 heading 을 가진다 로그인을h2태그로, 텍스트로 , img로 하지않는다 (login)
  - form  , get  (login-form)
  - feildset ㅡ> div 같은거 , 연관성있는 서식, 컨트롤을 묶어야 한다는 차이가 있다 
    - legend 회원로그인 폼  ㅡㅡ> fildest가 뭘묶었는지에대한 이름 xhtml에는 꼭있어야되지만 hmlt5에는 없어도된다 가능하다면 준다 
  - label 명시적인 레이블링 필요. input에 #아이디선택자 userEmail를 label에 [for "아이디이름"] 선언 내부적인 로직의 연결고리 생각하기
  - Div 2개 만들어서 내부에 label 인풋\
  - 로그인 버튼 button type "submit " 
  - 링크는 ul에 li > a 태그 

![이름 없는 노트북-2](https://user-images.githubusercontent.com/68043654/87938943-3fc46580-cad2-11ea-9ae8-b0c3f1a3de1f.jpg)

```html
<div class="user-email">
                <lable for="userEmail">아이디</lable> label for에 input id 값 써주면 기계적인 연결이된다
                <input type="email" id="userEmail">  -->구형 브라우저는 email값을 text로 인식
              </div>

 <div class="user-email">
                <label for="userPw">비밀번호</label>
                <input type="password" id="userPw">
              </div>
```

### 마크업, CSS

- 고민해서 짠 마크업을 효과를 주기위해서 바꾸다가는 레이아웃이  틀어질 수 있다
- 마크업 시 재사용 안하는 태그는 쪼개지 않도록 잘 설계한다 
- CSS를 줄때는 어떤게 더 효율적일지 생각하고 코딩하기 

### A Tag와 접근성

a태그를 쓸때는 내부여백을 키워서 선택할수있는영역을 늘린다 (사용자 접근성 용의)

## 아이콘 삽입 시 CSS 속성

```css
.member-only a::before{
  content: '\e803'; --필수
  font-family: 'fontello';  --필수 
  
  @import나 head영역에 cdn link연결 필수 
```



#### 내일 질문할 내용

1. 왜 btn-login에 paddig 값을 5px 줬을까
