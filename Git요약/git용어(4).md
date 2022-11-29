### :red_circle: FAST FORWARD MERGE

가장 기본적인 MERGE는 FAST FORWARD MERGE다. FAST FORWARD MERGE는 현재 브랜치의 HEAD가 대상 브랜치의 HEAD까지로 옮기는 MERGE다.

FAST FORWARD MERGE는 다음 명령어를 통해 가능하다.

$ git switch [현재브랜치]

$ git merge [대상 브랜치]

## :red_circle: FAST FORWARD 의 한계점

FAST FORWARD 는 중간에 변경이 없을 때만 동작한다, 만약 중간에 다른 커밋이 껴있고, 해당 커밋이 같은 부분을 수정했다면 충돌이 일어나 제대로 동작하지 않는다.

## :red_circle: 3-WAY-MERGE

3way 병합은 복잡한 병합을 처리할 수 있는 방법이며, 여러 개발자와 협업으로 작업하는 경우 대부분 이 방법을 사용함.

브랜치 모양이 갈라지는 형태로 나뉠 때는 Fast-Forward 방식의 알고리즘을 적용하여 병합할 수 없음. 이 때 사용하는 방법이 3-way 방식.

2개의 브랜치를 병합하려면 공통 커밋을 찾아야 함. 이 공통 커밋을 공통 조상 커밋이라고 함. 공통 조상 커밋을 포함하는 브랜치와 새로운 두 브랜치, 세 개의 브랜치를 하나로 병합하는 과정에서 브랜치가 3개 있기 때문에 3-way 병합이라고 함.

### :red_circle: Rebase

Git에서 한 브랜치에서 다른 브랜치로 합치는 방법으로는 두 가지가 있다. 하나는 Merge 이고 다른 하나는 Rebase다

$ git rebase main

- topic 브랜치의 모든 커밋들  main 브랜치 이후에 추가

- Rebase는 히스토리가 선형으로 단순함.

- 원래의 커밋 이력이 변경됨.

## :red_circle: Rebase 의 위험성

Rebase가 장점이 많은 기능이지만 단점이 없는 것은 아니니 조심해야 한다. 그 주의사항은 아래 한 문장으로 표현할 수 있다.
