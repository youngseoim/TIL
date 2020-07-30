  

### Background blur효과

- filter: blur(0); 
  - 필터 속성을 이용해서 background에 blur효과를 주려고 했으나 텍스트까지 블러처리가 되기때문에 사용하지 않았다
- Background 속성에 rgba 값을 (0,0,0,0.5)를 줘서 반투명한 상태로 뒤에 배경을 비추게했다
  - Filter:blur 방식과는 다르게 텍스트는 남고 배경이 비쳤지만 blur 효과를 주지 못했다
- Backdrop-filter를 사용하면 원하는 결과값을 도출할 수 있지만 아직 브라우저 호환이 안되는경우가 많다

### 속성 선택자

- [Attribute=value]

  - attr이라는 이름의 특성값이 정확히 value인 요소를 선택합니다.

- [attr~=value]

  - attr이라는 이름의 특성값이 정확히 value인 요소를 선택합니다.
  - attr특성은 공백으로 구분한 여러 개의 값을 가지고 있을 수 있습니다.
  - Ex) [class~=클래스명 클래스명 클래스 명]

- [attr|=value] 

  - attr이라는 특성값을 가지고 있으며, 그 특성값이 정확히 value이거나 value로 시작하면서 -(U+002D)문자가 곧바로 뒤에 따라 붙으면 이 요소를 선택합니다 . 보통 언어 서브코드(en-US, ko-KR등)가 일치하는지 확인할 때 사용합니다 .

- [attr^=value] 

  - 접두사 value가 값에 포함되어 있으면 이 요소를 선택합니다 .
  - btn__search  >> Btn이 접두사

- [attr$=value] 

  - 접미사 value가 값에 포함되어 있으면 이 요소를 선택합니다.
  - btn__search >> Search가 접미사 

- [attr*=value] 

  - 값 안에 value라는 문자열이 적어도 하나 이상 존재한다면 이 요소를 선택합니다.
  - [h2*=btn]  >> btn이 들어간 클래스를 전부 선택 

  

  ###  오늘 공부한 예제

  <img width="516" alt="스크린샷 2020-07-30 오후 9 39 16" src="https://user-images.githubusercontent.com/68043654/88923843-4b234800-d2ad-11ea-8907-8d100e30bbee.png">

  - 추천서적, 새소식, 게시판, 트위터, 인기 사이트 sprite기법 

    -  ```css
      .sprite{
        background-image: url(./images/sprite_main.png);
        background-repeat: no-repeat;
      }
      .spriteBook{
        background-position: 0 0;
      }
      .spriteNews{
        background-position: 0 -230px;
      }
      .spriteBoard{
        background-position: 0 -115px;
      }
      .spriteFavorite{
        background-position: 0 -345px;
      }
      .spriteTwitter{
        background-position: 0 -460px;
      }
       ```

    - 전체 제목영역에 background image를 넣어준 후에 각 요소별로 포지션만 이동해준다 

    - sprite 기법을 사용하는 이유는 여러장의 이미지를 랜더링하는것보다 한장의 이미지를 랜더링하는것이 성능이 훨씬 좋기 때문에

  

  ### 내일 하게 될 메인영역 video 속성

  - src

    - 비디오 파일의 주소

  - controls

    - 컨트롤러 표시

  - autoplay

    - 자동재생

    - 자동재생은 접근성 관련해서 보조기기의 도움을 받아서 보이스오버를 사용하는 유저들이

      접근했을때 자동재생되면 오디오가 겹치는 현상 때문에 몇 몇 브라우저에서 금지되어 있다.

    - 단 muted속성을 사용해서 음소거 처리를 해준경우에는 auto값을 사용가능하다.

  - loop

    - 반복 재생

  - width / height

    - 영상의 가로,세로 길이

  - Muted

    - 음소거

  - Video태그가 지원하는 형식은 

    - ogg, mp4, webm의 확장자만 지원하기 때문에 사용하기 까다롭다 