## Github-Study

#Introduce
이곳은 제가 깃허브를 스스로 정리한 내용을 업로드 하는 곳 입니다.

### 1.1 버전관리
## 1.1.1 버전이란?

버전은 이전과 약간씩 다른 변화들을 구분하는 표시입니다.<br>
서브버전은 버전과 버전 사이에 변화된 것을 말합니다.

## 1.1.2 버전관리의 필요성 ?
개발 도중에는 수많은 기능이 추가되고, 코드가 변경됩니다.<br>
테스트 하는 과정에서 불안정한 코드가 있다면 작업하기가 어렵습니다.<br>
따라서 이전 상태로 돌아가 다시 시작할 수 있는 코드의 복귀 지점이 필요합닏.<br>
이것이 버전관리의 필요성입니다.

1.2 버전관리 시스템
1.2.1 버전 관리 소프트웨어
코드와 컨텐츠의 변화를 관리하고 추적하는 소프트웨어를 버전관리 시스템이라고 합니다.
현재 사용하는 VCS는 집중형과 분산형, 두 종류로 구분할 수 있습니다.

집중형
집중형 시스템은 말 그대로 모든 소스코드가 한곳에 집중되어 있는 형태입니다.
하나의 메인 중앙 서버에서 개발 구성원의 모든 소스코드를 통합적으로 관리합니다.
클라이언트-서버 모델이라고도 합니다.
장점: 시스템 운영이 수월함
단점: 서버에 문제가 생기면, 메인 저장소에 모든 개발자가 접근이 불가능한 상황이 발생 가능, 파일을 변경하려면 개발자들은 순서대로 대기하고 있어야 함.
집중형 관리 시스템 예시) SCCS,RCS,CVS,서브버전

분산형
분산형 버전관리 시스템은 저장소가 여러 개 있습니다. 여러 저장소에 각 버전별로 소스를 개별 보관 합니다. 분산 저장소는 P2P 방식으로 공유하고, 공유 가능한 저장소 사본을 개발자에거 제공합니다.
장점: 메인 서버에 문제가 생기더라도 지속적으로 개발할 수 있음.
단점: 익숙해지는 데 시간이 걸림.
분산형 관리 시스템 예시) 깃, 머큐리얼, 비트키퍼

1.3 깃
깃은 2005년에 리눅스 개발자인 리누스 베네딕트 토르발스가 개발했습니다.

깃의 특징
- 대표적인 분산형 버전 관리 시스템. 원격 저장소와 별개로 개발자 각각의 로컬 컴퓨터에 복제본 소스 코드로 저장할 수 있음.
- 인터넷이 연결되어 있지 않아도, 로컬 컴퓨터의 소스 코드만으로 버전을 관리할 수 있습니다.
- 원격 저장소로 개발자의 저장소와 연결하거나 동기화 작업을 할 수 있음.

1.3.1 백업 기능
분산형 깃은 자신의 로컬 컴퓨터에서 독립적으로 소스의 버전 관리를 할 수 있습니다. 오류로 모든 소스 코드를 잃을 수 있는 상황에 대비하여 별도의 외부 저장 장치에 데이터를 백업하기도 합니다. 이럴 때 깃을 사용하면 편리합니다. 깃을 사용하면 코드를 원격 저장소에 저장할 수 있습니다.

1.3.2 협업 개발
깃은 다수의 개발자와 코드를 공유하고 협업할 때 매우 유용합니다.

코드 공유
깃을 사용하면 네트워크를 통해 코드를 좀 더 쉽게 공유할 수 있습니다. 인터넷이 연결되지 않은 상태에서도 코드 이력을 관리하고, 다른 개발자와 공유하여 협업할 수 있습니다.

책임과 기록
깃은 변경된 모든 이력을 저장합니다. 누가 언제 어떤 파일을 수정했는지 기록합니다. 깃은 커밋(Commit)을 거쳐 모든 코드의 수정 이력을 기록합니다. 커밋으로 저장된 원본 객체는 수정할 수 없습니다.

원격 공유
깃에서는 원격 저장소가 중앙 서버 역할을 합니다. 자신의 코도 저장소를 원격 서버에 푸시(Push)하여 저장합니다. 또 다른 개발자의 소스를 원격 서버에서 풀(Pull) 또는 페치(Fetch)하여 언제든지 내려 받을 수 있습니다.

병합
하나의 소스 코드를 여러 가지 브랜치로 분기하여 독립된 기능을 구현할 수 있습니다. 독립적으로 구현된 소스를 주고 받으며, 각 브랜치를 하나로 병합하기도 합니다. 깃에서는 다양한 병합 알고리즘을 제공하여 소스 코드의 충돌을 최소화하고 최종 코드를 쉽게 유지합니다.

공개
원격 저장소를 사용하여 개발중인 코드를 외부로 공개할 수 있습니다. 이를 통해 기능 한계를 극복하고 외부 개발자와 협업할 수 있습니다. 외부 개발자는 원격 저장소를 포크(Fork)하여 소스 코드의 버그를 수정하거나 기능을 개선할 수 있습니다.

2. 깃과 소스트리 설치 및 환경 설정
2.1~2.2 깃 & 소스트리 설정

2.3. 첫 번째 깃 실행
2.3.1 터미널
터미널 환경이란 텍스트 명령어를 입력하고 실행하는 환경을 의미합니다. 이를 이용하면 깃 작업을 다양하게 할 수 있습니다. GUI는 많이 사용하는 기능 위주로 동작을 구현했기 때문에 터미널보다 정밀한 작업은 하기 어렵습니다.

2.3.2 깃 명렁어로 실행
깃 프로그램 이름은 git입니다. 터미널에서 git과 명령어를 입력하면 깃이 동작합니다. 

2.4 환경 설정
깃을 설치했다면 여러 가지 환경 설정도 해야 합니다. 사용자 이름과 이메일 주소는 필수 항목이고, 그 외 나머지 항목은 옵션입니다.
