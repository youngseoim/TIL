### 어제 쪽지시험 오답풀이

이미지 아래에 약 2px 정도의 baseline이 남아 배경색이 표시되는 문제가 있다. 이와 같은 문제를 해결하기 위해 두 가지 방법을 사용하였다 각 방법에 맞는 코드를 입력하시오

- 내가 쓴 오답: display:block / vertical-align: middle,top,bottom,baseline
  - 다른건 다 맞는데 vertical-align의 기본값인 baseline 때문에 배경색이 남는현상이 생기는거라서 baseline은 포함되지 않는다 



### css 순서, 선택자 우선순위

```css
.notice-list, 
.pds-list, 
.notice-more, 
.pds-more{
  display: none;
}
.tab-act .notice-list, 
.tab-act .pds-list, 
.tab-act .notice-more, 
.tab-act .pds-more{
  display: block;
}

---- 선택자의 우선순위 생각하기 
```

## 예제 레이아웃 배치

<img width="422" alt="스크린샷 2020-07-23 오후 7 42 38" src="https://user-images.githubusercontent.com/68043654/88278089-cc626400-cd1c-11ea-992e-1426896e038d.png">

### 내가 한 마크업 및 간단한 레이아웃배치

![수업예제 news Markup-2](https://user-images.githubusercontent.com/68043654/88282078-cc199700-cd23-11ea-9ce4-b98e810a14db.jpg)

- 강사님은 내가 a 태그로 감싼 부분에 article 태그를 사용.



```css
/* 내가짠 새소식 position 사용 */
.news{
  position: relative;
  /* background-color: yellow; */
}
.news-heading{
  color: #db5629;
  font-size: 1.5rem;
  font-weight: 700;
  border-bottom: 1px solid #aaa;
  width: 300px;
  padding: 40px 10px 10px 0;
  margin: 0;

}
.news-item{
  display: block;
  width: 100%;
  margin-top: 25px;
  /* margin-left: 150px; */
}
.news-item .news-item-subject{
  margin: 0;
  margin-bottom: 5px;
  margin-left: 140px;
}
.news-item .news-item-date{
  display: block;
  margin-bottom: 10px;
  margin-left: 140px;
}
.news-item .news-item-brief{
  margin: 0;
  margin-left: 137px;
}
.news-item-thumnail{
  position: absolute; 
  top: 95px;
  left: 0px;
  margin: 0;
  text-align: center;
}
.news-item-thumnail img{
  margin-bottom: 15px;
  box-shadow: 0 15px 15px 0px #ccc;
}
.news-more{
  position: absolute;
  top: 30px;
  right: -8px;
  padding: 8px;
}

```





```css
/* 강사님이 작성하신 새소식 position 사용 */
.news{
  margin-top: 20px;
  position: relative;
}
.news::before{
  content: "";
  position: absolute;
  top: 35px;
  left: 0;
  width: 80%;
  height: 1px;
  background:#aaa linear-gradient(90deg,#aaa, #fff);
}
.news-heading{
  margin: 0;
  font-size: 1.5rem;
  font-weight: 700;
  color: #db5629;
}
.news-item{
  margin-top: 30px;
  padding-left: 130px;
  position: relative;
}
.news-item-subject{
  margin: 0;
  font-size: 1.4rem;
}
.news-item-brief{
  margin: 10px 0;
  line-height: 1.5;
}
.news-item-thumnail{
  margin: 0;
  position: absolute;
  top: 3px;
  left: 0;
  text-align: center;
}
.news-item-thumnail img{
  margin-bottom: 15px;
  box-shadow: 0 15px 15px 0px #ccc;
}
.news-more{
  position: absolute;
  padding: 8px;
  top: -8px;
  right: -8px;
  background-color: skyblue;
}
```

- 내가짠코드의 보완점
  - 강사님은 새소식아래쪽에 border를 주기위해 section영역에 ::before를 줬고
  - 내가 선택한 방법은 h2에 border-bottom을 주고 width 값을 줘서 border의 길이를 조절해줬다,
    - 뭐가 더 나은 방향이라는 판단의 기준 ? 스스로 어떻게 판단을 해 나가야 할지모르겠다!!
  -  그리고 강사님은 figure영역의 이미지를 배치하기위해 thumnail에 absolute , menu-item에 relative를 줬다 news 영역에 relative가 있는데 또 menu-item에 relative를 선언해준것은 section 영역에서 Top,left 값을 조절하는것보다 Menu-item에 relative를 줌으로써 top,left 값을 0으로 줘도 되기때문이다 
  - 내가 선택한 방법은 news 영역에 relative, thumbnail에만 absolute를 줬기때문에 더 비효율적이다

