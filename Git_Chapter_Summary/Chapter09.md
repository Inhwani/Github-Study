# 9.1 되돌리기

깃을 사용하면 언제든지 원하는 시점으로 전체 코드를 되돌릴 수 있음.

# 9.1.1 다시 시작.

깃에서 코드 작업을 되돌리는 방법은 reset과 revert 두 가지 임

# 9.2 리셋

리셋은 커밋을 기준으로 이전 코드로 되돌리는 방법으로, 기록한 커밋을 취소함.

커밋을 취소하는 만큼 리셋시 신중하게 작업해야 함.

# 9.2.1 복귀시점

복귀는 어떤 시점으로 돌아가는 것을 의미

따라서 복귀 시점을 알려줘야 함.

리셋은 이 시점을 커밋을 기준으로 정함

커밋 메시지는 특정 시점을 파악하는 데 매우 좋음.

```
$ git reset --hard HEAD^^^
```

# 9.2.2 reset 명령어

reset 명령어를 사용하면 지정된 커밋 코드로 되돌아감.

```
$ git reset 옵션 커밋 ID
```

# 9.2.3 soft 옵션

soft 옵션은 가장 낮은 단계의 리셋 동작. 

soft 옵션은 파일을 수정하고, add 명령어로 스테이지 영역에 올려 커밋을 실행하기 직전의 단계로 되돌림.

soft 옵션은 단순히 HEAD 위치를 이동하는 역할.

# 9.2.4 mixed 옵션

```
$ git reset 커밋 ID --- 생략가능
```

mixed는 기본 옵션임

리셋한 후 스테이지 상태까지 복원하지 않고

mixed 옵션은 스테이지 상태를 제외하고 복원하기 때문에 Unstaged 상태가 되어 메시지가 빨간색으로 표시됨.

커밋하려면 add 명령어를 먼저 실행해야 함.

# 9.2.5 hard 옵션

hard 옵션은 가장 강력한 옵션임.

hard 옵션은 리셋되는 복귀 시점의 커밋 상태와 해당 커밋의 워킹 디렉터리까지 모두 되돌림

즉, reset --hard 명령어를 사용한 커밋 이후의 모든 내용은 모두 삭제됨.

hard 옵션을 사용하면 워킹 디렉터리 내용도 함께 삭제됨.

# 9.2.7 커밋 합치기

앞에서는 리베이스 병합의 -i 옵션을 사용하면 여러 커밋을 하나로 합치는 동작을 수행할 수 있음

단일 커밋은 커밋 명령어의 --amend 옵션으로 커밋 수정 가능.

# 9.2.8 스테이지 리셋

스테이지 영역에 등록할 때는 add 명령어

```
$ git add 파일이름
```

add 명령어로 등록된 스테이지 영역의 파일을 다시 unstage 상태가 되도록

```
git reset 파일이름
```

파일 이름을 지정하여 리셋하면 해당 파일은 unstage 상태가 됨

```
$ git reset --mixed HEAD 파일이름
```

# 9.2.9 작업 취소

수정 작업을 완전히 취소하려면 워킹 디렉터리와 스테이지 상태를 모두 제거하여 마지막 커밋 상태로 되돌려 놓아야 함.

리셋할 때의 시점을 현재 HEAD를 기준으로 하면 해당 시점의 수정 작업을 모두 삭제할 수 있음.

# 9.3 리버트

깃은 커밋의 버전을 되돌릴 수 있는 다른 방법인 리버트를 제공함.

리버트와 리셋 차이점은 커밋 정보 삭제 여부

# 9.3.1 취소 커밋

리버트는 기존 커밋을 남겨 두고 취소에 대한 새로운 커밋을 생성

취소 커밋을 생성할 때는 revert 명령어를 사용함.

# 9.3.2 리버트 지정

리버트는 한 번에 커밋 하나만 취소할 수 있음

```
$ git revert 커밋 ID
```

# 9.3.4 qudgkq cnlt

리버트를 이용하여 병합한 커밋을 취소할 수 있음

리셋은 방금 전 실행한 병합만 삭제함

리버트는 시간이 지난 후에도 과거의 병합을 선택하여 취소할 수 있음.

```
$ git revert --mainline 숫자 병합커밋ID
```
리버트로 병합을 취소할 때는 mainline 옵션을 같이 사용.