# Git / Github



## Git 저장소 공간

- 작업트리(work tree) : 현재 작업중인 파일
- 인덱스(index) : 작업트리에 파일들은 stage로 이동 , commit하기 전의 위치
- 저장소(Repository) : 스테이지의 파일들은 commit해서 push하면 저장되는곳 

--> Git을 이용해서 효율적으로 버젼관리 

## Git 명령어

### git config

- 사용자 이름 등록 : git config --global user.name "John Doe" 
- 사용자 이메일 등록: git config --global user.email johndoe@example.com 
- Git의 설정 정보 조회 : git config --list
- --global 옵션을 주면 전역 속성을 적용시킨다 

### git status

- 현재 상태를 나타낸다

### git add

- 특정 파일 stage 시킨다 = git add 파일명

### git commit

- 현재 인덱스 상태를 저장소에 저장 
- 커밋 메세지 : git commit -m(message)
- 방금 작성한 커밋메세지 내용추가 : git commit --am 

### git rm

- remove의 약자로 파일을 삭제한 후 stage 한다 
- 지정한 파일 삭제하고 stage : git rm 파일명 

---

### 그 외 git 명령어

- Mkdir = 메이크 디렉터리 (디렉터리 생성)

- Touch = 새로운 파일 만들기  touch index.html 

- Echo = 파일을 만들면서 내용을 추가할때, 기존 파일의 내용을 덧붙임

   Ex) echo '<!doctype html>' >> 경로

- cat = 파일안의 내용 확인

- Ls = 파일 보기 

- ls -a  = 숨은 파일 보기 

- git add 파일명  >> 스테이지로 보낸다 

- git commit -am 'head 요소 추가' >>

- git rm --cached index.html   >> 스테이지로 올라간 파일을 다시 내린다

- clear : 터미널창 클리어 시키기 / :q 빠져 나오기  /   :wq 세이브 후 빠져나오기 

  ​	--- > clear의 경우 마지막 입력 상태에서 창만 새롭게 보여준다 , :q의 경우 내용이 끝나지 않은상태로 이어질때 강제로 나온다 

- Git log --oneline == >로그를 한줄로 보여주세요

- Git reset//hard of soft  초기화 하고 전으로 돌아간다 

- git remote -v >> romote 저장소의 위치확인 



---

# HTML / CSS - day 1



!<doctype> -- > 문서적 정의

HTML 4.0 / XHTML   ㅡㅡ> HTML 5 에 비해 dtd3가지중 한가지를 선언해 줘야하는 단점 존재

- HTML = root element 

attribute / property 의 차이

- attribute는 DOM안에 존재하지만 변하지 않는 값, property는 DOM안에 존재하지만 동적이기때문에 변할 수 있다
- attribute는  id,style,href,target,link등 속성 그 자체의 objecte
- property는 name,color,font 등 위 속성들의 object가 가지고 있는 구성 요소이다 

<html lang="ko-kr">  html의 attribute(속성)은 lang(렝귀지)를 사용, 언어와 국가코드 명시 

* 접근성 (Accessibility)을 꼭 고려하자 
* Seo 검색 최적화를 위해 타이틀은 그 사이트를 대표하는 중심 키워드
* 디자인도 중요하지만 컨텐츠로 나눠서 마크업을 해야 검색최적화가 잘 된다 
* Header,nav,footer등 컨텐츠를 나눌 수있는 태그는 사용하고 그 외에 애매한 태그에만 div사용하기
* article 태그 = 독립적인 컨텐츠   // section = 큰 단락  둘다 기준이 애매하기때문에 둘다 사용해도된다 
* 클론코딩이나  유명한 개발자의 github에서 코드를 볼 때 그 태그를 사용한 이유에 대해서 생각하기 

