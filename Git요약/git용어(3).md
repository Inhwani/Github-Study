### :red_circle: BRANCH의 개념

여러 개발자들이 동시에 다양한 작업을 할 수 있게 만들어 주는 기능

각자 독립적인 작업 영역 안에서 마음대로 소스코드를 변경

### :red_circle: CHECKOUT의 개념

체크아웃은 크게 두가지 기능을 합니다.

- 브랜치 혹은 커밋 전환
- 내용 되돌리기

$ git checkout branch name

특정 브랜치로 이동하기

$ git checkout -b (new branch name)

특정 브랜치 생성 후 해당 브랜치로 이동

$ git checkout .

모든 변경 사항을 취소하는 것

### :red_circle: SWITCH의 개념

switch는 checkout에서 브랜치를 변경하는 부분만 담당한다.

이전에는 git checkout <branch_name>으로 브랜치를 변경했다.

하지만 이젠 switch로 변경한다

$ git switch [name]

