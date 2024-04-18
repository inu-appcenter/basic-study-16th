# 2주차_API/REST API란?


# 📌API란?

---

![img1 daumcdn](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/0edde49e-79a6-4c92-b265-19fe7799a4c0)

> **Application Programming Interface**의 약자로, 소프트웨어 응용 프로그램에서 **다른 소프트웨어 구성 요소 또는 서비스와 상호 작용하기 위한 인터페이스**를 제공하는 프로그래밍 기술
> 

한 단어씩 나누어 보면

- **Application**: 특정한 업무를 수행하기 위해 개발된 응용 소프트웨어
- **Programming**: 컴퓨터에 부여하는 명령을 만드는 작업. 수식이나 작업을 컴퓨터에 알맞도록 정리해서 순서를 정하고 컴퓨터 특유의 명령 코드로 고쳐쓰는 작업
- **Interface**: 사물과 사물 사이 또는 사물과 인간 사이의 경계에서, 상호 간의 소통을 위해 만들어진 물리적 매개체나 통신 규칙

종합해보면 응용 소프트웨어를 만드는 데 쓰는 매개체나 통신 규칙을 말한다고 볼 수 있다.

# 📌REST API란?

---

<img width="90%" alt="image" src="https://github.com/inu-appcenter/basic-study-16th/assets/86196038/7f684db9-d02a-4b17-8cfd-0d1ab6ecaf05">

API를 사용하다 보니 개발자마다 소통의 규칙과 메뉴얼 등이 달라 문제를 겪자 API에도 체계가 필요하다는 관점에서 REST API가 출현하였다.

> REST API란 Representational State Transfer API의 약자로, API 작동 방식에 대한 조건을 부과하는 소프트웨어 아키텍처를 말한다
> 

REST는 처음에 인터넷과 같은 복잡한 네트워크에서 통신을 관리하기 위한 지침으로 만들어졌다. REST 기반 아키텍처를 사용하여 대규모의 고성능 통신을 안정적으로 지원할 수 있다. 쉽게 구현하고 수정할 수 있어 모든 API 시스템을 파악하고 여러 플랫폼에서 사용할 수 있다. 

### REST 구성 요소

REST의 구성 요소로는 3가지가 있다.

1. 자원(Resource): URI
    - Rest API는 컴퓨터가 가지는 데이터들을 Resource라 칭한다.
    - 모든 자원에는 고유한 ID가 존재하고 이 자원은 server에 존재한다.
    - HTTP와 마찬가지로 URI로 자원을 구별한다.

   ![%EC%98%88%EC%8B%9C](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/6292db9b-9985-471c-a2b5-872dea1646dc)
    
    > Collection: example.com/topics
    > 
    > - topic이라는 정보 전체를 식별하는 uri이다. 이러한 REST API를 Collection이라고 부른다.
    > 
    > Element: example.com/topics/1
    > 
    > - topic의 정보 하나를 식별하는 uri이다. 이러한 REST API를 Element라고 부르며, Element가 모여 Collection을 이룬다.
    > - id 값을 사용하는 것이 일반적이다.
2. 행위(Verb): HTTP Method

   ![rest](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/1116897b-af9a-40a8-b3b3-57411ef87ebb)

    - HTTP 프로토콜의 Method를 사용한다.
    - HTTP 프로토콜은 GET, POST, PUT, DELETE와 같은 메서드를 제공한다.
3. 표현(Representation of Resource)
    
    Client가 자원의 상태에 대한 조작을 요청하면 Server는 이에 대한 적절한 응답(Representation)을 보낸다.
    
    REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 Representation으로 나타난다. 


![%EC%A0%95%EB%B3%B4%EA%B0%80%EA%B3%B5%EB%B0%A9%EB%B2%95](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/bd3afacc-05c6-4915-982b-2f3e0f64a3f8)

**REST API에서 Resource 가공 방법**

- 기존의 정보 가공 방법에는 CRUD 4가지가 존재한다.
- REST API에서는 이러한 정보 가공 기법을 method라 부른다.

| 기존 정보 가공 방법 | REST API에서 정보 가공 방법 | 역할 |
| --- | --- | --- |
| Create | post | 생성 |
| Read | get | 조회 |
| Update | put | 전체 내용 수정 |
| Update | patch | 부분 내용 수정 |
| Delete | delete | 삭제 |

### REST 특징

1. Server-Client(서버-클라이언트 구조)
    - 자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client가 된다.
    
    > REST Server: API를 제공하고 비즈니스 로직 처리 및 저장을 책임진다.
    Client: 사용자 인증이나 context(세션, 로그인 정보) 등을 직접 관리하고 책임진다.
    > 
    - 서로 간 의존성이 줄어든다.
2. Stateless(무상태)
    - HTTP 프로토콜은 Stateless Protocol이므로 REST 역시 무상태성을 갖는다.
    - Client의 context를 Server에 저장하지 않는다.
        - 즉, 세션, 쿠키와 같은 Context 정보를 신경 쓰지 않아도 되므로 구현이 단순해진다.
    - Server는 각각의 요청을 완전히 별개의 것으로 인식하고 처리한다.
        - 각 API 서버는 Client의 요청 만을 단순 처리하며 이전 요청이 다음 요청에 연관되어서는 안된다.
        - 단, 이전 요청이 DB를 수정하여 DB에 의하여 바뀌는 것은 허용한다.
        - Server의 처리 방식에 일관성을 부여하고 부담이 줄어들며, 서비스의 자유도가 높아진다.
3. Cacheable(캐시 처리 가능)
    - 웹 표준 HTTP 프로토콜을 그대로 사용하여 기존 웹 인프라를 그대로 활용 가능하며 HTTP가 가진 가장 강력한 특징인 캐싱 기능도 적용할 수 있다.
        - HTTP 프로토콜 표준에서 사용하는 Last-Modified 태그나 E-Tag를 이용해 캐싱 구현이 가능하다.
    - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구되는데,
    캐시 사용을 통해 응답 시간이 빨라지고 REST Server 트랜잭션이 발생하지 않기 때문에 전체 응답 시간과 성능, 서버의 자원 이용률을 향상 시킬 수 있다.
4. Layered System(계층화)
    - Client는 REST API Server만 호출한다.
    - REST Server는 다중 계층으로 구성될 수 있다.
        - API Server는 순수한 비즈니스 로직을 수행하고 앞 단에는 보안, 로드밸런싱, 암호화, 사용자 인증 등을 두어 구조 상의 유연성을 줄 수 있다.
        - 로드밸런싱, 공유 캐시 등을 통해 확장성과 보안성을 향상시킬 수 있다.
    - PROXY, 게이트웨이 같은 네트워크 기반의 중간 매체를 사용할 수 있다.
5. Code-On-Demand(optional)
    - Server로부터 스크립트를 받아서 Client에서 실행한다.
    반드시 충족할 필요는 없다.
6. Uniform Interface(인터페이스 일관성)
    - URI로 지정한 Resource에 대한 조작을 통일되고 한정적인 인터페이스로 수행한다.
    - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
        - 특정 언어나 기술에 종속되지 않는다.
        

### REST의 장단점

**장점**

- HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요가 없다.
- HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
- HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
- Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
- REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도를 쉽게 파악할 수 있다.
- 여러가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
- 서버와 클라이언트의 역할을 명확하게 분리한다.

**단점**

- 표준이 존재하지 않는다.
- 사용할 수 있는 메소드가 4가지 밖에 없다.
- HTTP Method 형태가 제한적이다.
- 브라우저를 통해 테스트할 일이 많은 서비스에서 쉽게 고칠 수 있는 URL보다 Header값을 수정하는게 더 어렵게 느껴질 수 있다.
- 구형 브라우저에서 지원되지 않는 부분이 존재한다.
- PUT과 DELETE를 사용하지 못한다.
- pushState를 지원하지 않는다.

# 📌API 용어

---

### URL / BaseURL / URI

**URI (Uniform Resource Identifier)**는 우리 말로 ‘통합 자원 식별자’이다.

Uniform은 리소스를 식별하는 통일된 방식을 말하고, Resource란 URI로 식별이 가능한 모든 종류의 자원을 지칭하며, Identifier는 다른 항목과 구분하기 위해 필요한 정보를 말한다.

즉, URI는 인터넷 상의 리소스 “자원 자체”를 식별하는 고유한 문자열 시퀀스이다.

**URL (Uniform Resource Locator)**은 네트워크 상에서 통합 자원(리소스)의 “위치”를 나타내기 위한 규약이다. 즉, 자원과 식별자의 위치를 동시에 보여준다. 

![URI_URL](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/30aefcc4-0ac9-4c55-aec0-82f7592e531b)

URI와 URL을 비교하면 **URL=식별자**, **URL=식별자+위치**로 볼 수 있다.

- inu.ac.kr은 URI이다. 리소스의 이름만 나타내기 때문이다.
- 반면 https://inu.ac.kr URL이다. 이름과 더불어, 어떻게 도달할 수 있는지 위치까지 함께 나타내기 때문이다. URL에는 프로토콜인 https도 포함된다.

**BaseUrl**

![BaseUrl_%EC%9D%B4%EB%9E%80_-_what_is_BaseUrl](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/da0c96bb-19c2-4e91-8fd4-47459fa02cb6)

baseUrl은 url을 상대 경로로 쓸 때 url 맨 앞에 붙는 주소를 의미한다.

예를 들어, url이 /post이고 baseURL이 [http://some-domain.com/api/이면](http://some-domain.com/api/이면), [http://some-domain.com/api/post로](http://some-domain.com/api/post로) 요청이 가게 된다.

### Header / Body

HTTP 메시지는 보통 Header와 Body로 이루어진다.

HTTP Header는 클라이언트와 서버가 요청 또는 응답으로 부가적인 정보를 전송할 수 있도록 한다.

대소문자를 구분하지 않는 이름과 콜론(:) 다음에 오는 값으로 이루어져 있다.

HTTP Body는 해당 요청에 대한 실제 메시지 내용을 전송한다.

헤더는 크게 요청(Request) 헤더와 응답(Response) 헤더로 나뉜다.

1. 공통 헤더(General Header)
    
    요청/응답이 생성된 날짜 및 시간 등과 같은 HTTP 통신에 대한 일반적인 정보가 포함된다. 전송되는 HTTP 본문 컨텐츠와는 관련이 없다.
    
2. 요청 / 응답 헤더 (Request / Response Header)
    
    클라이언트/브라우저가 요청을 서버로 보내고 서버가 브라우저로 응답을 보낸다.
    
    요청 헤더는 요청한 URL, 메소드 (GET, POST, HEAD), 요청 생성에 사용된 브라우저 및 기타 정보를 포함한다.
    
    응답 헤더는 컨텐츠에 사용된 인코딩, 서버 시스템에서 응답을 생성하는 데 사용되는 서버 소프트웨어 및 기타 정보를 포함한다.
    

3. 엔티티 헤더(Entity Header)

실제 메시지 또는 전송중인 HTTP 본문에 대한 정보가 포함된다. 컨텐츠 길이, 컨텐츠 언어, 인코딩, 만료 날짜 및 기타 중요한 정보와 같은 정보를 포함한다.

### Endpoint

Endpoint는 RESTful API가 사용자 인터페이스에서 서버의 리소스에 액세스 할 수 있도록 해주는 URL이다.

서비스를 사용 가능하도록 서비스에서 제공하는 커뮤니케이션 채널의 한쪽 끝을 말한다.

### HTTP Status code (HTTP 상태 코드)

HTTP/1.0에서 도입한 HTTP 상태 코드는 클라이언트가 보낸 HTTP 요청을 웹 서버가 정상적으로 처리했는지 아니면 에러가 발생했는지 여부를 알려주는 역할을 한다. 

즉, 상태 코드는 웹 서버가 HTTP 요청을 처리한 결과를 알려주는 것이다.

상태코드는 다음과 같이 5개의 그룹으로 분류한다.

![img1 daumcdn 1](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/d4a962ab-39b5-45ef-b2f5-61f6ed42d42b)

100번대 코드는 요청에 대한 처리가 계속되고 있다는 정보를 제공하며 특수한 용도 외에는 거의 사용되지 않는다.

200번대 코드는 클라이언트가 요청한 작업을 성공적으로 처리했음을 의미한다.

300번대 코드는 클라이언트가 요청한 리소스의 위치, 즉 URL이 변경되었을 경우 다른 URL로 다시 요청하도록 알려준다.

400번대 코드는 클라이언트가 보낸 요청에 오류가 있음을 의미한다.

500번대 코드는 서버 내부에서 오류가 발생한 경우 사용한다.

아래는 가장 흔하게 사용되는 상태 코드이다.

![img1 daumcdn 2](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/7b889781-d22f-467d-8eb8-d675510e519d)

현재 버전의 HTTP는 각 상태 코드 분류에 대해 적은 수의 코드만을 정의하고 있다. 코드 분류만 지킨다면 HTTP가 정의한 상태 코드를 변경하거나 독자적인 상태 코드를 만들어도 된다. 

### HTTP Method-

HTTP Method란 클라이언트 - 서버 구조에서 요청(Request)과 응답(Response)가 이루어지는 방식을 의미한다.

서버가 수행해야 할 동작을 지정하여 요청을 보내는 방법이라고 할 수 있다.

HTTP 메서드는 서버가 수행해야 할 동작을 지정하고, URI는 리소스만 식별하여 리소스와 동작을 분리할 수 있다.

HTTP Method는 크게 8가지가 있다.

![img1 daumcdn 3](https://github.com/inu-appcenter/basic-study-16th/assets/86196038/26c3f6f6-8797-48c1-adca-db94fbb345c8)

- GET: 리소스를 조회
- POST: 데이터 추가, 등록
- PUT: 리소스 대체, 수정 / 해당 리소스가 없으면 새롭게 생성
- DELETE: 리소스 삭제
- PATCH: 리소스 부분 변경 (수정)
- HEAD: GET과 동일하나, HTTP 메세지의 body 부분을 제외하고 조회
- OPTIONS: 서버와 브라우저가 통신하기 위한 통신 옵션을 확인하기 위함
    - 서버가 어떤 method, header, content-type을 제공하는지 알 수 있다.
- CONNECT: 대상 자원으로 식별되는 서버에 대한 연결 요청