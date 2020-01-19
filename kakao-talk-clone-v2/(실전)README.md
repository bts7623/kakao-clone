# kakao-clone
 nomadcoder kakao-clone coding(실전)

 Kakao Desktop App clone

# Object
  - HTML, CSS 개념을 숙지하고 카카오톡 클론 코딩을 진행한다.

# History
#### 2019.01.12: #0-0 ~ #1-3
#### 2019.01.13: #1-4 ~ #1-5
#### 2019.01.14: #1-6
#### 2019.01.16: #1-7 ~ #1-8
#### 2019.01.19: #1-9
  
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

#### #1-4 Chat Screen
  - friends, find tab에서 comment icon 삭제
  - more tab에서 comment 대신 qrcode icon 사용
  - 채팅창 한칸 우선 구현하기
    + main tag를 써서 브라우져 내의 메인부분 지정(디자인적 측면)
  - .chats의 main tag에 구현
    + ul.chats_list로 채팅목록들이 올 목록 묶음 tag 구현
      * 하위에 li.chats__chat tag를 써서 1개의 채팅창 구현
    + li를 왼쪽부터 [프로필+이름+미리보기], [시간]으로 나눔
      * div.chat__column*2
      * 이 때 chats__chat__column 너무 기니까 chat으로 명명을 바꾸고 헷갈리지 않게 li tag의 class명을 .chats__chat.chat으로 적음.
    + 첫번째 .chat_column은 [프로필]과 [이름, 미리보기]로 나뉨
      * img.chat__avatar
      * div.chat__content
        * span.chat__username
        * span.chat__preview
    + 두번째 .chat_column은 시간으로 span.chat__timestamp
  - 정리
    + 메인영역(main.chats) //디자인 측면
      * 리스트(ul.chats__list)
        * 채팅 1개 영역(li.chats__chat chat) //한개만 만들면 여러개 만들 수 있음
          * 프로필+이름+미리보기(div.chat__column) //프로필까지 column 3개 해도 될듯
            * 프로필 사진(img.chat__avatar)
            * 이름+미리보기(div.chat__content)
              * 이름(span.chat__username)
              * 미리보기(span.chat__preview)
          * 시간(div.chat__column)
            * 시간(span.chat__timestamp)

#### #1-5 Friends Screen
  - 내 프로필 사진이 다른 친구들 아바타 보다 크다.
  - 개발자 마인드로 보고 생각해라.
    + chat, friends 모두 비슷한 폼과 같은 모양의 사진을 쓰고 있다.
      * 이미지를 위한 전역 클래스를 만들어야 한다.
      * g-avatar class를 추가(global avatar)
    + li의 종류가 3가지(나, plus, 친구)이기 때문에 하이픈 2개를 쓴 클래스를 추가하여 구분한다.
      * friend--lg: large라는 뜻(큰 사진) = 내 프로필
    + li로 구분하기 에매해서 header tag를 추가하여 구분함
      * 한 웹페이지에 여러 header를 둘 수 있다.
      * 내 프로필은 header에 둔다.
    + 모든 영역은 2개의 column으로 둔다.

#### #1-6 Find Screen
  - main.find>header.find 생성
    + 4개의 버튼을 div가 아님 ul>li로 구현
      * ul.find__header-btn.header-btn: 규칙을 위해 find__ 하위 명칭 사용
      * 4개 버튼은 크기가 크므로 fa-3x 적용
      * 단어
        * envelop: 편지 봉투, 봉투, 비밀 봉투
    + firend list의 UI가 동일하므로 friends.html에 있는 li를 그대로 가져옴
      * li class명 find__로 변경하고 불필요한 것 제외 및 수정
      * friend-status 삭제, now-listening → add-btn 수정
  - 단축키
    + 단어 블록 씌운 뒤 Ctrl+D를 누르면 아래 방향으로 같은 단어 하나씩 같이 블록 씌워짐

#### #1-7 More Screen
  - friends.html의 header 프로필을 가져와서 이용한다.
  - 버튼들은 ul을 통해 만들어준다.
  - fontawesome 새로운 타입
    + fab > brand

#### #1-8 Setting Screen
  - more에서 설정 버튼 클릭 시 이동되도록 설정 이모티콘을 a tag로 만듦
  - more.html을 복사해서 붙여넣고 필요없는 부분 삭제
    + status bar, header에서 이름과 돋보기 빼고는 다 삭제
  - main > header에 버튼 생성

#### #1-9 Chat Screen
  - setings.html 복붙한다.
  - index.html에 가서 컨텐츠 li tag 하위 내용을 모두 a tag 안에 넣는다.
  - 三 같이 생긴 목차 아이콘을 '햄버거바'라고 부른다고 함.
    + fontawesome에서 hamburger로 검색
    + search icon 뒤에 div에 넣어서 삽입
  - settings의 main은 필요 없으니 삭제
  - 대화 메시지를 남길 리스트 작성
  - 대화 메시지는 총 2가지(내꺼, 남의꺼)
    + incoming-message: 도착하는 메시지
      * content>author+bubble
        * author: 글쓴이 이름
        * bubble: 메시지 내용(카톡이 버블 같아서 쓴듯?)
      * timestamp: 받은 시간
    + 보내는 메시지
      * 아바타 삭제, 글쓴이 이름 삭제, timestamp 위치 왼쪽으로 이동
  - 메시지 창은 main에 넣고 메시지 아래 입력 바는 main 밖에 만듦

#### VSCode 단축키
  - Art+Shift+방향키: 해당 라인 위, 아래에 복사하기
  - Art+Shift+I: 블록한 라인 맨 뒤에 커서 두기
  - Art+Shift+Drag: 블록한 라인에서 해당 마우스 커서 위치를 기준으로 커서 두기
  - Ctrl+home/end: 맨위, 맨아래
  - Ctrl+B: 사이드바 숨기기
  - 단축키들은 File>Preferences>keyboard shortcuts에 들어 있음

---

#### #2-0 ResetCSS
  - HTML은 기본적으로 padding, margin등의 디폴트 값이 정해져있다.
  - 그것 들은 모두 0으로 만드는 것을 reset.css 추가로 한번에 진행하고자 함.
  - 참고 링크
    + [reset css](https://meyerweb.com/eric/tools/css/reset/)

#### #Day9 Code Challenge
  - #2.0 ~ #2.3
  - 조건
    + Use flex box
    + Use Google Fonts
    + Use Font Awesome