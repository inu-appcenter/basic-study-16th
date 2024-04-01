# 1주차_Git/GitHub란?

생성일: 2024년 3월 29일 오후 3:04

# 📌**Git (깃) 이란?**

---

![download](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/e57ddcaa-d9b5-422b-a15c-4455bccc37d7)

> ***깃(Git/ɡɪt)** 은 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 [스냅샷](https://www.notion.so/1-_Git-GitHub-b7602361e65849b0b94211be41ba9b53?pvs=21) 스트림 기반의 [분산 버전 관리 시스템](https://www.notion.so/1-_Git-GitHub-b7602361e65849b0b94211be41ba9b53?pvs=21)이다. (위키백과)*
> 

## **스냅샷**

**스냅샷(Snapshot)** 이란 사진을 찍듯이 특정 시간(시점)에 데이터 저장 장치(스토리지)의 파일 시스템을 포착해 별도의 파일이나 이미지로 저장, 보관하는 기술을 말한다. 

원본 데이터 전체를 그대로 복사해 다른 곳에 저장하는 백업과는 다르게 추가된 데이터(변화된 부분)의 크기(용량)만 스냅샷을 하여 저장하기에 전체적인 용량을 아낄 수 있다.

![img1 daumcdn](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/76a0ed8b-f0f4-4e87-b498-bf0cecbb5caa)

백업 방식

![img1 daumcdn 1](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/36e30bbb-8eaa-4ecd-9a67-2b72f2463b85)


스냅샷 방식

백업 방식과 비교하자면 위 그림으로 표현할 수 있지만 실제로 Git에서 사용하는 방식은 기존 버전관리 시스템(SVN, P4V 등)에서 사용하던 델타 기법과는 다른 방식으로 버전 데이터를 관리한다.

![03](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/6a3f2044-ecfa-445a-9773-9b85ad5cc0d4)

델타 방식

![04](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/512a07d6-c9f1-4b23-a335-6323794274cf)


스냅샷 방식

**델타 방식**은 각 파일의 버전을 생성할 때, 파일 전체를 저장하고, 이후 해당 파일에 발생하는 모든 수정 사항, 즉 변경점을 저장한다
반면에 **Git**은 저장소의 파일 시스템 전체를 스냅샷으로 취급한다. 커밋 시점의 저장소 상태가 하나의 버전이 된다. 파일이 변경되지 않았다면 Git은 파일을 새로 저장하지 않고 링크만 저장한다.

## 버전 관리 시스템

- **버전 관리**
    
    ![vcs-hell](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/fec68d7b-f53c-4057-8b08-333eb5993564)
    

파일들의 버전을 관리하는 가장 간단한 방법은 위 사진처럼 각 버전의 복사본을 디렉토리에 함께 보관하는 것이다. 스냅샷에서 살펴본 [백업 방식](https://www.notion.so/1-_Git-GitHub-b7602361e65849b0b94211be41ba9b53?pvs=21)의 원형이다. 

다만 해당 방식은 파일의 버전 이력 쉽게 알기 어렵다는 문제와 용량이 큰 파일을 관리하기에는 저장 공간에 부담이 크다는 문제, 수작업으로 진행하다 보니 파일을 잘못 삭제하거나 하는 실수가 있을 수 있다는 문제가 있다.

이런 문제를 해결하기 위해 버전 관리 시스템이 고안되었다.

- **버전 관리 시스템**

버전 관리 시스템(VCS, Version Control System)은 파일 버전을 관리하는 소프트웨어다. 사용자가 파일의 복제본을 직접 생성하지 않아도 여러가지 명령어를 통해 파일 버전을 효율적으로 관리할 수 있도록 도와준다. 단순 파일 복제를 넘어 변경 사항만 기록해서 디스크를 효율적으로 사용하고 브랜치를 생성해서 서로 다른 작업을 독립적으로 진행하는 등 다양한 기능을 지원한다.

버전 관리 시스템에는 다음과 같이 중앙 집중식 버전 관리 시스템과 분산형 버전 관리 시스템으로 나뉜다.

![img1 daumcdn 2](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/b2c9023b-9d66-4c7d-a966-95de9e7db411)

- **중앙 집중식 버전 관리 시스템(CVCS, Central Version Control System)**

**CVCS**에서 사용자는 **원격 저장소에서 최신 버전의 파일만을 내려받아서 사용한다**. 사용자가 새로운 버전을 추가하기 위해서는 무조건 원격 저장소에 추가해야 한다. 최신 버전이 항상 원격에 유지되며 사용자는 원격에 접속하지 않고는 작업 이력을 남길 수 없으므로 관리자로서는 관리하기 쉽다는 장점이 있다. 하지만 사용자가 원격 저장소에 연결되어 있지 않을 경우 협업, 백업을 할 수 없다는 단점이 생긴다.

- **분산형 버전 관리 시스템(DVCS, Distributed Version Control System)**

**DVCS**는 원격 저장소에서 최신 버전의 파일만 가져오는 것이 아니라 **과거 이력을 포함한 저장소의 모든 데이터를 복제**한다. 복제한 후에는 로컬에서 자유롭게 작업을 진행할 수 있고 원격 저장소에 문제가 생겨도 로컬에 복제된 저장소로 복구할 수 있다는 등의 장점이 있다. 복제한 로컬 저장소는 원격에 접속하지 않고도 모든 버전에 접근할 수 있는 진정한 백업이다.

## **Git 의 장점**

- 소스 코드를 주고 받을 필요 없이, 같은 파일을 **여러 명이 동시에 작업하는 병렬 개발이 가능**하다.
- 분산 버전 관리 시스템이기 때문에 **인터넷이 연결되지 않은 곳에서도 개발을 진행**할 수 있고, 중앙 저장소가 날라가 버려도 원상복구할 수 있다.
- 팀 프로젝트가 아닌, 개인 프로젝트에서도 Git을 통해 **버전 관리를 하면 체계적인 개발**이 가능해지고, 프로그램이나 패치를 배포하는 과정도 간단해진다.

## **Git 작동 구조**

![img1 daumcdn 3](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/90ac2119-ce97-4a21-bdd2-0ca587bd7eb2)

Git에서는 파일의 상태를 크게 3가지로 분류한다. 이 3가지 상태는 파일이 Git에 의해 어떻게 관리되고 있는 지를 나타낸다.

- **Working Directory**

작업 디렉토리는 개발자가 실제 작업하고 있는 공간을 의미한다. 여기에서 파일을 생성하거나 수정하면, 그 파일들은 Working Directory에 위치한 상태가 된다. 이 때 해당 파일들의 상태는 다시 두 가지로 나뉜다.

**UnTracked** 상태의 파일들은 Git이 이전에 본 적 없는 새로운 파일이거나, ‘.gitignore’ 파일에 의해 Git의 추적에서 제외된 파일이다. 이러한 파일들을 Git에 의해 관리되고 있지 않는 상태이다.

**Tracked** 상태는 Git이 이전에 본 적 있는 파일로, 이전의 커밋에 포함되었던 파일이거나 git add 명령어를 통해 추적 대상에 추가된 파일이다. 이러한 파일들은 Git에 의해 관리되고 있는 상태이다.

- **Staging Area**

스테이징 영역은 커밋을 준비하는 임시 공간이다. 개발자는 Git add 명령어를 통해 Working Directory의 파일들을 스테이징 영역에 추가하고, 이렇게 추가된 파일들은 다음 커밋에 포함될 준비가 된 상태이다.

- **Repository**

리포지토리는 파일의 바뀐 내용들이 모두 커밋된 상태를 나타낸다. 즉, 파일이 어떤 버전에 포함되어 있다는 것을 의미한다. git commit 명령어를 실행하면, 스테이징 영역의 모든 파일들이 커밋되어 리포지토리에 저장된다.

여기에 GitHub와 같은 원격 저장소가 포함된다면 다음과 같은 작동 구조를 가진다.

![img1 daumcdn 4](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/8a072f36-2e1b-4164-8945-b7c274fdc1b7)

원격 저장소의 내용을 로컬 저장소로 복사(clone)하고 로컬 저장소의 내용을 원격 저장소로 업데이트(push)하거나 원격 저장소에서 최신 형상을 로컬 저장소로 가져올(pull) 수 있다.

## Git 명령어

| 분류 | 명령어 | 기능 |
| --- | --- | --- |
| 시작 및 설정    | $ git --version | 설치된 git 버전 확인 |
|  | $ git init | .git 하위 디렉토리 생성 |
|  | $ git config --global user.name "사용자이름" | 사용자 이름 설정 |
|  | $ git config --global user.email "사용자이메일" | 사용자 이메일 설정 |
|  | $ git status | 상태 확인 |
| 저장소   | $ git remote add origin [github 저장소 주소] | 원격 저장소 연결 |
|  | $ git remote -v | 저장소 확인 |
|  | $ git clone /로컬/저장소/경로 | 로컬 저장소 복제 |
|  | $ git clone 이름@호스트:/원격/저장소/경로 | 원격 저장소 복제 |
| commit 명령어    | $ git add 파일명 | 커밋에 변경사항 올림 |
|  | $ git add . | 수정한 전체파일 올림 |
|  | $ git commit -m "메세지" | 커밋 생성(변경사항 저장) |
|  | $ git log | 커밋 내역 확인 |
|  | $ git status | 파일 상태 확인 |
| branch 명령어       | $ git branch | 브랜치 목록 확인 |
|  | $ git branch 브랜치명 | 브랜치 생성 |
|  | $ git checkout 브랜치명 | 브랜치로 이동 |
|  | $ git checkout -b 브랜치명 | 브랜치만들고 이동 |
|  | $ git checkout master | master 브랜치로 돌아옴 |
|  | $ git branch -d 브랜치명 | 브랜치 삭제 |
|  | $ git log --oneline | 한 커밋씩 출력 |
|  | $ git log --branches --graph | 커밋을 그래프로 표시 |
| push 명령어    | $ git push origin master | 원격 저장소에 업로드 |
|  | $ git push 저장소주소 브랜치이름 | 커밋을 원격 저장소에 업로드 |
|  | $ git push -u 저장소주소 브랜치이름 | 커밋을 원격 저장소에 업로드 |
|  | $ git remote add origin 저장소주소 | 클라우드 주소 등록 |
|  | $ git remote remove 저장소주소 | 클라우드 주소 삭제 |
| merge 명령어   | $ git pull | 원격 저장소 변경사항 가져오고 병합하기 |
|  | $ git merge 다른브랜치이름 | 현재 브랜치에 다른 브랜치 병합 |
|  | $ git add 파일이름 | 파일 병합 |
|  | $ git diff 브랜치이름 다른브랜치이름 | 병합 이전의 내용과 비교 |
| 로컬 명령어 | $ git checkout --파일명 | 변경 전으로 되돌림 |
|  | $ git fetch origin | 현재 상태를 다운로드 |

# 📌**GitHub (깃허브) 란?**

---

![%EA%B9%83%ED%97%88%EB%B8%8C](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/b083f061-ee71-46ab-9b12-b15c57dee836)

> ***깃허브(GitHub)** 는 분산 버전 관리 툴인 깃(Git) 저장소 호스팅을 지원하는 웹 서비스이다. (위키백과)*
> 

깃허브(GitHub)는 Git을 지원하는 웹 호스팅 서비스 시스템(클라우드)의 한 종류이다. 내 컴퓨터에 있는 깃의 히스토리(기록)을 가져와서 깃허브 웹사이트(클라우드)에 올릴 수 있고 변경된 히스토리를 확인할 수 있다.

## GitHub 장단점

### 장점

- git 저장소 호스팅 사이트 중 가장 큰 규모의 서비스이다
- 업로드 / 다운로드의 속도가 가장 빠르다
- private repository를 무료로 사용 가능하다 (협업자 제한 없음)
- 최근 무료 서비스 정책으로 대부분의 기능이 이용 가능하다
- Git 호스팅 서비스 중 가장 안정적인 서버를 제공한다

### 단점

- LFS(Large File Storage)의 트래픽 제한이 있다

## GitHub 외 다른 저장소

- **GitLab**
    
    ![img1 daumcdn 5](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/29b91c40-4143-4d93-810f-117f425392eb)
    

GitLab(깃랩)은 자신의 서버에 설치하여 서버 내 프라이빗한 Git 원격 저장소를 만들수있는 서비스이다.

개발 외 DebOps 환경 구축에 용이하다. (이슈 추적, 테스트, CI/CD 파이프라인)

3rd party 플러그인/툴 없이 자체 CI/CD가 가능하다.

Kubernetes 기반으로 배포 및 모니터링이 가능하다.

GitHub에 비해서는 느린 push와 pull 속도를 가지고 있다.

- **BitBucket**
    
    ![img1 daumcdn 6](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/b58ad3c7-1b2d-4643-a8d7-4ecfc25788ba)
    

Bitbucket은 Atlassian이 개발하고 제공하는 DVCS로 Git 기반의 코드 호스팅 및 협업 도구이다. 

Jira와의 연동성이 좋고 Jenkins, CircleCI CI/CD 도구를 제공한다.

코드 리뷰, 테스트, 분석 도구를 활용한 Pull Request 단계에서의 Code Insights 기능을 제공한다.

계정의 비공개 콘텐츠 clone, push 작업 시 2단계 인증(2FA) 절차가 필수이다.