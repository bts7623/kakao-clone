# kakao-clone
 nomadcoder kakao-clone coding(실전)

 Kakao Desktop App clone

# Object
  - HTML, CSS 개념을 숙지하고 카카오톡 클론 코딩을 진행한다.

# History
#### 2019.01.12: #0-0 ~

  
# Concept
#### #0-0, #0-1
  - Introduction
    + 이 강좌는 버전업된 2번째 버전이다.
    + Atom에서 VSCode를 쓴다.
  - Project Setup
    + GitHub Desktop Repository 연동
    + 소스폴더에 .gitignore 파일을 만들어서 특정 파일은 Repository에 올라가지 않도록 설정
      * .gitignore 파일에 비밀소스나 파일을 적으면 Repository에 안올라간다고함.
      * 여기서는 macOS에서 생성하는 .DS_Store를 적었는데 잘 모르겠음
  - Project Plan
    + 카카오톡의 chats, find, friends, settings, more 페이지를 만들꺼임
      * 이 때 chats화면이 index 화면이 됨

#### #0-3 What are we using
  - 사용 툴 설치
    + ColorZilla, PageRulerRedux
    + 이미 이론편에서 설치함
  - VSCode는 emmet이라는 모듈을 사용하기 때문에 html:5 입력하여 폼 생성하는 등의 작업이 default로 가능

#### #들어가기에 앞서
  - 이론 마지막 homework로 BEM에 대한 링크가 있었다.
    + 대충 느낌은 왔지만 한글판 포스팅을 보니 BEM은 CSS 작명법 중 하나로 이름 자체로도 해당 element가 어떤 것을 의미하는지 알릴 수 있는 방법이다.
  - BEM 표기법
    + .block{}
    + .block__element{}
      * block의 자식 요소이다.
    + .block--modifier{}
      * block의 다른 상태나 버전을 나타낸다.
    + 하이픈(-), 언더스코어(_)를 두 개 사용하는 이유는 block 자체의 명칭에 하이픈, 언더스코어가 사용될 수 있기 때문이다.(ex_btn-danger, bts-success)
    + BEM의 핵심은 다른 개발자들에게 이 마크업이 무엇을 하는 놈인지 이름 자체로 많은 것을 알려줄 수 있다는 것이다.
  - 참고 링크
    + [BEM으로 사고하기](https://mytory.net/html-css-js/2015/05/07/mindbemding-getting-your-head-round-bem-syntax.html)

#### #1-1 Status Bar
  - 항상 컴포넌트 단위나 반복되는 페이지 순서로 개발함(하나의 분리되고 독립적인 것)
    + 헤더, 스테이터스 바, 네비게이션 바 등
  - 참고 링크
    + [fontawesome](https://fontawesome.com/icons?d=gallery)
      * 다양한 유/무료 아이콘 CSS 추가 가능
      * Start에서 이메일 입력하면 kit을 주고 해당 link를 추가해주면 됨
      * 이후 icon 탭에 가서 검색하고 좌측 메뉴에서 free 선택해줌
      * 검색된 아이콘 눌러서 class명 받아서 사용하면 됨