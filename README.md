# kakao-clone
 nomadcoder kakao-clone coding

 Kakao Desktop App clone

# Object
  - HTML, CSS 개념을 숙지하고 카카오톡 클론 코딩을 진행한다.

# History
#### 2019.12.27: 기본공지, #1-1 ~ #1-6
#### 2019.12.30: #1-7

  
# Concept
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