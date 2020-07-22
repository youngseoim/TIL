### 폼서식

1대 1 대응 레이블 

-  label 과 input 의 1:1 대응

- 비주얼 상 label값이 없다고해서 label을 주지 않으면 접근성 관점에서 input이 뭐에 관한 input인지

  전달해주기 위해 label값을 줘야한다 

  -  Label을 안보이게해주기 위해서  accessibility hidden을 사용할것 (컨텐츠가 안보여도 tab키 이동가능)
  - Display:none; (컨텐츠도안보이고 tab 키이동 불가, 기계적으로 사라짐  )

- placeholder는 input창에 뭘 넣어야 하는지 하는 힌트이다 

- label두개가 사용가능하지만 보조기기는 접근하지 못한다 

회원가입form  

- 필드셋은 여러개 쓸수있다 (연관있는 정보를 묶어서)
  - 필수와,선택 정보를 나눠서 필드셋으로 나눠줄수 있다.
    - 아이디,비밀번호(필수)  , 성별(선택)  선택요소는 안적어도 회원가입이 진행되도록 



### 선택자

```html
.search-form input[type="search"]{   ----type 선택자
}
```



### button, a tag

- button태그는 태그내부에  다른요소를 포함할 수 없다
- a 태그는 다른요소를 포함할 수 있다
- 둘다 키보드 포커스를 받을 수 있다 

### Time tag

time 태그 필수속성 datetime 2020-07-22t 

- time 태그를 안쓰고 나중에 날짜를 연산하려면 번거롭기때문에 time쓰면좋다 



GitHub.com/niawa 

http://www.wah.or.kr/  자료실 -> 연구자료실 



### 수업 예제 마크업 (미완성)

![수업예제 자료검색 Form-2](https://user-images.githubusercontent.com/68043654/88178675-b5146f80-cc65-11ea-9d5b-de8fad932f02.jpg)



![이름 없는 노트북 (2)-2](https://user-images.githubusercontent.com/68043654/88178671-b2b21580-cc65-11ea-8f93-35510bc60a91.jpg)

 ### 주말에 해볼 로그인 폼 마크업  (미완성)

![Login Form 2](https://user-images.githubusercontent.com/68043654/88178657-b04fbb80-cc65-11ea-92d6-c11015e028d4.jpg)