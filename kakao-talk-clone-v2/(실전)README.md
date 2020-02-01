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
#### 2019.01.21: #2-0 ~ #2-1
#### 2019.01.26: #2-2 ~ #2-7
#### 2019.01.27: #2-8 ~ #2-12
#### 2019.01.29: #2-13 ~ #2-15
#### 2019.01.31: #2-16 ~ #3-0
#### 2019.02.01: #3-1 ~ 3-7
  
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
  - reset.css
    + HTML은 기본적으로 padding, margin등의 디폴트 값이 정해져있다. 
    + 그것들을 모두 0으로 만드는 것을 reset.css 추가로 한번에 진행하고자 함.
    + reset.css를 만들어 해당 내용을 넣음
    + styles.css에 @import "reset.css";하여 reset.css를 import한다.
    + 각각의 html에는 styles.css를 link한다.
    + reset.css는 h1의 글씨 크기를 기본 폰트와 같게한다던가 ul, li 기본 나열을 한다던가 하는 것처럼 모두 초기화해버림 > 모든 기본 style 값을 없앰
  - nomalize.css
    + 모든 브라우저에서 각각의 요소들의 기본 값으로 통일되어 보이게 하는 것
    + h1을 h1사이즈로 보인다던가 표준을 따름 > 기본 style 값
  - 참고 링크
    + [reset css](https://meyerweb.com/eric/tools/css/reset/)

#### #2-1 Status Bar
  - css 기본 값 설정
    + body style을 설정함으로써 내부 기본 CSS 설정
      * background-color: white;
      * padding: 10px 20px;
        * 카카오톡 UI에 들어간 padding 설정(chrome tool을 이용하여 측정)
      * color: #020202;
        * 약간 검은색으로 text color가 들어감(chrome tool을 이용하여 측정)
  - status-bar.css
    + status-bar css를 별도로 만들어서 styles.css에 import한다. 
    + display: flex; 
      * 모든 element를 바로 옆으로 이동시키는 것(세로 → 가로) 
      * status-bar div 아래 있던 status-bar__column 2개가 가로로 배치된다. 
        * 시간과 와이파이, 베터리등 상태 아이콘들
    + justify-content: space-between;
      * 가로로 배치된 두 요소를 양 끝으로 떨어뜨리기
    + margin-bottom: 30px;
      * status-bar와 header 사이 거리 추가 
    + google fonts에서 원하는 typography 고르기
      * 원하는 font를 고르고 CUSTOMIZE를 통해 원하는 값을 선택하고 EMBED 탭에서 import 소스를 복사해서 css파일에 import함
      * CUSTOMIZE에서 너무 다양한 크기를 체크할 경우 로딩 속도가 느려져 비추
      * bodt style에 적용
        * font-family: 여러 글꼴을 쉼표(,)로 구분하여 우선순위를 정의한다.
        * 앞에서부터 해당 폰트가 없으면 다음 폰트를 적용한다.
        * 띄어쓰기가 들어간 폰트명은 작은따옴표, 큰따옴표로 감싸준다.
        * google fonts에서 고른 폰트를 맨 앞에 두고 뒤에부터는 -a를 입력할 때 자동완성되는 디폴트 값을 쓴다.
    + .status-bar i{font-size: 14px;}
      * status-bar의 아이콘의 크기를 조금 줄인다.(기본 16px인듯)
    + opacity: 0.7;
      * header 및 main 글꼴보다 조금 연한 부분을 표현하기 위해 투명도를 준다.
      * 0.8의 경우 70%  
    + 배터리와의 간격을 조금 두기 위해 .status-bar__battery-lever에 margin-left: 5px; 추가
  - 참고 링크
    + [google fonts](https://fonts.google.com/)  

#### #2-2 Header
  - header 마찬가지로 display: flex, justify-content: space-between 해주기
  - font-size:24px, font-weight: 700 하기
    + font-seight는 글씨 굵기인데 여기서는 google font에서 import한 size만 쓸 수 있다.
  - margin-bottom: 30px
  - icon
    + size 키우기
      * .header__icon font-size:20px; 
    + content들이 위쪽에 붙어있기 때문에 align-items center 추가
    + icon 간 간격 주기
      * margin-left: 20px
    + 아이콘에 마우스를 대면 클릭 모양 되도록
      * cursor: pointer; 
  - div는 display:block이 되어있기 때문에 모양이 망침. span은 inline 
  - a tag 클릭 시 보라색되는 것을 막는 작업 진행
    + a{color: inherit;} 부모의 색을 따른다는 뜻 

#### #2-3 Navigation Bar Part One
  - nav-bar.css 생성 및 import
  - 스크롤을 해도 제 자리에 있고, body에 걸어놓은 padding이 안 먹어야해서 해제한다.
    + sticky(끈적거리다)하게 할 것 
    + position: fixed;
      * 해당 element를 데어다가 다른 레이어에 올려두기 때문에 width를 설정해주어야만 한다.
        * background-color를 해서 확인한다.
      * top OR bottom, left OR right를 통해 element의 위치를 잡는다. 
    + 아이콘과의 간격을 padding해준다.(20px, 50px) 
    + nav-bar와 main 사이에 1px의 작은 border가 있다.
  - status-bar, header도 fixed로 해보기.
    + 생각보다 잘 안됨  
  - .nav__list{ position: flex; justify-content: space-between;} 
    + 이 때, 마지막 아이콘이 화면에서 사라지는 오류가 발생
      * box-sizing 설정을 border-box로 바꿔서 해결 
  - box-sizing
    + Parent container 안에 있는 content의 사이즈 범위를 설정하는 값
    + content-box, border-box 2가지 형태가 있다.
      * content-box: CSS 기본값으로 content 영역이 100px일 때 테두리(border)와 안쪽 여백(padding)이 추가되면 해당 너비가 content 너비에 추가되어 부모 크기를 넘어가면 삐져 나감
      * border-box: border, margin 추가 시 부모 크기를 벗어나게 되면 content 크기를 줄여서 사이즈를 맞춘다. → 보통 box-sizing: border-box;를 해야 크기 조절이 편함
    + 따라서 마지막 아이콘이 사라진 이유는 설정값이 content-box로 되어있어서 padding값을 합친 크기가 부모 div를 삐져나가서 그렇다.
  - 참고 링크
    + [box-sizing MDN](https://developer.mozilla.org/ko/docs/Web/CSS/box-sizing)

#### #Day9 Code Challenge
  - #2.0 ~ #2.3
  - 조건
    + Use flex box
    + Use Google Fonts
    + Use Font Awesome

#### #2-4 Why Border Box
  - box-sizing: border-box에 대한 설명

#### #2-5 Navigation Bar Part Two
  - 채팅이 왔을 때 채팅 이모지에 빨간 숫자 넣기
    + position: relative, absolute 이용
      * 자식 absolute, 부모 relative하면 가서 붙는다.
      * 부모기준 top(bottom), right(left)로 위치 정해줌
  - 아이콘이 들어가 있느 nav__list-link div안에 nav__badhe div 생성 
    + 숫자 정렬을 위해 display: flex, justify-content: center, align-items: center 해줌
    + border-radius: 50%를 줘서 원모양을 만든다.

#### #2-6 Friend Component Part One
  - 친구창과 채팅목록창이 거의 비슷하기 때문에 한번에 같은 CSS를 적용하기 위해 friend.html에 있는 구조를 index.html에 그대로 사용한다.
  - 단, li class명에 Chats__chat은 유지해주고 차이나는 부분의 class명을 바꿔준다.
    + chat__timestamp: 마지막 채팅 시간을 표기
    + friend__bottom-text: 친구 프로필와 글씨 크기가 조금 차이나서 별도 구분
  - display: flex 했을 때, li tag 안에 a tag가 들어가면 flex가 안먹는 오류 발생
    + 잘 모르겠다. 니꼴라스는 li를 2번써서 난 오류인데 나는 그게 아니었음.
    + 우선은 flex 이용 시 대상의 div 구조를 파악하는 것으로 정리하자.
  - 사진 크기 조정
    + .friend .friend__avatar가 있고, g-avatar가 있다. (각각 width: 50px, 70px)
      * 이 때 friend__avatar는 .friend .friend__avatar로 .friend 자식으로 있는 .friend__avatar에게 적용
      * g-avatar는 .friend__avatar.g-avatar 띄어쓰기를 하지 않으므로써 2개의 클래스 모두를 갖고 있는 element에 속성을 부여한다.

#### #2-7 Friend Component Part Two
  - 사진 크기 나누기
    + 친구창과 더보기의 프로필 사진은 g-avatar 70px
    + 대화목록 사진은 m-avatar 60px
    + 나머지는 50px
  - text-decoration: none;
    + 링크에 밑줄 쳐지는 것을 없앰
  - 프로필과 알림말 사이 margin-right: 15px 추가
    + 이 때 margin이 아닌 padding을 주게되면 box-sizing: border-box 속성 효과로 프로필이 작아진다.
  - .friend__content .friend__name{display: block}
    + 이름 span이 상태메시지 span을 아래로 밀어준다.
  - CSS에 .class 2개를 적을 때는 항상 하나 위 부모 클래스를 적어준다.
  - friend__status, friend__bottom-text, chat__timestamp 글씨크기, 투명도 조절

#### #2-8 Friends Screen
  - friend.css > 프로필 하나의 CSS
  - friends.css > friends.html의 전반적인 CSS
  - plus friend 상하에 padding, margin, border 추가
  - 멜론 음악표기 부분은 friends.css가 아닌 friend.css에서 진행
    + 확실한 구분 필요. 개별CSS냐 창 전체 CSS냐
    + padding을 준 뒤 boreder-radius 하면 동그래짐
    + opacity, font-size 조절

#### #2-9 Find-Screen
  - flex를 2번 적용시킴
    + 4개의 아이콘을 가로정렬하고 space-between 하기 위해서 list에 적용
    + 아이콘과 이모티콘을 세로로 두고 가운데 정렬하기 위해 li에 적용
      * flex-direction: column, align-items: center; 
    + 좌우 padding 주려다가 space-around로 해결 
  - 이모티콘 title에 margin top 주고 이모티콘, title 둘 다 사이즈 줄임
  - header는 끝났고 recommended에 padding-top, margin-top, border-top 줌
  - 필요한 부분에 margin을 줌
  - 친구추가 아이콘에 background-color, padding, border-radius 진행

#### #2-10 More Screen
  - Find와 다를 바가 거의 없음.
    + 상단 이모지와 하단 이모지 배치가 거의 비슷하므로 묶어서 CSS 적용하는 정도 참고
    + 나는 Suggestions에 사진을 썻지만 니콜라스는 이모지에 background-color를 입힘
  - Suggestions icon에 이모지 버전과 사진버전 둘로 나눔 
  - 참고 링크
    + [Cursor MDN](https://developer.mozilla.org/it/docs/Web/CSS/cursor)

#### #2-11 Settings Screen
  - 뒤로가기 화살표와 이모티콘 크기가 같아야 하기 때문에 header.css를 참고
  - 화살표 문구와 일직선이 되도록 크기 및 간격 통일
    + font-size: 20px, margin-right: 20px;  
  - 기존 캡처 화면과 다른방향으로 진행
    + 문구의 굵기를 300으로 진행. google font 스크립트에서 300추가 
      * 얇은 글씨가 됨 
  - margin-bottom, padding-bottom이 합쳐져서 하단부가 너무 많이 간격이 떨어짐
    + .settings__setting:last-child{margin-bottom:0;}을 통해 마지막 부분에는 margin은 주지 않음
  - dribbble, pinterest
    + 멋진 디자인을 찾을 수 있는 웹사이트
    + b가 3개임
    + 디자이너들이 만들어 놓은 다양한 기능의 디자인들을 참고할 수 있음
  - 참고 링크
    + [dribbble](https://dribbble.com/)  
    + [pinterest](https://www.pinterest.co.kr/)

#### #2-12 Chats Screen Part One
  - 기존 캡처화면이 아닌 버전으로 작업 진행
    + 영감은 전 강의에서 보여준 bribble과 pinterest에서 참고
  -  채팅 입력창(chat__write)
    + fixed해서 하단에 고정시켜놓고 가운데 정렬한다.
      * fixed 된 container를 가운데 정렬하는 법
        * margin: 0 auto; //상하 0, 좌우 여백 동일하게
        * left: 0, right: 0 //fixed 위치 좌, 우 0
    + 하단에 그림자 생성
      * box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.6);
      * box-shadow: 수평 수직 퍼짐정도(blur) rgba(r, g, b, 투명도);
      * 그림자 2개를 붙일 수도 있다.
        * box-shadow: 그림자A, 그림자B, 그림자C;
  - 다른 웹사이트에서 영감을 얻어 해당 부분의 CSS 요소를 개발자 모드에서 복사해서 그대로 가져올 수 있다.
    + 그림자 요소는 stripe.com에서 영감을 받았다.
    + stripe.com 하단부 그림자 부분을 개발자 모드에서 가져온다.
  - 입력창 설정
    + width: 80%를 준다.
      * .chat__write-column:nth-child(2)로 2번째에만 준다.  
      * 전체 div에서 입력창에게 80% 영역을 할당해주기 위한 작업인듯하다.
    + input만 빼서 width: 100%, padding: 10px, border: none; 준다.
      * 80% 영역에 input text로 가득차게하고 padding으로 두툼하게 만든다. 
      * text가 상하좌우 여백을 두고 가운데에 써지도록 된다.
      * border: none으로 테두리를 없애준다.
    + input:focus{outline: none;}
      * text 입력 시 생기는 테두리를 없애준다.  
    + outline
      * border보다 바깥에 생성할 수 있으며, 여러 속성이 있지만 결국엔 border처럼 outline: 1px solid red; 식으로 설정할 수 있다.
      * outline-offset: 15px; 등으로 border와의 거리를 지정할 수 있다.
  - 채팅창을 꾸밀 이미지를 subtle patterns에서 찾는다. 
    + image 폴더에 넣고 background-image:url("../images/chatBg.png")로 넣는다.
    + 채팅창을 꽉 채우기 위해 body에 클래스명을 넣어 padding 0을 해주고, header, status-bar에 따로 padding: 0 20px;를 넣어 채팅화면을 제외하고는 padding을 유지시켜준다.
  - .chat{min-height: 100vh;}
    + chat 클래스가 적용된 div에 viewport의 100% 높이를 주는 역할
    + viewport는 screen
  - 참고 링크
    + [stripe](https://stripe.com/)  
    + [outline w3schools](https://www.w3schools.com/css/css_outline.asp)
    + [outline MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
    + [subtle patterns](https://www.toptal.com/designers/subtlepatterns/)

#### #2-13 Chats Screen Part Two
  - index.html에도 chat class명을 써서 문제가 생김. chat.html에서는 chat-screen으로 클래스명 변경 > CSS에도 변경
  - 이것 역시 니콜라스식으로 디자인 시작.
  - flex주고 방향 column해주고 padding margine 주기
  - timestamp에 padding, 그림자, 대문자 표기, 굵게(700) 적용
  - 사진, 대화창
    + 대화창, 사진 배열 후 사진을 동그랗게 만들기
    + width 100%줘서 라인 전체 차지하게 하기 
      * 나중에 50%로 바꿈
      * align-self: flex-start;로 왼쪽에 붙임
    + padding: 0 20px;로 좌우 여백 주기
  - 참고 링크
    + [align-self MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self) 

#### #2-14 Chat Screen Part Three
  - align-items: flex-start;
    + 상대방 프로필을 위로 올리고 싶어서 사진 class 별도로 flex 설정을 했었는데 그냥 모두를 감싸고 있는 li class인 message class에서 flex-start하면 됐다.
    + 사진은 중간에 있었으니 올라가고 이름과 문구도 해당 height 내에서 위로 올라간다. 
  - 닉네임과 bubble 사이 간격 띄우기
    + .incoming-message .message__author에 margin-bottom: 10px;
      * display: block;을 해준다. block 요소로 지정해줘야 적용되는듯.
        * 아마도 span이 inline 구문이라 그런듯?

#### #2-15 Chat Screen Part Four
  - bubble에 그림자가 안먹어서 니콜라스는 div에 text가 있어서 문제였다.라고 하면서 span으로 바꿧지만 나는 애초에 그림자가 div에서도 잘 먹혀서 그냥 둠(참고)
  - uiGradients
    + 이론편에서 잠깐 나왔던 것 같은 홈페이지. 새로고침을 하면 계속 새로운 그라데이션을 보여준다. 
  - background-image:linear-gradient(시작 색, 끝 색);
    + 배경색에 그라데이션을 줄 때 사용  
  - 참고 링크
    + [uiGradients](https://uigradients.com/)
    + [linear-gradient MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)

#### #2-16 Bugfixing
  - 니꼴라스의 버블들이 margin-bottom을 먹지 않는 문제를 해결하는 영상
  - #2-15에서 bubble에 그림자가 안먹어서 니콜라스가 span으로 div들을 바꿨는데 결과적으로 span이 box처리가 안되어서 margin을 먹지 않게됨
  - 따라서 니콜라스는 span처리를 해서 그림자가 생긴줄 아니까 css에서 bubble display: block; 처리를 해줘서 span이지만 box로 인식하게해서 margin을 줌
  
#### #3-0 Fixed Header
  - header 고정
    + header를 고정시키기 위해 status-bar와 header를 header-wrapper div로 감싼다.
    + position fixed를 해주고 top: 0px, width: 100%, background-color: white 해준다.
    + box-shadow를 가져와 적용시켜준다. 너무 진해서 맨 앞꺼는 지움
  - main 부분인 chat-screen에 margin-top: 100px해줘서 간격을 맞춰준다.

#### #3-1 Going Crazy Part One
  - 기존 text input을 버리고 클릭 했을 때 효과가 들어간 input을 만들고자 함
  - input:focus 때 이모티콘을 숨기려면 이모티콘 태그들이 input 태그 보다 뒤에 있어야 한다.
    + 다 뒤로 보냄.
    + 이모티콘 position: absolute로 모두 변경
  - sibling
    + 잘모르겠음. CSS 특정 요소 선택 시 해당 요소 이후의 요소들만 선택된다는 듯
    + input 다음 요소에만 CSS를 줄 수 있기 떄문에 input tag이전 요소에는 CSS를 줄 수 없다.
    + .chat__write:focus ~ .chat__icon{display: none;}
      * .chat__write(input tag) 다음에 있는 sibling 선택
      * opacity: 0으로 해서 transition 먹임
  - sibling selector
    + CSS 적용 요소를 선택하는 방법 중 하나로 ':, +, ~' 등으로 요소를 선택한다.
    + 여기서 쓰인 요소는 '~'로 형제 요소들을 선택하는데 해당 input 하위 형제들만 선택하는 것 같다.
  - 참고 링크
    + [sibling selector](https://www.codingfactory.net/10791)

#### #3-2 Going Crazy Part Two
  - .chat__write:focus{}
    + 줄어들면서 위로 올라와서 그림자와 둥근 테두리 갖기
      * box-shadow, transform: translateY(-100px);, width: 80%, border-radius
    + transition: all 0.5s ease-in-out;을 넣어서 자연스러운 효과 추가
  - container에 padding 좌우가 걸려있어서 input 양 옆에 공백이 있었음. 그래서 지워줌
  - .chat__write margin: 0 auto;
    + input tag 정렬을 안해놓으면 transition 시 왼쪽으로 치우쳐짐
  - 참고 링크
    + [transform MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)   

#### #3-3 Message Animation
  - 개요
    + 입력 input 창에 그림자가 넘실거리는 float animation 주기
    + incommung message, sent message 양 옆에서 나오는 animation 주기
  - 입력 input 창에 그림자가 넘실거리는 float animation 주기
    + @keyfrmaes floating{}
      * 그림자 3개 넣어서 50%에 변화 추가
      * transform: translateY()추가해서 둥실둥실 추가
        * 기존 효과가 이미 -100이므로 -100 ~ -110으로 작성
    + .chat__write:focus에 animation 추가 해서 linear, infinite 하기 
    + infinite로 무한 반복 시켜서 둥실 둥실 느낌 나기 
    + 문제가 생김. translate 기본값이 -100px라서 자연스럽게 안올라가고 점핑되듯이 확 튐.
    + 니콜라스는 따로 처리 안하고 그냥 translate 효과 없애고 그림자만 갖고가기로 함.
  - incommung message, sent message 양 옆에서 나오는 animation 주기
    + to, from으로 만들고 transform: translateX();로 효과를 준다.
    + forwards 효과를 줘서 마지막 상태로 유지되도록 작성

#### #3-4 Fade Animations
  - 개요
    + 채팅창 프로필 그림자 주고 Y축으로 회전하기
    + main창 load 시 아래에서 위로 올라오기(50px)
    + navigation bar main창 load 후 아래에서 올라오기(80px)
  - 채팅창 프로필 그림자 주고 Y축으로 회전하기
    + @keyframes spinImg{}
    + transform: rotateY(1turn);
    + animation: spinImg .5s linear infinite;
  - main창 load 시 아래에서 위로 올라오기(50px)
    + styles.css에 main animation 적용
  - navigation bar main창 load 후 아래에서 올라오기
    + nav animation 걸기
    + animation-delay: 0.5s; 줘서 main load 후 load되도록 설정
    + 처음부터 nav-bar가 사라졌다가 올라올 수 있도록 nav 설정에 transform: translateY(80px); 넣어주기 

#### #3-5 Screen Size Media Query
  - 개요
    + 브라우저 폭 최소 사이즈가 일정 이상일 시 경고 문구 화면으로 화면을 가림
  - min-width: 500px 이상이면 화면 출력
    + span.notice 
      * 모든 html 최 하단에 경고문구 span을 넣는다.
      * nav 밑에 정도? 
      * z-index: 4; 정도 넣어줘야 header-bar에 안 묻힌다.
      * position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      * 나머지 알아서 맞춰주고 display: none을 해준다.
        * 이 때 opacity: 0;으로 해버리면 화면을 가리고는 있기 때문에 다른 기능들 클릭이 안된다.
    + mobile.css 
      * @media screen and (min-width: 500px){} 
      * .notice{display: flex;}
      * 이 경우 500px에도 적용되니 501px로 설정하는 것이 정확하다.
    + Media Query
      * 대충 찾아봤을 때, 다양한 조건을 걸어서 CSS를 적용시킬 때 사용하는 것 같다.
      * screen은 PC 화면, print는 출력화면 등으로 나누어서 보고 and, not, or(,), only 등으로 조건을 걸 수 있고, 조건 안에 조건을 중첩해서 넣을 수도 있다.
      * screen, print 등의 1차적?인 부분 외에 min-width 등의 속성을 넣을 대는 괄호안에 넣어줘야 한다.
      * 우리가 쓰는 screen and (min-width)의 경우, 사용자가 화면에서 사용하고(screen and) 최소 폭이 550px이상일 때(min-width)라는 뜻으로 볼 수 있다.
      * 어차피 화면으로 보고 있기 때문에 screen을 지워도 정상 작동한다.
  - 참고 링크
    + [@media MDN](https://developer.mozilla.org/ko/docs/Web/CSS/@media#mf-name) 
    + [Media Query MDN](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Media_queries#%EA%B5%AC%EB%AC%B8)

#### #3-6 Publishing on Github Pages
  - front-end로만 구성된 이번 project를 github에서 웹사이트 화 시킬 수 있다.
  - branch를 하나 따서 project를 올리는 것인데, 이 때 꼭 branch명을 'gh-pages'로 지어야함.
- 