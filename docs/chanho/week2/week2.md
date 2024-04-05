# 기초 스터디 2주차

# API란?

API란 Application Programming Interface의 약자로 응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 **인터페이스**를 뜻한다.

> 인터페이스란?
> _서로 다른 장치나 사람 또는 사물 2개 이상의 무언가를 이어주는 매개체
> (ex: 마우스, 모니터 등등)_

즉, API는 어떤 응용 프로그램에서 데이터를 주고 받기 위한 방법으로써 어떤 특정 사이트에서 특정 데이터를 공유할 경우에 어떠한 방식으로 정보를 요청해야 하는지, 그리고 어떠한 데이터를 제공 받을 수 있을 지에 대한 규격을 의미한다.

API는 오픈 API와 비공개 API가 있다. 오픈 API는 누구나 쉽게 접근해 정보를 공유하기 위해 만들어진 규격이고, 비공개 API는 권한이 있는 일부 사용자들에게만 정보를 제공하기 위해 만들어진 규격이다.

---

# REST API란?

---

REST API란 REST 기반의 API로 클라이언트와 서버 간의 두 컴퓨터 시스템이 인터넷을 통해 정보를 안전하게 교환하기 위해 사용하는 인터페이스

REST API 설계 기본 규칙

- 도큐먼트 : 객체 인스턴스나 데이터베이스 레코드와 유사한 개념
- 컬렉션 : 서버에서 관리하는 디렉터리라는 리소스
- 스토어 : 클라이언트에서 관리하는 리소스 저장

> REST란?
> Representational State Transfer의 약자로 HTTP 프로토콜을 통해 API를 설계하기 위한 아키텍쳐 스타일이다. 뛰어난 유연셩이 이점이다.
> (ex: HTTP URI, HTTP Method(POST, GET, PUT, DELETE, PATCH 등)

![Untitled](/week2/week2.png)

## REST의 구성요소

---

1. **자원(Resource) : HTTP URI**
   - 모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재한다.
   - 자원을 구별하는 ID는 ‘/groups/:group_id’와 같은 HTTP URI이고 Client는 URI를 이용해서 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.
2. **행위(Verb) : HTTP Method**
   - HTTP 프로토콜의 Method를 사용한다.
   - HTTP 프로토콜은 GET, POST, PUT, DELETE와 같은 메서드를 제공한다.
3. **표현(Representation of Resource)**
   - Client가 자원의 상태에 대한 조작을 요청하면 Server는 이에 적절한 응답(Representation)을 보낸다.
   - REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 응답을 받을 수 있다.
   - 주로 JSON이나 XML을 통해 주고 받는다.

## REST의 특징

---

1.  **Uniform (유니폼 인터페이스)**

    Uniform Interface는 URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일을 말합니다.

2.  **Stateless (무상태성)**

    REST는 무상태성 성격을 갖습니다. 다시 말해 작업을 위한 상태정보를 따로 저장하고 관리하지 않습니다. 세션 정보나 쿠키정보를 별도로 저장하고 관리하지 않기 때문에 API 서버는 들어오는 요청만을 단순히 처리하면 됩니다. 때문에 서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해집니다.

3.  **Cacheable (캐시 가능)**

    REST의 가장 큰 특징 중 하나는 HTTP라는 기존 웹표준을 그대로 사용하기 때문에, 웹에서 사용하는 기존 인프라를 그대로 활용이 가능합니다. 따라서 HTTP가 가진 캐싱 기능이 적용 가능합니다. HTTP 프로토콜 표준에서 사용하는 Last-Modified태그나 E-Tag를 이용하면 캐싱 구현이 가능합니다.

4.  **Self-descriptiveness (자체 표현 구조)**

    REST의 또 다른 큰 특징 중 하나는 REST API 메시지만 보고도 이를 쉽게 이해 할 수 있는 자체 표현 구조로 되어 있다는 것입니다.

5.  **Client - Server 구조**

    REST 서버는 API 제공, 클라이언트는 사용자 인증이나 컨텍스트(세션, 로그인 정보)등을 직접 관리하는 구조로 각각의 역할이 확실히 구분되기 때문에yddyde 클라이언트와 서버에서 개발해야 할 내용이 명확해지고 서로간 의존성이 줄어들게 됩니다.

6.  **계층형 구조**

    REST 서버는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있고 PROXY, 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 합니다.

## REST의 장단점

---

### **장점**

- HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요가 없다.
- HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
- HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
- Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
- REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
- 여러가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
- 서버와 클라이언트의 역할을 명확하게 분리한다.

### **단점**

- 표준이 존재하지 않는다.
- 사용할 수 있는 메소드가 4가지 밖에 없다.HTTP Method 형태가 제한적이다.
- 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 값이 왠지 더 어렵게 느껴진다.
- 구형 브라우저가 아직 제대로 지원해주지 못하는 부분이 존재한다..

ex) PUT, DELETE를 사용하지 못하는 점

ex) pushState를 지원하지 않는 점

# API에서 사용하는 용어들

---

### url / base url / uri

- url :
  - Uniform Resource Locator의 약자로 Resource의 정확한 위치 정보(파일의 위치)를 나타낸다.
    url을 통해 Resource가 어디에 있는지 어떻게 접근할 수 있는 지 알 수 있다.
  - (ex : [https://www.youtube.com/feed/history](https://www.youtube.com/feed/history) = 유튜브 시청 기록 URL)
- base url :
  - 웹 사이트나 웹 애플리케이션에서 사용되는 기본 url을 나타낸다.
  - (ex : [https://www.youtube.com/feed/history/](https://www.youtube.com/feed/history/2) 여기서 [https://www.youtube.com](https://www.youtube.com/feed/history/2)가 base url이다.)
- uri :
  - 자원의 위치 뿐만 아니라 자원에 대한 고유 식별자로 url을 포함한다.
  - uri의 하위 개념으로는 url과 urn이 있다. 따라서 모든 url은 uri이지만 모든 uri가 url은 아니다.
  > **urn이란?**
  > 리소스 위치와 상관없이 이름 만으로 식별할 수 있다는 개념
  > urn은 url의 한계로 인해 생긴 것이지만 url이 대중화가 되어 채택되지 못함
  > url의 한계 : 리소스 위치 변경 시 url 사용 불가
  - uri는 통합 자원 식별자로 주소에 식별자가 있으면 uri이다.
  - url은 리소스 주소를 나타내므로 리소스 위치까지만 있으면 url이다.
  - (ex 1 : [https://www.youtube.com/feed/history](https://www.youtube.com/feed/history) 여기서 유튜브의 feed 경로 안에 있는 history 경로를 나타낸다. category는 리소스의 실제 위치이므로 이 주소는 url이다.)
  - (ex 2 : [https://www.youtube.com/feed/history/12](https://www.youtube.com/feed/history/2) 여기서 category라는 자원의 경로를 나타내는 부분까지는 url이지만 [/12](https://www.youtube.com/feed/history/2)는 식별자이므로 url을 포함한 uri라고 할 수 있다.)

### header / body

HTTP 통신을 사용하면 클라이언트와 서버 간에 두 가지 유형의 메시지(HTTP 요청 및 HTTP 응답)를 전송할 수 있다.

클라이언트/브라우저가 요청을 서버로 보내고 서버가 브라우저로 응답을 보낸다. 두 메시지는 공통 포맷을 가지고 있고, HTTP header와 HTTP body를 포함한다.

- header :
  - 일반 헤더 : 본문 컨텐츠와 관련 없이 요청/응답이 생성된 날짜 및 시간 등과 같은 일반적인 정보가 포함된다. 요청과 응답 모드에 공통적으로 사용된다.
  - 요청 / 응답 헤더 : 요청을 할 때는 요청 헤더가 있고 응답을 보낼 때는 응답 헤도가 있다.
    - 요청 헤더 : 요청한 URL, 메소드(GET, POST, HEAD). 요청 생성에 사용된 브라우저 및 기타 정보와 같은 요청에 대한 정보가 포함된다.
    - 응답 헤더 : 컨텐츠에 사용된 인코딩, 서버 시스템에서 응답을 생성하는 데 사용되는 서버 소프트웨어 및 기타 정보가 포함된다.
  - 엔티티 헤더 : 실제 메시지 또는 정송중인 HTTP 본문에 대한 정보가 포함된다. (컨텐츠 길이, 컨텐츠 언어, 인코딩, 만료 날짜 및 기타 중요한 정보 등)
- body : 가져 올 실제 데이터 컨텐츠/메시지 본문이 나타난다. 컨텐츠에는 요청한 리소스에 따라서 HTML코드, 이미지, CSS 스타일 시트 JavaScript 파일 등이 포함될 수 있다.

### endpoint

- endpoint :
  - endpoint는 API가 RESTful API를 인터페이스를 통해 서버의 리소스에 액세스 할 수 있도록 해주는 URL이다.

### HTTP Status code

- 1xx(정보) : 요청을 받았으며 프로세스를 계속 진행한다.
- 2xx(성공) : 요청을 성공적으로 받았으며 인식했고 수용했다.
- 3xx(리다이렉션) : 요청 완료를 위해 추가 작업 조치가 필요하다.
- 4xx(클라이언트 오류) : 요청의 문법이 잘못되었거나 요청을 처리할 수 없다.
- 5xx(서버 오류) : 서버가 명백히 유효한 요청에 대한 충족을 실패했다.

### HTTP Method (GET, POST, PUT, PATCH, DELETE)

- **GET :**
  - 리소스를 조회하는 메소드이다.
  - 멱등성이라는 개념을 지니고 있어, 여러번 조회 요청을 하여도 리소스는 변하지 않는다.
  - 서버에 데이터를 전달하는 경우에는 쿼리스트링을 통해서 전달한다.
  - (ex : [https://search.naver.com/search.naver?where=nexearch&sm=top_hty&fbm=0&ie=utf8&query=안드로이드](https://search.naver.com/search.naver?where=nexearch&sm=top_hty&fbm=0&ie=utf8&query=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C) 에서 query=안드로이드가 이에 해당한다.)
- **POST :**
  - 주로 새로운 리소스를 생성하는데 사용된다.
  - 성공적으로 완료하면 201 HTTP응답을 반환한다.
  - 데이터를 메시지 바디에 쿼리 파라미터 형식으로 전달한다.(key-value)
  - 데이터가 외부로 노출되지 않기에 보안상 이점이 존재한다.
- **PUT :**
  - 리소스를 완전히 대체하는 개념(덮어쓰기)
  - 클라이언트가 리소스를 식별할 수 있다.
    - (ex : PUT /posts/1 = 1번 게시글 수정 요청)
  - 부분 수정이 불가능
    - (ex : A, B 존재할 때 PUT으로 C를 보낼 경우 A, B 모두 삭제되고 C로 대체)
  - 멱등성을 지님
- **PATCH :**
  - PUT과 같이 리소스를 수정하는 역할을 하지만, 리소슬르 부분 수정한다는 점에서 차이가 존재
    - (ex : A, B 존재할 때 PATCH로 B=C를 요청하면 데이터가 A, C로 변경된다.)
  - 멱등성을 지니지 않음
- **DELETE :**
  - 리소스를 제거하는 역할이다.
  - 멱등성을 지님

> **멱등성**
> 동일한 요청을 한 번 보내는 것과 여러 번 연속으로 보내는 것이 같은 효과를 지니고, 서버의 상태도 동일하게 남을 때, 해당 HTTP 메소드가 멱등성을 가졌다고 말한다.

# 추가 : RESTful

---

## RESTful이란

- RESTful은 일반적으로 REST라는 아키텍처를 구현하는 웹 서비스를 나타내기 위해 사용되는 용어이다.
- RESTful은 REST를 REST답게 쓰기 위한 방법으로, 누군가가 공식적으로 발표한 것은 아니다.
  - 즉, REST원리를 따르는 시스템은 RESTful이란 용어로 지칭된다.

## RESTful의 목적

- 이해하기 쉽고 사용하기 쉬운 REST API를 만드는 것
- RESTful한 API를 구현하는 근본적인 목적이 성능 향상에 있는 것이 아니라 일관적인 컨벤션을 통한 API의 이해도 및 호환성을 높이는 것이 주 동기이니, 성능이 중요한 상황에서는 굳이 RESTful한 API를 구현할 필요는 없다.
- RESTful 하지 못한 경우
  - (ex 1: CRUD 기능을 모두 POST로만 처리하는 API)
  - (ex 2: route에 resource, id 외의 정보가 들어가는 경우 (/students/updateName))
