## 4.4.3 파일 상태와 커밋

_______________________________________________________________________________________

반드시 tracked 상태로 변경해야 커밋이 가능함.

tracked 상태인 파일을 수정하면 다시 modified 상태로 변경됨.

modified 상태의 파일은 반드시 ADD 명령어로 다시 Staging Area에 재등록 해야 함.

```
$ git commit
```

수정된 파일 이력을 커밋하는 명령어.
- 독립적으로 사용 가능
- 옵션을 추가하여 여러 동작을 같이 수행 가능
- --help 명령어 입력시 옵션 확인 가능

깃의 커밋은 HEAD와 Staging Area 영역 간 차이를 비교하여 새로운 객체를 생성.

## 커밋 메세지

커밋은 변경된 파일 차이를 깃 저장소에 기록, 구별하는 메시지를 같이 작성 해야함

이를 커밋 메시지라고 함.

커밋은 파일 이름을 여러 개 사용하지 않고 하나만 가짐.

모든 커밋은 반드시 커밋 메시지를 작성해야 함.

## 파일 등록과 커밋을 동시에 하는 방법

커밋을 하려면 반드시 Working Directory를 정리해야 함.

ADD 명령어로 추가되거나 수정된 파일들을 Staing Area에 등록 해야함.

```
$ git commit -a
```

위의 두 가지를 한 번에 해결할 수 있음

 커밋을 하기 전 자동으로 모든 파일을 등록하는 과정을 미리 수행
 
 _______________________________________________________________________________________
 
 ## 4.5 커밋 확인
 
 ## 4.5.1 스테이지 초기화
 
 ```
 $ git status
 ```
 
 터미널에서 Status 명령어를 실행해서 상태를 확인한다.
 
 Working Tree clean 메시지를 확인 가능하다.
 
 커밋을 하면 Staging Area 영역은 초기화된다.
 
 _______________________________________________________________________________________
 
 ## 4.5.2 로그 기록 확인
 
 ```
 $ git log
 ```
 
 깃은 커밋 목록을 확인할 수 있는 log 명령어를 제공함
 
 log 명렁어는 시간 순으로 커밋 기록을 출력함, 내림차순으로 나열함.
 
 _______________________________________________________________________________________
 
 ## 4.6 두 번째 커밋
 
 ## 4.6.1 파일 수정

_______________________________________________________________________________________

index.htn 파일을 수정하여 간단한 인사말을 넣습니다.

_______________________________________________________________________________________ 
 ## 4.6.2 파일 변경 사항 확인

_______________________________________________________________________________________

git status 명령어 입력시 modified : index.htm 메시지가 출력됨.

_______________________________________________________________________________________ 
 ## 4.6.3 수정된 파일 되돌리기

_______________________________________________________________________________________
 
 파일을 수정하면 modified 상태로 변경됨. 
 
 하지만 잘못 수정할 수도 있음. 파일을 원상태로 되롤리려면 ?
 
 ```
 $ git checkout -- 수정파일 이름
 ```
 
 이전 커밋으로 되돌리는 명령어 이다.
 
 수정 파일을 되돌리면 이전 커밋 이후에 작업한 수정 내역은 모두 삭제함.
 
 _______________________________________________________________________________________

## 4.6.4 스테이지에 등록
 
 _______________________________________________________________________________________
 
 변경된 소스 코드를 커밋하는 것은 파일을 생성하고 등록하는 과정과 매우 유사
 
 - 기존 파일을 수정하면 파일은 modified 상태로 변경 
 - 그리고 Working Directory로 이동
 - 파일이 수정되면 Add 명령어로 Staging Area 영역에 재등록 해야함.
 - 즉 파일을 수정할 때마다 등록 작업을 반복 해야함.

```
$ git add 수정파일 이름
```

_______________________________________________________________________________________

## 4.6.5 두 번째 커밋

```
$ git commit -m "커밋 메시지"
```

커밋시 -m 옵션을 사용함.

```
$ git commit -am "커밋메시지"
```

-a 옵션은 Commit 명령어를 실행하기 전 Working Directory에서 Staging Area로 등록을 도와주는 명령어

-m 옵션은 커밋을 도와주는 명령어

커밋 옵션 -a와 -m을 동시에 사용시 등록과 커밋을 한 번에.

_______________________________________________________________________________________

## 4.6.6 두 번째 커밋 확인

_______________________________________________________________________________________

## 4.6.7 깃허브에서 확인

_______________________________________________________________________________________

## 4.7 메시지가 없는 빈 커밋

_______________________________________________________________________________________

커밋을 할 때 반드시 커밋 메시지를 같이 작성해야 함.

하지만 의미 없는 커밋이라 메시지를 생략하고 싶은 경우 이를 허용함.

_______________________________________________________________________________________

## 4.7.1 세 번째 커밋

_______________________________________________________________________________________

index.htm 파일을 우선 수정

그 이후 수정된 파일을 Staging Area에 재등록

터미널에서 메시지가 없는 빈 커밋을 작성하려면 --allow-empty-messeage 옵션을 사용

```
$ git commit --allow-empty-message -m ""
```

메세지가 없는 빈 커밋이 실행

_______________________________________________________________________________________

## 4.7.2 소스트리에서 빈 커밋

## 4.7.3 빈 커밋 확인

## 4.8 커밋 아이디

$ git log 명령어 사용시 갓 커밋에는 이상한 영문과 숫자가 있습니다.

이를 커밋 아이디라고 함.

커밋 아이디는 특정 커밋을 가리키는 절대적인 이름이고, 명시적 참조 값입니다.

## 4.8.1 SHA1

커밋 아이디가 이렇게 영어와 숫자로 된 이유는 SHA1이라는 해시 알고리즘을 사용하기 때문

40자리의 hexa 값으로 되어 있음. 이를 사용하는 이유는 충돌을 방지하기 위해서.

## 4.8.2 단축키

SHA1 해시키는 매우 복잡한 구성임.

40자리의 16진수로 입력하다가 잘못 입력할 가능성이 높음.

해시의 앞쪽 7자만으로도 중복을 방지하면서 전체 키 값을 사용할 수 있음.

## 4.9 커밋 로그

깃은 터미널 기반의 응용 프로그램임.

깃의 로그는 저장소 커밋 기록들을 확인 할 수 있음. 

또한 커밋 메시지, 아이디도 확인할 수 있고, 브랜치 경로 등을 분석할 수 있는 옵션들도 제공합니다.

## 4.9.1 간략 로그

커밋 메시지를 여러줄 작성했다면, 로그 정보를 복잡하게 느낄 수 있음

--pretty=short 옵션 사용시 첫 번째 줄의 커밋 메시지만 출력

```
$ git shw 커밋 ID
```

특정 커밋의 상세 정보도 확인 가능

## 4.9.2 특정 파일의 로그

전체 커밋과 달리 특정 파일의 로그 기록만 볼 수 있음 log 명령어 뒤에 파일 이름을 적으면 됨.

log 명령어의 옵션은 매우 다양함.

소스트리 이용시 log 명령어와 복잡한 옵션을 사용하지 않아도 쉽게 로그 흐름을 파악할 수 있는 장점 존재.

## 4.10 Diff 명령어

diff 명령어는 커밋 간 차이를 확인함

## 4.10.1 파일간 차이

깃의 장점은 수정 이력을 커밋이라는 형태로 구분할 수 있음.

커밋으로 파일들의 수정 내역을 추적함.

깃은 거밋을 기준으로 파일들의 수정 이력을 비교해 볼 수 있는 diff 기능을 제공합니다.

## 4.10.2 Working Directory vs Staging Area

add 명령어로 파일을 추가하지 않은 경우, Working Directory와 Staging Area 영역간 변경 사항을 비교 할 수 있음.

```
$ git diff ----- Working Directory vs Staging Area
```

이처럼 워킹 디렉터리 내용과 스태이지 내용의 차이점을 출력함.

변경 파일을 add 명령어로 추가하여 스테이지에 등록.

## 4.10.3 커밋 간 차이

Staging Area에 있는 수정된 파일을 아직 커밋하지 않았다면, 최신 커밋과 변경 내용을 비교하여 볼 수 있음.

HEAD는 마지막 커밋을 가지고 있는 포인터임.

HEAD를 이용하면 최신 커밋과 이전 커밋을 비교하여 출력할 수 있음.

```
$ git diff head
```

## 4.10.5 diff 내용을 추가하여 커밋

커밋 메시지를 작성할 때 -v 옵션을 같이 사용하면 diff 내용을 추가 할 수 있음.

```
$ git commit -v ------diff 내용 추가
```

