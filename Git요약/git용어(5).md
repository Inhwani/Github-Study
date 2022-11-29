### 🔴 RESET

- 리셋은 커밋을 기준으로 이전 코드로 되돌리는 방법입니다.

- 또한 기록한 커밋을 취소합니다.

$ git reset 옵션 커밋 ID

옵션 세가지

- soft: 스테이지 영역을 포함한 상태로 복원

$ git reset --soft HEAD~ 

- mixed: 기본 옵션 값은 mixed이다. reset 명령어를 사용할 때 옵션을 지정하지 않으면 기본값 mixed로 선택

$ git reset --mixed 커밋ID

- hard: 실제 파일이 삭제된 이전 상태로 복원

$ git reset --hard HEAD~

### 🔴 REVERT

공개된 저장소에서 이전 상태로 되돌리기 위해 리버트를 사용한다

리셋과의 차이점은 커밋 정보 삭제 여부에 있으며, 리버트는 기존 커밋을 남겨 두고 취소에 대한 새로운 커밋을 생성한다.

🔴 직전 커밋이 아닌 다른 커밋을 취소할 때

$ git revert 커밋ID

