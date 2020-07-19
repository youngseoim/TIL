```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="UTF-8">
    <title>SALE.ZIP</title>
    <meta name="author" content="YOUNG SEO">
    <meta name="dscription" content="sale collection">
    <meta http-equiv="X-UA-Comatible" content="IE-edge">
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">


    <!-- http://ogp.me/ -->
    <!-- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started.html -->

    <!-- css style -->
    <link rel="stylesheet" href="css/reset.css">
    <link rel="stylesheet" href="css/main.css">

</head>

<body>
    <div class="container">
        <header>
            <div class="Banner_headerTop"><a href="#">
                    <img src="./saleimg/banner.jpg" alt="배너 이미지">
                </a>
            </div>
            <div class="header_menu1">
                <h1 class="logo">
                    <a href="#">
                        SALE.zip
                        <!-- <img src="./saleimg/logo.svg" alt="나는 로고"> -->
                    </a>
                </h1>
                <form action="#" method="POST" class="search_form">
                    <input type="search" id="search" name="search" placeholder="검색어를 입력하세요" required>
                    <span class="search-btn" onclick="$('search_form)
                <i class=" fas fa-search"></i>
                    </span>
                </form>
                <a href="#" class="main_news">회원 가입 EVENT. 신규 가입 시, 15% 쿠폰 + 3,000원 적립금본인인증 시, 10% 쿠폰 제공</a>
            </div>

            <nav class="user_menu clearfix">
                <a href="#" class="login_link">로그인</a>
                <ul>
                    <li><a href="#">회원가입</a></li>
                    <li><a href="#">비밀번호찾기</a></li>
                    <li><a href="#">장바구니</a></li>
                    <li><a href="#">배송조회</a></li>
                    <li><a href="#">고객센터</a></li>
                </ul>
            </nav>

        </header>

        <main class="main_container">
            <section class="main_content">메인 컨텐츠
            </section>
            <section class="main_menu_left">왼쪽 컨텐츠</section>
        </main>

        <footer></footer>



    </div>
</body>

</html>
```





```css
.container{
    max-width: 1400px;
}
a{
    text-decoration: none;
}

/* header */
.Banner_headerTop{
    text-align:center;
}
.Banner_headerTop img{
    width: 100%;
    height: 100%;
}
.header_menu1{
    width: 100%;
    background-color: #000;
    display: flex;
    justify-content: space-around;
    position: relative;
    padding: 23px 0 23px 0;
}
/* .logo img{
    width: 80px;
    position: absolute;
    top: -10px;
} */
.logo a{
    font-size:30px;
    font-weight: 700;
    color:#fff;
}
.search_form{
}
#search{
    width: 200px;
    height: 100%;
    border:none; 
}
button{
    display: none;
}
.main_news {
    display: block;
    /* text-align: center; */
    font-size: 16px;
    font-weight: 400;
    color: #fff;
}

.user_menu .login_link{
    float: left;
}
.user_menu ul li {
    float: right;
    /* display: inline-block; */
    /* justify-content: flex-start; */
    background-color: blueviolet;
}
.user_menu .clearfix::after{
    content: "";
    clear: both;
    display: block;
}

/* 메인 컨텐츠 */
.main_container{
    display: flex;
    flex-flow: row-reverse;
    background-color: gray;
    width: 100%;
    height: 500px;
}
.main_content{
    /* order: 2; */
    background-color: red;
    width: 70%;
}
.main_menu_left{
    /* order: 1; */
    background-color: rgb(49, 204, 83);
    width: 30%;
}

/* FOOTER */
footer{
    background-color: gray;
    width: 100%;
    height: 100px;
}
```

  다음에 해야될 것 

- 검색창에 아이콘 활성화안되는 이유 찾기 
- 유저 메뉴 부분 다듬기 및 flex로 하려면 어떻게 해야되는지 생각하기 
- 기준점 별로 git push 생각하기 (버전관리)