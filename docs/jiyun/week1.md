🍎 Git?
=======
### 2005년, 리누스 토르발스(리눅스 창시자)에 의해 만들어진 분산 버전 관리 시스템(Distibuted Version Control System, DVCS)
![image](https://velog.velcdn.com/images/thevlakk/post/46741c70-df17-4475-a502-2aa92458e9f2/image.png)

## 🍑  분산 버전 관리 시스템 (Distibuted Version Control System, DVCS)

**버전**
- 어떤 프로그램을 수정, 개선하여 완성했을 때 주어지는 번호 / 새로워질 때마다 번호를 늘려감 => 즉, "변화"를 의미
- 현재 내가 사용하고 있는 Java 17버전도 Java라는 언어가 수정과 업데이트를 지속적으로 해 온 것을 알 수 있음

**버전 관리 시스템 (Version Control System, VCS)**
- 파일의 버전 즉, 변화를 시간에 따라 관리해주는 시스템 
- 우리는 이 시스템을 이용해 나중에 특정 시점의 버전을 다시 꺼내올 수 있게 된다.

**분산 버전 관리 시스템(DVCS)**
- 원격저장소와 로컬저장소 모두를 이용해 파일의 버전을 저장
- 1차적으로 로컬저장소에서 프로젝트 저장 + 이후 파일의 버전을 원격저장소에 저장 가능 (분산되어 저장)

❓ 만약 서버가 다운되는 불상사가 벌어진다면❓
>-  DVCS는 필요한 파일의 일부분만 다운받아지는 것이 아닌 파일이 포함돼있는 프로젝트 전체(파일의 히스토리)를 다운 
=> 서버가 다운되도 문제없이 로컬에서  작업이 가능하다.
>- 서버가 날아가는 일이 생기더라도 클라이언트가 다운받은 프로젝트 중 하나를 골라 서버를 복원시킬 수도 있다.

- 인터넷이나 네트워크 어딘가에 있는 저장소인 리모트(remote) 저장소(원격 저장소)를 중심으로 로컬 저장소에서 변경된 내용을 서로 공유할 수 있다. => 다른 개발자와 협업을 하기에도 좋다. 

**_📓 내용에 들어가기 앞서 대체 왜 버전 관리를 해야 할까-?_**
![스크린샷 2024-03-25 213325](https://github.com/inu-appcenter/basic-study-16th/assets/146628970/17195976-123b-41c5-9936-6a714b678cf9)

하나의 문서 파일에만 수정의 수정을 계속 더한다면 과거의 작업 내용이 필요할 때(이전 문서와의 비교, 파일 손상, 파일 복구 등)  원하는 것을 얻지 못할 것이다. 이때 사본(=버전)을 만든다면 원하는 작업을 수행할 수 있다.
>추가로 위의 사진에서 변경일자와 같이 구분에 용이하게 만든다면 더욱 관리가 수월해질 듯

## 🍑 Git 핵심 기능
   * 버전 관리 (Version Control)
   * 백업 (Backup)
   * 협업 (Collaboration)

## 🍑 Git 동작 방식
![image](https://github.com/inu-appcenter/basic-study-16th/assets/146628970/65dfc0b6-afa8-452a-881d-5db219c98297)
### ✏️ Subversion(자유 소프트웨어 버전 관리 시스템 중 하나) 또는 Subversion과 비슷한 VCS
- **델타 방식** : 파일에 어떤 변화가 나타났을 때 변화된 부분만을 기록

![git vcs](https://github.com/inu-appcenter/basic-study-16th/assets/146628970/d528c0e4-315f-4094-95f0-626d5aef144f)
### ✏️  Git
- **스냅샷 방식** : 파일에 변화가 나타났을 때 변화된 부분만이 아닌 파일 전체를 기록 (변경되지 않은 부분은 이전 상태의 파일 링크 저장) 
+ 한 번 찍은 스냅샷은 수정할 수 없으며 영구적이다.

## 🍑  Git 공간
3개의 파일이 머무를 수 있는 공간이 있다.
- **Working Directory** 
: Git Directory에서 가져온 파일을 작업 중인 내 로컬 컴퓨터
: Untracked와 Tracked, 2가지 상태 가짐
   >Untracked : 파일을 저장소에 저장할 필요가 없어 git이 신경쓰지 않는 상태
   >Tracked : 파일을 추적, 관리하기 위해 git이 신경쓰는 상태
   
- **Staging Area**
: 곧 commit할 파일에 대한 정보가 담겨있는 곳 (Staged 상태의 파일 담고 있음)
: Working Directory에서 파일이 복사됨 (옮겨지는 거 ❌) => WD에서 파일을 수정해도 SA에 반영 ✖️ 

- **Git Directory(Repository)**
: Git이 프로젝트의 데이터(스냅샷)를 저장하는 곳 (Git의 핵심)

## 🍑  Git 파일 상태 및 과정
아래는 모두 Tracked 상태에서의 파일들
**상태**
- **Unmodified** : 수정되지 않은 파일
- **Modified** : 수정된 파일
- **Staged** : commit되기를 대기하는 파일

**과정**
![스크린샷 2024-03-27 003230](https://github.com/inu-appcenter/basic-study-16th/assets/146628970/9c142f4f-82bd-4b4d-8b31-3ba50716d6a4)
1. 새 파일 = Untracked 상태 -> Tracked 상태로 (Tracked에서 Staged 상태임) 
~~완전 처음 파일이니 바로 commit을 기다리는 늒임~~
2. 파일 commit -> Unmodified 상태로
3. Unmodified 파일 수정 -> Modified 상태로
4. Modified 파일에 add 명렁어 -> Staged 상태로
5. Staged 파일 commit -> 2번 단계

> ❓ 하나의 파일이 두 개의 상태 가지기 가능
> - 가능🙆 |  하나의 파일이 Staged, Modified 두 개의 상태를 가질 수 있다. 파일(스냅샷)이 Staging Area에 복사되기 때문에 Staging Area에 있는 파일에 영향이 가지 않는다.

## 🍑 Git 명령어
**git status**
: 파일의 상태 보여줌

**git add**
: When Unmodified, 파일을 Modified 상태로 (새 파일일 경우, Staged 상태로)
: When Modified, 파일을 Staged 상태로

**git commit**
: 스냅샷을 Git 저장소에 저장

**git remote**
: 원격 저장소 관리

**git init**
: 새로운 저장소 생성

**git clone**
: 코드 또는 저장소를 로컬 컴퓨터로 복제

**git push origin <브랜치 이름>**
: 브랜치를 원격 저장소로 전

**git fetch**
: 원격 저장소의 최신 변경 사항(메타데이터 정보)을 가져옴

**git merge <다른 브랜치>**
: 내 브랜치에 다른 브랜치의 내용 병

**git pull**
: fetch + merge

🍏  GitHub?
==========
### Git을 이용해 소스코드와 같은 파일을 편리하게 관리할 수 있는 웹 호스팅 서비스 중 하나
![GitHub](https://velog.velcdn.com/images/persestitan/post/7557ea9c-4eaf-4124-b743-530a8375c41b/image.jpeg)

## 🍈 GitHub 주요 기능
- 버전 관리 : Git을 이용해 프로젝트 파일 관리
- 협업 : GitHub를 원격저장소로 둠으로써 인터넷만 있다면 프로젝트 팀원 누구나 접근 가능
- 백업 : GitHub에 원격저장소를 만든 뒤 동기화하면 이후 지역저장소로 백업 가능
- 오픈 소스 : 소스코드를 공유하는 공간이기 때문에 다른 개발자가 작성한 코드를 자유롭게 볼 수 있음

## 🍈 다른 저장소
- GitLab
: Git 이용
: 이슈 추적 및 프로젝트 관리
: CI(지속적인 통합)/CD(지속적인 배포) 내장
: 개발 및 배포를 종합적으로 관리 가능
_ 차이점 : 소프트웨어의 개발과 운영에 있어 모든 기능을 제공해주는 단일 애플리케이션_

- Bitbucket 
: Git 이용
: 다른 툴, 웹 훅과의 연동 지원
: 개인의 작업보단 협업을 위한 툴

- SourceForge
: 오픈 소스 소프트웨어 개발 관리를 위한 웹사이트 ~~(오픈소스 저장소 늒임)~~
: 여러 버전 관리 시스템 지원 (CVS, Git...)
