# kakao-clone
 nomadcoder kakao-clone coding(실전)

 Kakao Desktop App clone

# Object
  - HTML, CSS 개념을 숙지하고 카카오톡 클론 코딩을 진행한다.

# History
#### 2019.01.12: #0-0 ~ #1-3

  
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
  - Status Bar
    + 좌측 시간, 우측 상태 값 구현
    + .status-bar의 큰 frame을 만들고
      * 2개의 .status-bar__column을 만들고
      * 하나는 span.status-bar__clock
      * 하나는 각각의 아이콘들과 베터리 잔량을 표기하는 span.status-bar__battery-level
    + 아이콘들은 fontawesome에서 가져옴
      * 다양한 유/무료 아이콘 CSS 추가 가능
      * Start에서 이메일 입력하면 kit을 주고 해당 link를 추가해주면 됨
        * 강좌에서는 CSS link인데 지금 주는 것은 script문 한줄임
      * 이후 icon 탭에 가서 검색하고 좌측 메뉴에서 free 선택해줌
      * 검색된 아이콘 눌러서 class명 받아서 사용하면 됨
  - 참고 링크
    + [fontawesome](https://fontawesome.com/icons?d=gallery)

#### #1-2 Screen Title
  - header: Status Bar 하단부에 위치한 부분 header tag를 써서 구분해줌(header tag에 header class 추가)
  - header.header 추가 > header__header-column 2개 추가
    + 왼: Chats text 부분, 오: 아이콘 부분
      * 왼쪽에는 h1으로 Chats를 써줌
      * 오른쪽에는 header__icon 3개 추가
  - icon
    + fontawesome icon tag에는 규칙이 있음.
      * far: Regular Style > 선만 딴 형태
      * fas: Solid Style > 채워져있는 형태
      * size: .fa-5x  추가 > 5크기로 변경
      * fa-iconName: fa는 fontawesome인듯. 모든 아이콘 이름 앞에는 'fa-'가 붙음

#### #1-3 Navigation Bar
  - nav tag로 메뉴 frame을 만들고 ul, li tag로 리스트를 추가함
    + nav>ul>li
    + nav: 웹 사이트에서 주요한 지점으로 이동할 수 있는 navigation tag. html5가 되면서 모든지 div에 넣었던 방식에서 영역별로 나누어 작성할 때 일반적으로 메뉴와 같은 부분을 nav태그로 만든다.
    + ul>li는 순서가 상관없는 리스트를 구현할 때 사용되며, 보통 ul에 여러개의 li tag를 넣고 li tag에 a tag를 넣어 링크 이동하도록 구현함.
  - 카톡 하단부 친구창, 대화창, 검색창, 더보기 메뉴바를 구현
    + icon 검색: user, message, search, ellipsis(점 3개)
  - 해당 탭이면 해당 아이콘은 채워지고(fas) 그 외는 채워지지 않은 아이콘(far)으로 하고자 하는데 유료 아이콘이 있어서 제한됨
  - 각 선택지로 이동할 때마다 title, header의 문구, 아이콘의 채워짐을 변경해줌
    + 지금까지 작성된 것을 복사해서 다 넣어줌