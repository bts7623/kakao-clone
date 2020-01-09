# kakao-clone
 nomadcoder kakao-clone coding

 Kakao Desktop App clone

# Object
  - HTML, CSS 개념을 숙지하고 카카오톡 클론 코딩을 진행한다.

# History
#### 2019.12.27: 기본공지, #1-1 ~ #1-6
#### 2019.12.30: #1-7 ~ #3-3
#### 2020.01.08: #3-4 ~ #3-6
#### 2020.01.09: #3-7

  
# Concept
### Module #1 The tools of a Web Developer
#### #1-1, #1-2
  - Visual Studio Code 관련 Extensions 추가
    + prettier: setting > format on save 체크박스 클릭 > 저장 시 자동으로 코드 배열이나 세미콜론 체크해줌
    + Material Theme > VSC 테마스킨
    + Material Icon Theme > VSC 파일확장자에 따른 아이콘 테마

#### #1-3, #1-4
  - Git: 소스파일의 변경 내역을 추적하는 것
    + 소스 변경 후 PC 혹은 클라우드에 푸쉬해서 저장하고 공유할 수 있음
  - Version Control
    + Repositories: 소스코드를 저장하는 폴더(Git은 그것을 추적하는 시스템)
    + Commits: 파일 변경 기록함!
    + Branches: 나무가지 / default는 master branch
      * master branch를 복사해서 하나의 새로운 환경을 만들어서 새로운 기능을 테스트한다고 보면 됨.
      * master branch는 실 사용자들이 이용하고 있고, branch를 따서 새 기능을 테스트 한 뒤 문제가 없을 시 master와 합친다.
      
#### #1-5, #1-6
  - Git vs Git Hub
    + Git: 코드의 변경사항 추적 > 코드가 언제, 어떻게, 누구에 의해서 변경되었는지 기록하는 것.
    + GitHub: 이런 변경사항들을 클라우드에 올리는 곳
      * 비슷한 플랫폼으로 Bitbucket이 있다.
    + GitHub Desktop: GitHub에서 만든 desktop 설치버전
    + console로도 Git을 이용할 수 있고 빠르지만 접근성이 낮아 숙련도가 필요하다.

#### #1-7
  - GitHub Repository
    + GitHub Desktop에서 Repository를 생성하면 GitHub에도 생성됨
    + Repository 설정 시 local Path를 원하는 곳에 잡아줌.(Default 문서\GitHub)
  - GitHub Desktop Commit&Push
    + 해당 local Path에서 파일내용 변경 시 자동으로 GitHub Desktop에 실시간으로 변경사항이 표기됨
    + 현시점까지 변경된 모든 사항을 한번에 Commit할 수 있으며 Local master branch에 update가 됨.(GitHub 올라가는거 아님)
    + Commit을 하면 우측 상단을 통해 Push할 수 있으며, Push하면 GitHub에 Commit 내용이 반영됨.

#### #1-8
  - HTML, CSS 둘 다 프로그래밍 언어가 아니다.
    + HTML, CSS 둘의 상호보완으로 페이지가 구현됨
    + HTML은 브라우저에게 각 요소가 무엇인지 설명하고, CSS는 각 요소의 색상, 크기, 배경은 어떠한지 등을 설명함
  - HTML: Hyper Text Markup Language
    + Mark-Up: 밑줄을 긋다.
    + HTML은 널부러져있는 소스코드들을 어디가 무엇을 나타내는지 표기, 마킹하는 언어. 여기서부터 여기까지는 타이틀, 여기서부터 여기는 링크. 들 각각 무엇인지 알려주는 언어이다.
  - CSS: Cascading Style Sheet
    + cascade: 폭포수, 계단식
    + 각각의 요소가 어떻게 생겼는지 정의하는 것
      * 색상, 크기, 배경 등

---
### Module #2 HTML5
#### #2-1, #2-2 #2-3
  - HTML: tag가 많은 text문서, 표기하고 강조하는 언어
  - index.html
    + 웹 서버들이 index파일을 제일 먼저 찾도록 설계되어 있음.(Default 값)
  - <tag> 태그
    + <이름 속성="값">내용</이름> 형식으로 쓰임
    + <name attribute="value">Content</name>
    + <a>의 attribute로 target="_blank"해주면 새창으로 이동한다.

#### #2-4
  - <!DOCTYPE html>: 구글 크롬이 이 문서가 html임을 인식하게 해줌.
    + 따로 닫는 태그 </>가 없는 것: self-contained tag
    + self-contained tag는 그 자체로 정보를 제공하기 때문에 닫는 태그가 없다.
  - html은 head, body로 나뉘며 꼭 닫아줘야 브라우저가 인식함
    + head는 일반 사용자에게 보이지 않고 브라우저에게 정보를 줌
  - 기본 tag
    + head 태그와 header 태그는 엄연히 다름
      * head invisible: 브라우저 데이터를 저장하는 곳
      * header visible: 머릿말을 표기하는 곳
    + head > title
      * 해당 html의 title을 정해줌. 탭의 이름.
    + body > h1 ~ h6
      * 굵은 글씨로 써줌
  - 갑자기 튀어나온 Awesome Useful Google Chrome Extensions
    + [colorZilla](https://chrome.google.com/webstore/detail/colorzilla/bhlhnicpbhignbdhedgjhgdocnmhomnp?hl=en)
    + [Page Ruler](https://chrome.google.com/webstore/detail/page-ruler/emliamioobfffbgcfdchabfibonehkme?hl=en)

#### #2-5
  - meta tag: 추가 정보, 엑스트라
    + meta 정보는 사용자가 아닌 브라우저를 위한 정보로 모두 head에 적는다.
    + 사용자가 보는 Contents는 모두 body에 적는다.
    + charset: Character encoding
      * 해당 언어로 아래 코딩을 인코드하겠다는 정보. utf-8사용
    + name = author, description 등 다양한 meta tag가 있다.
      * author: 작성자
      * description: 내용. >> 구글링 시 해당 웹페이지에 대한 부가설명, 간략한 설명글
  - 참고 링크
    + [Special tags that Google understands](https://support.google.com/webmasters/answer/79812?hl=en)
    + [The Document-level Metadata element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta)

#### #2-6
  - Semantic Tag: 의미 있는 태그
    + 단순히 공간 할당이 아닌 태그 자체에 의미가 있는 것들을 나타내는 듯
      * 제목, 문단, 네비게이션 등 뭔가 뜻이 있는 태그
      * 검색해보니 태그 자체에 엄청난 의미나 기능이 있는 것이아니고 페이지 레이아웃을 스타일링 할 수 있는 태그를 임의로 정의해서 쓰는 것.
      * 해당 태그들은 검색 엔진의 컨텐츠 식별에도 도움을 줌
      * HTML5에서 태그가 추가됨
    + h tag
    + section: 부분
    + article: 항목
    + header, footer: 머릿글, 바닥글
  - Non Semantic Tag: 의미 없는 태그. 아무 지칭하는 바가 없는 태그
    + div > division: 분할정도의 뜻으로 의미 없음
      * 단순히 박스나 컨테이너가 필요할 때 쓰는 태그
    + span: 짧다는 뜻으로 타이틀인지 문단인지 알 수 없음
      * 텍스트를 위한 컨테이너가 필요할 때 쓰는 태그
  - 참고 링크
    + [Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)
    + [HTML5 Migration](https://www.w3schools.com/html/html5_migration.asp)

#### #2-7
  - tag들은 id와 class를 이용해서 구분할 수 있다.
  - id는 element 당 1개(고유), class는 반복될 수 있다(동일 속성 부여).
  - id는 고유하기 때문에 고유한 부분에서만 사용
  - 대부분의 서비스들은 동일한 폼의 반복이기 때문에 class를 이용해서 속성을 부여
    
#### #2-8 
  - Recap: recapitulation 요약, recapitulation 개요를 말하다.

---
### Module #3 CSS3
  - #3 CSS3 Part는 해당 강좌 소스파일을 통째로 올려줘서 그것을 Commit하고 강좌를 들으면서 진행하는 연습은 그 때 그 때 파일을 생성하고 지우고 하면서 진행함.

#### #3-1, #3-2
  - How to mix our CSS with our HTML
  - CSS의 구성
    + selector(id, class, tag name){property}
    + selector: 대상 지정
      * h1{ property }
      * property 개수의 제한은 없음
      * 모든 tag를 대상으로 지정할 수 있음
      * id, class를 대상 조건에 포함할 수 있음
        = 태그 tag
        = 클래스 .class
        = 아이디 #id
    + property: 속성 값 부여
      * property-name: value;
      * 공백없음(띄어쓰기 안됨), 세미콜론 필수

#### #3-3
  - Mixing CSS with HTML
  - html 파일 만들고 "html:5" 쓰고 "Enter" 치면 기본 폼이 쫙 깔림
  - CSS HTML에 적용하는 법
    + inline > 내부 삽입(안좋음)
      = html 소스 내부에 style 태그를 삽입하여 CSS 작성하는 법
      = 페이지 이동하면 CSS가 다 풀려서 페이지별로 스크립트를 삽입해줘야 해서 좋지 않다.
      = 스타일시트 만들어서 떙겨오기
    + 별도의 css파일 만들어서 html 문서 head에 연결하기
      * 연결된 모든 html에 css가 적용됨
      * 유지보수가 편리함
      * head 태그 내부 최 하단에 link 걸기
      ```javascript
        <head>
            <link href="style.css" rel="stylesheet">
        </head>
      ```

#### #3-4 Box Model
  - element들은 다 Box구조로 구현된다.
  - 크게 4가지(Content, Padding, Border, Margin)로 구분된다.
    + Content(내용): 내용이 들어가는 부분
    + Padding(내용↔경계): 내용과 박스 경계 사이 간격
    + Border(경계): 박스 경계
    + Margin(경계↔바깥): 박스 경계와 바깥 요소 사이 간격
  - 자동완성 명령어(아직 안알랴줌 > Ctrl+Space+Enter 같음)
    + default로 div로 생성되고, 시작을 span으로 하면 쭉 span으로 생성
      * name1#name2.name3
        = id가 name2, class가 name3인 name1 tag
      * 명령어>명령어: 부모관계
      * 명령어+명령어: 같은depth
      * 명령어*n: n개의 tag 생성
      * 명령어{$}*n: 1~n까지 입력된 n개의 tag
    + 예시
      * tag>tag.class+tag#id 형식
      * article>h2.articleheader2+h4#arth4
      ```html
      <article>
          <h2 class="articleheader2"></h2>
          <h4 id="arth4"></h4>
      </article>
      ```
      * tag name없이 id, class만 입력 시 div로 생성
      * .name>.name2+.name3+.name4>.name5
      ```html
      <div class="name">
         <div class="name2"></div>
         <div class="name3"></div>
         <div class="name4">
              <div class="name5"></div>
         </div>
      </div>
      ```
      * span으로 시작 시 나머지는 span으로 생성됨
      * span.name>.name2+.name3+.name4>.name5
      ```html
      <span class="name">
          <span class="name2"></span>
          <span class="name3"></span>
           <span class="name4"><span class="name5"></span></span>
       </span>
      ```
  - padding, margin 설정
    + top, bottom, right, left가 있음
      * padding-top: 50px; 
      * margin-right: 30px;
    + 단축키
      * padding: 50px; //상하좌우 50px
      * padding: 20px 30px; //상하 20px, 좌우 30px
      * padding: 10px 20px 30px 40px; //상 10px, 우 20px, 하 30px, 좌 40px
        * 시계방향
    + 구글크롬 개발자모드(F12, 화면 우클릭 검사)에서 적용사항 확인 가능
  - border
    + 폭(border-width), 스타일(border-style), 색상(border-color)
      * 스타일을 지정하지 않으면 표기되지 않음
      * border-width: 5px;
      * border-style: dashed;
      * border-color: red;
    + 단축키(border: width style color;)
      * border: 5px dashed red;
      * 순서 바뀌어도 상관 없는듯 하지만 위 순서로 고정하자
    + border-style
      * border도 padding, margin처럼 상하좌우로 스타일을 설정할 수 있다.
        * 1: 상하좌우, 2: 상하/좌우, 3:상/좌우/하, 4:상/우/하/좌
      * border에 width style color 한번에 쓸 때는 적용이 안된다.
      * [참고링크](https://developer.mozilla.org/ko/docs/Web/CSS/border-style)

#### #3-5 Inline vs Block vs Inline Block
  - Display
    + block(default): 가로 전체를 차지하며 옆에 다른 element를 둘 수 없다.
    + inline-block: 옆에 다른 element를 둘 수 있다.
    + inline: block의 형태를 잃는다. width, height 속성 값을 없애고 입력된 데이터의 크기만큼만 표기된다.

#### #3-6 Position property
  - Position
    + static(default): 입력된 그 위치에 그대로 있음.
      * 스크롤 내리면 위로 올라가서 사라짐
    + fixed: 눈에 보이는 그 자리에 고정되어 있음. 오버랩 되어 고정됨. 계속 보임.
      * 스크롤 내려도 사라지지 않고 그자리에 고정되어 보임
      * 상하좌우 간격 설정 가능
        * top OR bottom //top: 10px하면 최 상단에서 10px 떨어져서 고정되어 있다. bottom과 개념이 겹쳐서 둘 중 하나만 씀
        * left OR right //left: 50% 등 %로도 작성가능하다.
    + absolute: 상응하는 부모관계에 고정됨
      * fixed와 마찬가지로 top/bottom, left/right로 위치 조절 가능하지만 매칭되는 부모박스가 없으면 body를 기준으로 고정됨
      * 성능 자체는 static과 같고, 부모박스 내부 특정 위치에 element를 고정시키고 싶을 때 사용하는듯
      * position: relative; 박스를 부모관계로 인지하고 해당 박스 내부에 상대적으로 위치함
    + relative: absolute와 매칭되는 부모 박스
    + absolute, relative 관계는 1:多가 가능하다.
      * html tag 내에서 부모자식 관계를 갖고 있어야 한다.
      * 별도의 relative-1, relative-2, absolute-1, absolute-2 등의 매칭을 하는 것이 아니다.
      * 모두 relative와 absolute로만 position을 설정 하며 absolute position을 가진 box들이 html tag 내에서 부모로 있는 tag에 relative가 있으면 가서 달라 붙고 없으면 body에 붙는 것이다.
      * .A>.B (div A가 부모, div B가 자식인 형태)일 때 div B position이 absolute고 div A가 relative여야만 가서 붙는다.
      * .A+.B (div A와 div B가 부모자식 관계없이 놓여있는 형태)일 때 div B position이 absolute고 div A가 relative여도 div B는 div A에 안붙고 body에 붙는다.
  - 기타
    + [참고링크](https://www.w3schools.com/cssref/pr_class_position.asp)

#### #Day3 Code Challenge
  - 첫 코드 과제인데 실패함.
  - 코드 과제들은 code_challenge folder에 기록함.
  - 문제 원문(따로 복사를 못해둠 기억나는대로 기입)
    + red bar는 스크롤해도 그 자리에 있어야 한다.
    + blue box의 글은 50px 안에 있어야 한다.
      * This is the day one (color: white)
    + yellow box는 회색 테두리를 가져야 한다.
    + green box는 red, blue, yellow 중간에 있어야 한다.
  - Q&A
    + 상단 부 공간을 비우고 blue, yellow를 red선에 맞게 위치 시키는 것이 어려웠음
      * body에 padding을 줘서 해결
    + blue, yellow를 display: inline-box를 해도 옆에 안오고 위아래로 틀어짐
      * vertical-align: top;을 통해 윗단에 라인을 맞춤
    + green box를 올리는데 나는 position: fixed;를 body에 붙여서 진행하다보니 위치가 이쁘게 안나왔음.
      * yellow-box에 붙이고 top, left에 음수 값을 넣는 것이 포인트
    + z-index 빼고 다 구현 시 depth가 green>yellow>red>blue 순이었다.
      * z-index로 순서 정렬
  - 구현 방식 배워야할 점
    + red-bar를 nav tag로 구현했길래 뭐지? 하고 봤는데 nav가 목차 만들 때 주로 쓰는 태그이고 red-bar 형태가 목차이다 보니 div보다 nav로 구현한듯.
    + blue, yellow를 box라는 공통 class로 구현하고 blue, yellow class를 각자 부여해서 추가 설정을 함.
    + z-index로 red-bar, yellow-box, green-box의 depth를 정함
    + body padding, margin을 0을 줘서 초기화 시킴
  - z-index
    + position 속성을 이용하여 요소를 겹칠 수 있는데 이 때 요소들의 수직 위치를 정하는 속성
    + 숫자가 클 수록 위로 올라오고 작을 수록 아래로 내려감
      * 코드 상 나중에 입력한 것이 위로 올라옴
    + default값은 auto이며 기본 0으로 취급한다.
    + 자식 tag에 z-index를 아무리 높여도 부모 z-index가 낮으면 자식 tag는 부모 값을 따라간다.
    + 부모 z-index가 default고 자식만 z-index가 있으면 위로 올라올 수 있다.
      * red: 1, yellow: 0, green: 2를 해도 green이 부모인 yellow를 따라 0이되어
        red 아래에 깔림
      * red: 1, yellow:defualt(auto), green: 2를 하면 green이 red 위에 올라옴
  - 참고 링크
    + [nav tag](https://developer.mozilla.org/ko/docs/Web/HTML/Element/nav)
    + [z-index](https://developer.mozilla.org/ko/docs/Web/CSS/z-index)
    + [vertical-align](https://developer.mozilla.org/ko/docs/Web/CSS/vertical-align)

#### #3-7 Fluid layouts with Flexbox
  - display: inline-block;의 box가 다수 있을 경우 width값을 넘어가면 줄바꿈이 되어 내려오는데, 그 간격이 깔끔하지 않았다.
    + 이것을 해결하는 것이 Flex다.
  - display: flex;
    + display 속성의 하나 / display: flex;
    + children box에는 적용하지 않고 오직 부모 클래스에만 적용함
      * children에 display: inline-block; 처리를 안해도 inline-block 방식으로 출력 됨.
      * children box가 창을 줄여도 그 창에 맞춰서 폭이 조정됨. 
  - justyfy-content: property;
    + 행 정렬(수평)
      * 왼쪽: left
      * 오른쪽: right
      * 가운데: center
      * width 최대 값 기준으로 같은 간격 벌리기
        * 컨텐츠만: space-between // box가 양 끝에 붙음
        * 추변 간격 포함: pace-around // box와 양 끝 사이 간격이 있음
    + 단, flex-direction이 column이면 수직을 담당함
  - align-items: property;
    + 열 정렬(수직)
      * 위: flex-start
      * 아래: flex-end
      * 가운데: center
    + 단, flex-direction이 column이면 수평을 담당함
  - flex-direction
    + 자식 블럭을 가로로 쌓을지 세로로 쌓을지 정할 수 있음
    + column, column-revers: 세로
    + row(default), row-revers: 가로
  - flex-wrap
    + box들이 폭을 줄이지 않고 줄바꿈 되도록 설정
    + nowrap(default): 줄바꿈 되지 않고 창 크기에 맞게 크기가 줄어듦
    + wrap: 크기를 유지한채로 창 크기가 줄으면 줄 바꿈이 됨
  - 자식 box에 display: flex;하면 자식 box 내부의 text 등의 컨텐츠를 정렬할 수 있다.(움직일 수 있다.)
  - 참고 링크
    + [practice flexbox](http://flexboxfroggy.com/#ko)

#### #3-8 CSS Selectors and Pseudo Selectors
  - Pseudo Selectors(가상 셀렉터)
  - 기존의 class 명을 입력해서 CSS를 적용하는 것이 아닌 tag type을 입력해서 CSS를 적용하는 방법 → `html tag, id, class 사용 없이 CSS 적용하는 법`
  - tag 내부 property 
    + ex_input[type='submit']{background-color: red;}
    + input{border: 1px solod grey;}
  - .class:propery{}
    + last-child
      * .box:last-child{}
        * box 클래스의 가장 마지막 박스를 선택한다.
    + first-child > 가장 첫 박스
    + nth-child(n) > n번째 박스
      * nth-child(3) 3번쨰 박스 선택
    + nth-child(2n) > 2n번째 element를 선택
      * .box:nth-child(2n){background-color: red;} > 2, 4, 6.., 2n 번째 박스를 red로 칠함
      * 3n, 4n, 2n+1, 3n+1, 3n+2 등으로 응용 가능
  - input > .box{}
    + direct child, 직계라는 뜻
    + 그 밑에 다른 박스들이 있다면 그 박스들에는 해당되지 않음
      * .box{color: red;} / input > .box{color: green;} 설정이 있을 때
        * input tag 직계 하위 .box의 text는 green을 띠게 된다.
    + .class1 > .class2 등 응용 가능
  - input + .box{}
    + 형제관계: 동등선상에 있는 것을 선택
    + input tag와 직계 관계 없이 나란한 .box는 위 설정을 따름
  - 참고 링크
    + [nth-test](http://www.topdesignagencies.com/nth-test/)

#### #3-9 Element States with CSS
  - CSS States