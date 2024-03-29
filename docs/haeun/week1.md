contents

## git?  
컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템이다.  
소프트웨어 개발에서 소스 코드 관리에 주로 사용되지만 어떠한 집합의 파일의 변경사항을 지속적으로 추적하기 위해 사용될 수 있다. 

## 명령어  
git init: git 저장소 생성  
git clone: 원격 저장소를 가져옴  
git add: 스테이징 영역에 변경사항을 추가  
git commit: 새로운 커밋 만들기  
git stash: 커밋하지 않은 변경사항 임시 저장  
git revert: 커밋한 내용을 되돌리는 명령어(취소)  
git clean: git으로 관리되지 않는 파일 정리(git status로 untracted 상태 확인)    
git version: 현재 git 버전 확인  
git branch: 브랜치를 생성, 조회, 삭제  
git switch: 다른 브랜치로 전환(=git checkout)

git status : 변경된 파일 확인  
git add . : 변경된 파일 스테이징(커밋할 파일 세팅)  
git commit -m ' commit message '   
git push origin haeun : git허브에 올리기

## commit  
git에서는 commit이라는 단위로 변경사항을 생성하고 추적한다. commit에는 사용자가 정확이 원하는만큼만 변경사항을 추가할 수 있다.  이를 위해서 git에서는 프로젝트 디렉터리의 변경사항을 커밋으로 바로 생성하지 않고, 커밋으로 생성할 내용을 먼저 스테이징 영역에 추가한 다음, 이 스테이징 영역에 있는 내용만을 커밋으로 만든다. 

## gitflow?  
 깃플로우 전략은 소프트웨어의 소스코드를 관리하고 출시하기 위한 '브랜치 관리 전략' 중 하나이다.  
 git-flow 전략 외에도 github flow와 gitlab flow 전략 등도 있다.   
 git-flow에서 사용하는 브랜치의 종류는 5가지이다.  
 항상 유지되는 메인 브랜치(Master, develop)와 일정 기간 유지되는 보조 브랜치(Feature, Realease, Hotfix)로 나뉜다.  

## github? 
분산 버전 관리 툴인 깃을 사용하는 프로젝트를 지원하는 웹호스팅 서비스이다.  
git은 버전관리 시스템이고, github는 git으로 관리하는 프로젝트를 올려둘 수 있는 사이트이다.  
코드 버전관리, 코드 배포관리, 협업, 이슈관리 진도관리 등등  

## 다른 저장소  
-gitlab: 소프트웨어 개발 및 협읍을 위한 올인원 솔루션을 제공하는 웹 기반 devops 플랫폼  
-sourcetree: 명령어 대신 버튼 클린, GUI 프로그램, 무료, 시각적으로 커밋과 브랜치 표현  
-github desktop: GUI 프로그램, command 없이 버튼으로 git 이용