### :red_circle: 클론의 개념
: 원격 저장소를 지역 저장소에 복제 (공개된 저장소는 소유와 관계 없다)

명령어 

$ git clone 저장소 주소 [저장소 폴더명]

### :red_circle: PUSH의 개념

$ git push origin master

현재 폴더를 그대로 업로드 하는 것이 아니라, 지금까지의 이력/버전(commit)을 push 하는 것이다.

Working directory, Staging area의 변경사항들은 원격저장소로 push 되지 않는다.

따라서, push 전에 $ git status , $ git log 를 통해서 확인하는 습관을 가져야합니다.

### :red_circle: PULL의 개념

$ git pull origin master

원격저장소 변경 사항(이력)을 받아옵니다.

다른 작업 환경이나 위치에서 작업할 때, 혹은 공동 작업에서 타인이 commit해서 이력이 변경되었을 경우 등의 경우가 있습니다. 따라서, pull을 통해서 가져온 후, 작업을 진행하는 것이 좋습니다

### :red_circle: FETCH의 개념

원격 저장소로부터 필요한 파일을 다운

지역 브랜치는 원래 가지고 있던 지역 저장소의 최근 커밋 위치를 가리키고, 원격 저장소는 가져온 최신 커밋을 가리킨다
