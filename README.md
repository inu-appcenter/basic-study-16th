# 👩‍💻 Basic Study 16th
앱센터 16기를 위한 기초 지식 스터디 저장소입니다

## 🤗 Participants
### 😎 Management
|이주원|김원정|이대현|최명윤|
|:-:|:-:|:-:|:-:|
|<a href="https://github.com/Juser0"><img src="https://avatars.githubusercontent.com/u/108407945?v=4" width=120></a>|<a href="https://github.com/NARUBROWN"><img src="https://avatars.githubusercontent.com/u/38902021?v=4" width=120></a>|<a href="https://github.com/eogus4658"><img src="https://avatars.githubusercontent.com/u/58897339?v=4" width=120></a>|<a href="https://github.com/myeongyoon"><img src="https://avatars.githubusercontent.com/u/146305106?v=4" width=120></a>|
|[@Juser0](https://github.com/Juser0)|[@NARUBROWN](https://github.com/NARUBROWN)|[@eogus4658](https://github.com/eogus4658)|[@myeongyoon](https://github.com/myeongyoon)|
|**센터장**|**서버 파트장**|**iOS 파트장**|**안드로이드 파트장**|

---

### 📱 Android
|김하은|박희찬|안찬호|이준희|
|:-:|:-:|:-:|:-:|
|<a href="https://github.com/kihaeu"><img src="https://avatars.githubusercontent.com/u/163748800?v=4" width=120></a>|<a href="https://github.com/kichan05"><img src="https://avatars.githubusercontent.com/u/70091408?v=4" width=120></a>|<a href="https://github.com/ACH1002"><img src="https://avatars.githubusercontent.com/u/103422938?v=4" width=120></a>|<a href="https://github.com/Junhee8649"><img src="https://avatars.githubusercontent.com/u/67620918?v=4" width=120></a>|

---

### 🍎 iOS
|권효택|이예나|한현승|
|:-:|:-:|:-:|
|<a href="https://github.com/DIN-STUDIO"><img src="https://avatars.githubusercontent.com/u/86708287?v=4" width=120></a>|<a href="https://github.com/yena0213"><img src="https://avatars.githubusercontent.com/u/115888929?v=4" width=120></a>|<a href="https://github.com/82everywin"><img src="https://avatars.githubusercontent.com/u/109841880?v=4" width=120></a>|

---

### 💾 Server
|고지윤|김강욱|김승섭|
|:-:|:-:|:-:|
|<a href="https://github.com/jiyunio"><img src="https://avatars.githubusercontent.com/u/146628970?v=4" width=120></a>|<a href="https://github.com/kangwook1"><img src="https://avatars.githubusercontent.com/u/62889359?v=4" width=120></a>|<a href="https://github.com/ImKEISS"><img src="https://avatars.githubusercontent.com/u/86196038?v=4" width=120></a>|


## 📚 Concepts
### 1️⃣ Week 1
- Git이란 무엇인가?
    - Git에서 사용하는 명령어들을 간단하게 정리해주세요
- 그렇다면 GitHub는 무엇인가?
    - 그 외에 다른 저장소에 대해 아는 게 있다면 간단하게 정리해주세요
- 추가로 알아보면 좋을 것들 (선택)
    1. GitHub 저장소에 Pull Request 보내기 위한 과정에서 사용하는 git 명령과 명령별 옵션을 확인해본다.
    2. git 주소를 가져와서 commit하고 push할 때까지 흐름에 대해서 각자 이해한 내용을 설명한다.
    3. git add와 commit을 할때 git 내부에서는 어떤 동작이 일어나는 것인지 자료를 찾아서 학습하고 이를 비교해서 정리한다.

#### 📑 Ref.
- [Git Challenge site](https://git-challenge.com/)
- [Git 교과서 eBook link](https://thebook.io/080212/)

---

### 2️⃣ Week 2
- API란?
    - API의 정의를 간단하게 정리해주세요
- REST API란?
    - REST의 의미
    - REST 구성 요소/특징
    - REST의 장단점
    - 그외 추가적으로 공부한 내용이 있다면 정리해주세요
- API에서 사용하는 용어들
    - url / baseurl / uri
    - header / body
    - endpoint
    - HTTP Status code (200, 201, 400...)
    - HTTP Method (GET, POST, PUT, PATCH, DELETE)

---

### 3️⃣ Week 3
- API 연동 방법
    - FE
        - CORS Error
        - Mocking
    - BE
        - 각 HTTP Method마다 return해줘야하는 Status Code는?
        - 4xx, 5xx Status code 중 사용할만한 Status Code 정리해보기 ex) 400 - 유효성 검사 실패 시 사용

## 📝 Rules
> **모든 프로세스는 `issue 등록` - `branch 개설` - `마크다운 작성 후 PR`로 이루어집니다!**  
> `docs/본인이름/weekX.md` 형태로 만들어주세요! `(ex. docs/juwon/week1.md)`  
> +되도록이면 Git CLI를 사용해주세요! IDE나 GUI 툴에서 제공하는 관련 버튼이 어떤 명령어에 대응되는 지 알고 사용하셨으면 좋겠습니다!

- 커밋 컨벤션을 준수해주세요!
    - 해당 레포지토리에서는 마크다운 작업만 있을 예정이기 때문에 `Docs`만 사용해주시면 됩니다!
        - ex) Docs: 1주차 과제 일부 작성
    - Feat: 새로운 기능 추가
    - Fix: 버그 수정
    - Docs: 문서 수정
    - Style: 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우
    - Refactor: 코드 리팩토링
    - Test: 테스트 코드, 리팩토링 테스트 코드 추가
    - Chore: 빌드 업무 수정, 패키지 매니저 수정

- issue 규칙
    - 참고자료는 해당 레포지토리에서는 그렇게 준수하지 않으셔도 됩니다!
    - 참고: [https://velog.io/@junh0328/협업을-위한-깃허브-이슈-작성하기](https://velog.io/@junh0328/%ED%98%91%EC%97%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B9%83%ED%97%88%EB%B8%8C-%EC%9D%B4%EC%8A%88-%EC%9E%91%EC%84%B1%ED%95%98%EA%B8%B0)
    - 레이블 참고:
      [https://github.com/modolee/github-initial-settings](https://github.com/modolee/github-initial-settings)
    - 제목 참고: [https://doublesprogramming.tistory.com/256](https://doublesprogramming.tistory.com/256)
      <br><br>
    - 템플릿
        - issue 제목
            - 예시: **[Feat] 이슈 정리**
        - 제목 예시
            - [Add] UI button 구현

- branch 규칙
 - 각자의 영어 이름을 딴 branch 명을 사용한다.
    - 예시: 
    ```
    git checkout -b <브랜치명>      
    git checkout -b juwon
    ```

## ❔ FAQ
```markdown
Q. 해당 스터디는 어떤 스터디인가요?  
A. 앱센터 16기 신입부원들을 위한 기초지식 스터디입니다!
```

```markdown
Q. 파트별 스터디 이전에 진행하나요? 동시에 진행하나요? 
A. 앱센터 16기 스터디와 동시에 진행됩니다. 힘들겠지만 화이팅입니다!
```

```markdown
Q. 잘 모르겠는데 어떻게 하나요?
A. 파트장/센터장에게 막 물어보시면 됩니다!
```
