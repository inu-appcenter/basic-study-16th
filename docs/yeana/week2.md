## 🧩 API란?

(Application Programming Interface: 응용 프로그램 프로그래밍 인터페이스)

- 인터페이스
    
    상호 간의 소통(read/write)을 위해 만들어진 접점
    
    ex) 자동차 스마트키
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/700b4d3c-69f5-4ad4-beb3-650ff83dd912/15a0849a-1465-4012-bfe3-fa435aef0522/Untitled.png)
    
    ex) 치킨을 시키는 과정에서 알 수 있는 인터페이스는?
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/700b4d3c-69f5-4ad4-beb3-650ff83dd912/b834ddaa-18c6-48b5-8e5c-a0bc9242df55/Untitled.png)
    
    → 메뉴목록, 주문하기 버튼, 앱에 있는 모든 화면
    
- UI
    
    (User Interface: 사용자 인터페이스)
    
    : 사용자와 기계나 시스템같은 사물이 소통하는 데 도움을 주는 매개체
    
    ex) 스마트폰의 홈버튼/전원버튼 : 바탕화면으로 한번에 이동할 수 있게 해줌 → 이 요청을 전달하는게 홈버튼임 !
    
- CLI : Command Line Interface
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/700b4d3c-69f5-4ad4-beb3-650ff83dd912/6c15b2cb-c28c-429a-a536-4834f25f4c55/Untitled.png)
    
- GUI
    
    Graphic User Interface: 그래픽 사용자 인터페이스
    
    - 보통 우리는 바탕화면과 시작 메뉴에 있는 아이콘들을 더블 클릭하며 응용 프로그램들을 실행한다. 컴퓨터로 보고 있다면 크롬이나 파이어폭스, 사파리를 열어 이 글을 보고있을 것이다. 이 모든 것들이 **GUI**(그래픽 사용자 인터페이스, Graphic User Interface)의 일부이다/

⇒ UI와 GUI 그리고 CLI의 공통점 :  **어떤 사물(스마트폰, 컴퓨터, 인터넷 등)과 사용자 사이를 이어주는 다리 역할**을 함

- API
: 프로그램과 프로그램 간 다리, 프로그램을 간의 상호작용을 위한 인터페이스
    - ex1) 레스토랑 - 식당 메뉴판/웨이터 역할
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/700b4d3c-69f5-4ad4-beb3-650ff83dd912/db3aaf07-08a1-4622-b21d-18816e6e428a/Untitled.png)
        
        사용자가 웨이터(API)에게 주문 → 웨이터(API): 주문내역을 주방에 전달 → 요리사: 요리 후 웨이터에게 전달
        
        사용자: 요리과정을 알 필요 없음! ← 웨이터: 주문 음식을 손님에게 갖다줌
        
    - ex2) 온라인 쇼핑몰 운영 - 결제 시스템
        
        나 : 옷 판매에 집중
        
        결제 방법 : 다른 사람이 만든 결제 시스템을 받아 내 사이트에 넣기
        
        → 결제 시스템을 몰라도  API를 통해 옷을 판매할 수 있음
        
    
    ⇒ **API의 기능을 어떻게 구현하는지 몰라도 되고 난 그저 API가 갖다주는 걸 사용만 하면 된다**
    
    이를 통해 시간과 노력을 동시에 아낄 수 있다. 이처럼 API는 처음부터 개발하거나 유지 보수할 필요가 없는 외부 데이터와 기능에 접속할 수 있게 해준다.
    

### < API가 가져야하는 내용 >

(GET요청) [comic.naver.com/webtoon/detail? i](http://comic.naver.com/webtoon/detail?id)d=123412 

1. 요청방식(method) → get함수 사용 : 데이터 달라고 할것인지, 보내달라고 할것인지
2. 무슨자료 요청할지(endpoint) : 어떤 데이터를 요청할래? 웹툰? 댓글? 뉴스?
3. 자료요청에 필요한 추가정보 : 내아이디, 이름, 몇화보고싶은지

→ 우리는 브라우저를 통해 항상 API요청을 함(get요청을 함) : HTML을 통해 이미지나 이미지, 제목, 버튼 등에 API 주소가 숨겨져있음

public API : 누구나 사용가능한 공개 API

private API : 사내에서 몰래쓰는 API

partner API : 미리 정해둔 사람만 쓰는 API

→ 모든 프로그램은 API가질 수 있음

WindowsAPI : 윈도우 운영체제 기능들 사용가능(database관리 프로그램 등)

Database 관리 프로그램API : DB 입출력 기능들 사용 가능

xx 프로그램 API : xx 기능들 사용 가능

## 🧩 REST API란?

### Rest

- REST 구성 요소/특징
    - 구성요소
        1. 자원(Resource) : HTTP URI
            - 모든 자원엔 고유 ID 존재 → 이것은 server에 존재
            - ID : `/orders/order_id/1` 와 같은 HTTP URI
        2.  행위(Verb) : HTTP Method
            - HTTP 프로토콜 method 사용
            
            →  `GET`, `POST`, `PUT`, `DELETE 등의` 메서드를 제공
            
            ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/700b4d3c-69f5-4ad4-beb3-650ff83dd912/604a604a-6bd1-42d8-8fd2-4b93fd8c94c2/Untitled.png)
            
            이미지 출처: https://meetup.toast.com/posts/92
            
        3.  표현(Representations) : HTTP Message Pay Load
            - Client: 자원의 상태 (정보)에 대한 조작을 요청
            → Server: 적절한 응답 (Representation)을 전송
            - 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 Representation으로 나타낼 수 있음 ( in REST )
            
            cf) 현재는 JSON으로 주고 받는 것이 대부분임
            
        
    - 특징
        - **클라이언트 / 서버 구조** → 서로 간 의존성이 하락
            - 클라이언트: 유저와 관련된 처리, 서버: REST API를 제공
            → 각각의 역할이 확실하게 구분, 일괄적인 인터페이스로 분리되어 작동할 수 있게 함
            - REST Server: API를 제공하고 비지니스 로직 처리 및 저장을 책임짐
            - Client: 사용자 인증이나 context (세션, 로그인 정보) 등을 직접 관리하고 책임짐
            
        - **무상태성 (Stateless)** → 구현이 쉽고 단순해진다.
            - REST는 HTTP의 특성을 이용→ 무상태성 가짐
            - 서버에서 어떤 작업을 하기 위해 상태정보를 기억할 필요가 없음
            - 들어온 요청에 대해 처리만 해주면 됨
            
        - **캐시 처리 가능 (Cacheable)** → 전체 응답시간, 성능, 서버의 자원 이용률을 향상 시킬 수 있음
            - HTTP라는 기존 웹표준을 사용하는 REST의 특징 덕분에 기본 웹에서 사용하는 인프라를 그대로 사용 가능
            - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구
            - 캐시 사용을 통해 응답시간 fast
            - REST Server 트랜잭션이 발생하지 않음
            
        - **자체 표현 구조 (Self - descriptiveness)**
            - JSON을 이용한 메시지 포멧을 이용→직관적으로 이해할 수 있음
            - REST API 메시지만으로 그 요청이 어떤 행위를 하는지 알 수 있음
        - **계층화 (Layered System)** → 자유도가 높다
            - 클라이언트와 서버가 분리 → 중간에 프록시 서버, 암호화 계층 등 중간매체를 사용할 수 있음
            
        - **유니폼 인터페이스 (Uniform)** → 특정 언어나 기술에 종속되지 않음
            - Http 표준에만 따른다면 모든 플랫폼에서 사용이 가능
            - URI로 지정한 리소스에 대한 조작을 가능하게 하는 아키텍쳐 스타일
            - URI로 지정한 Resource에 대한 조작을 통일되고 한정적인 인터페이스로 수행
            
- REST의 장단점
    - 장점
        - HTTP 프로토콜의 인프라를 그대로 사용 → REST API 사용을 위한 별도의 인프라를 구출할 필요가 없음
        - HTTP 프로토콜의 표준을 최대한 활용 → 여러 추가적인 장점을 함께 가져갈 수 있게 해 줌
        - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용 가능
        - Hypermedia API의 기본을 충실히 지키면서 범용성 보장
        - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있음
        - 여러 가지 서비스 디자인에서 생길 수 있는 문제 최소화
        - 서버와 클라이언트의 역할을 명확하게 분리
    - 단점
        - 표준이 자체가 존재하지 않아 정의가 필요
        - HTTP Method 형태가 제한적
        - 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구됨
        - 구형 브라우저에서 호환이 되지 않아 지원해주지 못하는 동작이 많다.(ex: 익스폴로어)
- REST의 핵심 설계 목표
    1. 컴포넌트들간의 유연한 (쉽게 확장가능한) 상호 연동성 확보
    2. 범용 인터페이스
    3. 각 컴포넌트들의 독립적인 배포
    4. 지연 감소, 보안강화, 레거시 시스템을 인캡슐레이션하는 중간 컴포넌트로의 역할
    cf) 인캡슐레이션: 데이터에 헤더가 추가되는 과정 즉, OS Lv7 → Lv1로 내려 가는 과정을 뜻하며 간단하게 말하면 PC에서 다른 PC로 데이터를 전송할 때 데이터를 패키지화하는 과정을 말한다.
- REST API 설계 규칙
    
    **1. 슬래시 구분자(/ )는 계층 관계를 나타내는데 사용**
    
    ```html
    http://restapi.example.com/houses/apartments
    ```
    
    **2. URI 마지막 문자로 슬래시(/ )를 포함하지 않는다.**
    
    - REST API는 분명한 URI를 만들어 통신을 해야 하기 때문에 혼동을 주지 않도록 URI 경로의 마지막에는 슬래시(/)를 사용하지 않는다.
    
    ```html
    http://example.com/posts/    (X)
    ```
    
    **3. 하이픈(-)은 URI 가독성을 높이는데 사용**
    
    - 불가피하게 긴 URI경로를 사용하게 된다면 하이픈을 사용해 가독성을 높인다.
    
    **4. 밑줄(_)은 URI에 사용하지 않는다.**
    
    - 밑줄은 보기 어렵거나 밑줄 때문에 문자가 가려지기도 하므로 가독성을 위해 밑줄은 사용하지 않는다.
    
    **5. URI 경로에는 소문자가 적합하다. 대문자 사용은 피하도록 한다.**
    
    - RFC 3986(URI 문법 형식)은 URI 스키마와 호스트를 제외하고는 대소문자를 구별하도록 규정하기 때문
    
    cf) 파일확장자는 URI에 포함하지 않는다.
    
    **6. REST API에서는 메시지 body 내용의 포맷을 나타내기 위한 파일 확장자를 URI 안에 포함시키지 않는다.**
    
    **Accept header를 사용한다.**
    
    ```html
    http://restapi.example.com/members/345/photo.jpg (X)
    GET / members/345/photo HTTP/1.1 Host: restapi.example.com Accept: image/jpg (O)
    ```
    
    **7. 리소스 간에는 연관 관계가 있는 경우**
    
    => /리소스명/리소스 ID/관계가 있는 다른 리소스명
    
    ```html
    GET : /users/{userid}/devices (일반적으로 소유 ‘has’의 관계를 표현할 때)
    ```
    

### RESTful API

: HTTP와 URI 기반으로 자원에 접근할 수 있도록 제공하는 애플리케이션 개발 인터페이스

- 기본적으로 개발자는 HTTP 메소드와 URI 만으로 인터넷에 자료를 `CRUD` 할 수 있다.
- 'REST API'를 제공하는 웹 서비스를 **'RESTful'** 하다고 할 수 있다.

cf) RESTful은 REST를 REST 답게 쓰기 위한 방법으로, 누군가가 공식적으로 발표한 것은 아니다.

**cf) RESTful 하지 못하는 경우**

URI 규칙을 올바르게 지키지 않은 API는 REST API의 설계 규칙을 올바르게 지키지 못한 시스템은 REST API를 사용하였지만 RESTful 하지 못한 시스템이라고 할 수 있다.

> Ex1) CRUD 기능을 모두 POST로만 처리하는 API
> 

> Ex2) route에 resource, id 외의 정보, URI에 행위(method)에 대한 부분이 들어가는 경우(/students/updateName)
> 

## 🧩 API에서 사용하는 용어들

- url / baseurl / uri
    - url : 웹 상에서 서비스를 제공하는 각 서버(컴퓨터)들에 있는 자원(파일)의 위치
    - baseurl : 기본 URL은 웹사이트 주소의 연속적인 요소
        
        ex) Facebook 계정에 로그인하거나 컴퓨터에서 Facebook 페이지를 방문할 때마다 주소 부분 [http://facebook.com이](http://facebook.xn--com-5k0o/) 주소 표시줄에 표시되는 것을 알 수 있다. 이것은 기본 URL입니다. 그 이후에 오는 모든 것은 URL 경로이다. 
        
    - uri : 유일한 자원 식별자
    
    → url과 uri는 위치와 식별자(유일하게 식별할수 있는요소)라는 차이가 있음!
    

   

- header / body
    1.  Headers
        1. key:value 형태
        2. 추가 정보를 담고 있는 부분
        3. 다음과 같은 Header 정보가 자주 사용됨
        4. Host : 요청이 전송되는 target의 host url
        5. User-Agent(request) 혹은 Server(response) : 클라이언트 혹은 서버에 대한 정보
        6. Connection : 클라이언트와 서버 사이의 커넥션을 연속적으로 유지할 것인지 응답이 도착하면 연결을 닫는 형태로 단기로만 커넥션을 유지할 것인지 지시하는 부분
    
    2. Body
    
    해당 request 혹은 response의 실제 메시지 혹은 내용이 담겨 있음
    
- endpoint
    
    API가 서버에서 리소스에 접근할 수 있도록 가능하게 하는 URL
    
- HTTP Status code (200, 201, 400...)
    
    
    | 상태코드 |  |
    | --- | --- |
    | 200 | 클라이언트의 요청을 정상적으로 수행함 |
    | 201 | 클라이언트가 어떠한 리소스 생성을 요청, 해당 리소스가 성공적으로 생성됨(POST를 통한 리소스 생성 작업 시) |
    
    | 상태코드 |  |
    | --- | --- |
    | 400 | 클라이언트의 요청이 부적절 할 경우 사용하는 응답 코드 |
    | 401 | 클라이언트가 인증되지 않은 상태에서 보호된 리소스를 요청했을 때 사용하는 응답 코드 |
    |  | (로그인 하지 않은 유저가 로그인 했을 때, 요청 가능한 리소스를 요청했을 때) |
    | 403 | 유저 인증상태와 관계 없이 응답하고 싶지 않은 리소스를 클라이언트가 요청했을 때 사용하는 응답 코드 |
    |  | (403 보다는 400이나 404를 사용할 것을 권고. 403 자체가 리소스가 존재한다는 뜻이기 때문에) |
    | 405 | 클라이언트가 요청한 리소스에서는 사용 불가능한 Method를 이용했을 경우 사용하는 응답 코드 |
    
    | 상태코드 |  |
    | --- | --- |
    | 301 | 클라이언트가 요청한 리소스에 대한 URI가 변경 되었을 때 사용하는 응답 코드 |
    |  | (응답 시 Location header에 변경된 URI를 적어 줘야 합니다.) |
    | 500 | 서버에 문제가 있을 경우 사용하는 응답 코드 |
- HTTP Method (GET, POST, PUT, PATCH, DELETE)
    
    
    | METHOD | 역할 |
    | --- | --- |
    | POST | POST를 통해 해당 URI를 요청하면 리소스를 생성합니다. |
    | GET | GET를 통해 해당 리소스를 조회합니다. 리소스를 조회하고 해당 도큐먼트에 대한 자세한 정보를 가져온다. |
    | PUT | PUT를 통해 해당 리소스를 수정합니다. |
    | DELETE | DELETE를 통해 리소스를 삭제합니다. |