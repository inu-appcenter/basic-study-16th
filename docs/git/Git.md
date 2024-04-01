# Git의 3대 목적: 버전관리, 백업, 협업

### 1. 버전관리(VCS: Version Control System)

#### **파일의 변경사항을 추적하고 그 이력을 기록하고 관리하도록 돕는 버전관리 시스템**

**Git을 사용하지 않을 경우**

이전의 버전이 필요할 경우 다른 이름으로 따로 저장한 뒤에 새로운 버전을 만들어야 한다. 즉, 같은 이름의 파일이 수없이 많아지게 된다.

**Git을 사용하는 경우:**

이전 파일의 버전은 history에 따로 저장되고 갱신할 때 마다 changes에 갱신된다. 즉 같은 이름의 파일을 다른 이름으로 저장할 필요가 없고 각각의 파일이 갱신되는 것의 현황과 기록을 따로 Git을 활용해서 볼 수 있고 이전 버전으로 파일을 변경시킬 수도 있다..

## 2. 백업

컴퓨터는 고장날 수도 있기 때문에 귀중한 파일은 백업이 필요하다. 따라서 원격저장소인 Github에 따로 저장하여 안전하게 보호한다. 이때 원격전송을 사용할 수 있고 Github 내에서도 버전의 기록과 갱신을 확인할 수 있다.

push: 새롭게 만들고 파일을 업로드

pull: 새롭게 바뀐 파일을 다운로드

## 3. 협업

협업은 백업을 통한 push와 pull을 통해서 이루어진다.

# Git의 종류

Sourcetree, Github Desktop, Git(original) 등의 다양한 git client가 존재한다.

# 특징

- 대부분의 VCS와 다르게 ‘스냅샷’으로 저장된 각 버전을 저장한다.
- Local에서 변경사항을 추적하고 관리한다.
- Local에서 관리하여 인터넷이 필요없고 여러 클라우드 서비스와 독립적으로 사용될 수 있다.
- 인터넷이 없이 Local에서 관리를 하기에 다른 개발자들과 실시간으로 작업 내용을 공유할 수 없다.

### 명령어모음
#### 준비 및 시작
- 폴더 초기화 - git init
- 상태확인 - git status
- 로컬 저장소와 원격 저장소와 연결 - git remote add origin "깃허브 주소"
	- 연결 확인 - git remove -v
- 원격 저장소 복사 - git clone "깃허브 주소"

#### 브랜치 
- 브랜치 생성 - git branch [브랜치명]
- 브랜치 이동 - git checkout [브랜치명]
- 현재 브랜치 확인 - git branch
- 모든 브랜치 확인 - git branch -a
- 생성 및 이동 - git checkout -b [브랜치명]


#### 깃허브 업로드
- 변경 부분 적용 - git add [디렉토리명]
- 변경 부분 삭제 - git restore [디렉토리명]
- 변경 부분 모두 적용 - git add -all
- 브랜치의 수정 사항 가져옴 - git pull
	- ==<u><span style="background-color: #fff5b1; color: red">merge 전 필수</span></u>
- 커밋 - git commit -m "커밋 메세지"
- 푸시 - git push origin [브랜치명]

#### 수정
- 가장 최신 커밋 취소 - git reset HEAD^
- 여러 커밋 취소(ex: 3개) - git reset HEAD~3
- 강제 푸시 - git push origin [브랜치명] -f

#### Merge
- 현재 선택된 브랜치에 자식 브랜치 병합 - git merge [자식브랜치명]
- merge 취소 - git merge --abort

기록 조회 - git log


