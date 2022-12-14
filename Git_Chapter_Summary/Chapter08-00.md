# 8.1 병합

브랜치를 생성하는 목적은 원본 코드에 영향을 주지 않고 분리하여 개발하기 위해서

분리된 브랜치를 한 브랜치로 합치는 작업을 병합이라고 함.

# 8.1.2. 깃으로 자동 병합

복잡한 수정 내역을 순차적인 시간에 다라 병합하는 것은 쉬운 일이 아님.

깃의 자동 병합은 원본을 기준으로 두 파일의 변경 이력을 비교함.

변경된 파일 내용이 발견 되면 자동으로 수정된 코드 내용을 병합함.

깃의 병합은 브랜치를 기준으로 함.

병합하고자 하는 브랜치는 같은 로컬 저장소에 있어야 함.

충돌이란 아무리 좋은 도구라도 자동으로 반영하지 못하는 것들이 있음 이를 뜻함.

# 8.1.3 병합 방식

깃의 병합은 브랜치를 기반으로 실행함.

각 브랜치를 비교하여 자동 병합하는 형태임

따라서 병합하려면 브랜치를 만들어 브랜치 안에서 수정 작업을 해야 함.

깃에서 충돌 없이 병합하려면 FAST-FORWARD 병합, 3-WAY 병합 방식을 선택함.

# 8.2 FAST-FORWARD 병합

깃의 가장 간단한 브랜치 병합은 FAST-FORWARD 방식임

브랜치가 생성된 커밋에 따라 순차적으로 분기됨

커밋에맞추어 병합을 처리하는 방법이 FAST-FORWARD 병합.

# 8.2.2 병합 위치

깃의 merge 명령어는 브랜치를 병합함.

merge 명령어는 현채 브랜치를 기준으로 다른 브랜치의 모든 커밋을 병합함.

```
$ git merge 브랜치이름
```

브랜치 병합시 기준과 대상이 있어야 함.

기준은 체크아웃된 현재 브랜치임.

# 8.2.3. FAST-FORWARD 병합 적용

커밋 작업은 분기된 feature 브랜치에서 모두 수행했음. main 브랜치에는 추가된 커밋이 없음

이 두 브랜치를 FAST-FORWARD 방식을 사용하여 병합했다면

main 브랜치의 마지막 커밋 위치와 feature 브랜치의 마지막 커밋 위치가 같음

동일한 HEAD 포인터를 가지게 됨.

FAST-FORWARD 병합은 작업한 브랜치를 원본 브랜치에 병합할 때 

작업한 브랜치의 시작 커밋을 원본 브랜치 이후의 커밋으로 가리킴.

# 8.3 3-WAY 병합

3-WAY 병합은 좀 더 복잡한 병합을 처리할 수 있는 방법.

# 8.3.3 공통 조상

브랜치 모양이 갈라지는 형태로 나뉠 때는 3-WAY 방식을 이용해야 함

두 브랜치를 병합하려면 분할 기준인 공통 커밋을 찾아야 함.

이를 공통 조상 커밋이라고 함.

공통 조상 커밋을 포함하는 브랜치와 새로운 두 브랜치, 이렇게 3개를 하나로 병합해야 함

브랜치가 3개 있다고 해서 3-WAY 병합 이라고 함.

# 8.3.4 병합 커밋

3-WAY 병합은 두 브랜치에서 공통 조상 커밋을 자동으로 찾아줌.

병합을 성공적으로 완료한 후에는 새로운 커밋을 추가로 하나 생성함.

새로 생성된 커밋을 병합 커밋이라고 함.

병합 커밋은 부모 커밋이 2개라는 특징이 있음.

# 8.3.5 병합 메시지

3-WAY 병합을 할 때 새로운 병합 커밋이 생성됨.

3-WAY 병합은 병합 메시지가 필요함.

병합한 후에 새로운 커밋을 하면서 동시에 메시지를 자동 생성함.

```
$ git merge 브랜치이름 --edit
```
자동으로 작성되는 메시지 외에 직접 커밋 메시지를 작성하는 명령어.

# 8.4 브랜치 삭제

브랜치를 병합한 후에는 병합한 브랜치를 어떻게 관리할지 결정해야 함.

# 8.4.1 병합 후 삭제

병합된 브랜치의 커밋은 모두 원본 므랜치에 적용됨.

따라서 중복되는 커밋을 가지는 별도의 브랜치를 유지할 필요는 없음

```
$ git branch -d 브랜치이름
```
불필요한 브랜치는 삭제

-d 옵션은 병합을 완료한 브랜치만 삭제 가능

병합을 완료하지 않은 브랜치를 삭제하고 싶다면 -D 옵션 사용.
