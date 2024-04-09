## API란?

Application Programming Interface ( 응용프로그램 프로그래밍 인터페이스) 의 줄임말이다. 

응용프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스를 뜻한다. 

즉, 어떠한 응용 프로그램에서 데이터를 주고받기 위한 방법을 의미한다. 어떤 특정 사이트에서 특정 데이터를 공유할 경우 어떠한 방식으로 정보를 요청해야 하는지, 그리고 어떠한 데이터를 제공 받을 수 있을지에 대한 규격들을 API라고 한다. 

<p align="center"><img src=“https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcqVfU6%2Fbtsc0qfbK4O%2FgqZx5mfuqmwpmP1ziLKfG1%2Fimg.webp” width=”300” height=”100” ></p>

## REST API

- REST의 의미
    
    REST(Representational State Transfer)의 약자로 `자원`을 이름으로 구분하여 해당 ******`자원의 상태를 주고받는 모든 것`을 의미한다. 웹에서 데이터를 전송하고, 처리하는 방법을 정의한 인터페이스라고도 설명할 수 있다. 
    
    <p align="center"><img src="https://res.cloudinary.com/practicaldev/image/fetch/s--YTDTEgpk--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/ekawmj3rafdtn06hzj79png" width="400" height="300"></p>
    
    자원, 즉 문서, 사진, 그림, 데이터 등 소프트웨어가 관리하는 모든 것을 HTTP URI(Uniform Resource Identifier)를 통해 명시한다. 
    
    예를 들어 DB의 영화 정보가 자원일 때, /movies를 자원의 표현으로 정할 수 있다. 
    
    <p align="center"><<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fb8CMjS%2FbtscYWlqbSJ%2FizcMPJRhSP5kXLxhJOqmU1%2Fimg.png" width="200" height="80"></p>
    
    또한, 클라이언트는 데이터가 요청되어지는 시점에서 자원의 상태(정보=Pay Load)를 전달한다. 
    
    서버는 이에 응답하여 상태에 대한 조작에 대한 결과물을 JSON 이나 XML을 통해 클라이언트측으로 전달한다.  
     
    
    ***즉, REST는 HTTP URI를 통해 Client 와 Server 사이의 통신하는 방식 중 하나로, HTTP Method를 통해 자원을 처리하도록 설계된 아키텍처를 말한다***
    
- REST 구성요소
    - **자원 (Resource) : HTTP URI**
        
        모든 자원에 고유한 ID가 존재하고, 이 자원은 서버에 존재한다. 
        
        ID는 ‘/groups/:group_id’와 같이 HTTP URI로 이루어져 있고, 클라이언트는 이 URI를 통해 자원을 지정하고, 해당 자원의 상태에 대한 조작을 서버 측에 요청한다. 
        
    - **자원에 대한 행위 (Verb) : HTTP Method**
        
        HTTP 프로토콜의 Method를 사용한다. 
        
        HTTP 프로토콜을 GET, POST, PUT, DELETE와 같은 메서드를 제공한다 .
        
    - **표현 (Representations)  : HTTP Message Pay Load**
        
        클라이언트가 상태(정보)에 대한 조작을 요청하면 서버는 이에 적절한 응답(Representation)을 보낸다.  전달 방식으로는 주로 JSON 이나 XML를 통해 데이터를 주고 받는다. 
        
- REST의 특징
    1. 인터페이스 일관성 (Uniform Interface) 
        
        HTTP 표준에만 따른다면, 특정 언어나 기술에 종속되지 않고, 모든 플랫폼에 사용할 수 있다. URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일이다. 
        
    2. 무상태성 (Stateless)
        
        작업을 위한 상태정보를 따로 저장하고 관리하지 않는다. 세션 정보나, 쿠키정보를 별도로 저장하고 관리하지 않기 때문에 API서버는 들어오는 요청 만을 단순히 처리하면 된다. 
        
        때문에 서비스의 자유도가 높아지고, 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해진다. 
        
    3. 캐시 가능 (Cache)
        
        REST의 가장 큰 특징 중 하나는 HTTP라는 기존 웹표준을 그대로 사용하기 때문에, 웹에서 사용하는 기존 인프라를 그대로 활용이 가능하다. 따라서 HTTP가 가진 캐싱 기능이 적용 가능하고, 대량의 요청을 효율적으로 처리 가능하다. 
        
    4. Server-Client 구조
        
        REST서버는 API제공, 클라이언트는 사용자 인증이나 컨텍스트(세션, 로그인, 정보)등을 직접 관리하는 구조로 각각의 역할이 확실히 구분되기 때문에 클라이언트와 서버에서 개발해야 할 내용이 명확해지고 서로 간의 의존성이 줄어들게 된다. 
        
    5. 계층형 구조 
        
        REST 서버는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있고 PROXY, 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 한다. 
        
    6. 자체 표현 구조
        
        REST API 메세지만 보고도 이를 쉽게 이해할 수 있는 자체 표현 구조로 되어있다. 
        

- REST 의 장단점
    
    ✅ 장점
    
    - HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없다.
    - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
    - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
    - 서버와 클라이언트의 역할을 명확하게 분리한다.
    
    ✅ 단점
    
    - 표준이 존재하지 않는다.
    - HTTP Method 형태가 제한적이다.
    - 구형 브라우저에서 호환이 되지 않아 지원해주지 못하는 동작이 많다.  ( 익스플로어)
    - 브라우저를 통해 쉽게 고칠 수 있는 URL보다 Header정보의 값을 처리해야 하므로 전문성이 요구된다.

### REST API, RESTful API

❔ REST API 란

REST의 원리를 따르는 API를 의미한다. 다만, REST API를 올바르게 설계하기 위해서는 몇가지 규칙이 따른다. 

- URI는 동사보다는 명사를 , 대문자 보다는 소문자를 사용하여야 한다.

```
(X) http://everywin.com/Running  
(O) http://everywin.com/run
```

- 마지막 슬래시를 포함하지 않는다.

```
(X) http://everywin.com/Test/
(O) http://everywin.com/test
```

- 언더바 대신 하이픈을 사용한다. ( 공백을 제거한다)

```
(X) http://everywin.com/test_blog
(O) http://everywin.com/test-blog
```

- 행위를 포함하지 않는다

```
(X) http://everywin.com/select-post/1
(O) http://everywin.com/post/1
```

- 파일 확장자는 URI에 포함하지 않는다. (.jpg, .png …)

❔ RESTful API 란

기본적으로 REST의 원리를 따르는 시스템을 의미한다. 그러나, REST의 원리를 따른  모든 API를 RESTful API 라고 하지 않는다. 위에 작성한 몇 가지 설계 규칙을 올바르게  지킨 시스템을 RESTful 하다고 하며, 이를 RESTful API 라고 한다. 

모든 CRUD 기능을 POST로 처리하거나, URI 규칙을 올바르게 지키지 않은 API는 REST API를 사용하였지만, RESTful 하지 못한 API라고 할 수 있다. 

## API에서 사용하는 용어들


### URL /BaseURL / URI

- URL (Uniform Resource Locator)
    
    Resource의 정확한 위치 정보(파일의 위치)를 나타낸다. 
    
    우리는 URL을 통해 Resource가 어디에 있는지 어떻게 접근할 수 있는지 알 수 있다. 
    
    URL 에는 통신프로토콜, 도메인 또는 IP주소, 웹서버의 포트번호, 웹서버의 루트디렉토리부터의 파일 위치 경로, 쿼리문 등이 존재한다. 
    
    ex) https://www.google.com 
    
- BaseURL
    
    사이트가 존재하는 도메인의 상대적인 기본경로를 뜻한다. 
    
- URI (Uniform Resource Identifier)
    
    자윈의 위치뿐만 아니라 자원에 대한 고유 식별자로써 URL의 의미를 포함한다. 
    
    웹 기술에서 사용하는 논리적 또는 물리적 리소스를 식별하는 고유한 문자열 시퀀스다. 
    
    URL vs URI
   
    <p align="center"><img src="https://www.guru99.com/images/2/022220_0627_URLvsURIMos2.png"></p>
    
    위의 사진과 같이 “your name”이 “hyeonseung”이라고 하자. 이는 고유한 문자열이고, 식별 가능한 문자열이다. 따라서 URI 가 될 수 있다. 그러나, 이름만 가지고는 집 위치를 알 수 는 없기에, URL은 될 수 없다. 
    
    반면, 집 위치는 URL 뿐만 아니라 URI가 될 수도 있다. 그 이유는 “집 위치”는 “hyeonseung”를 식별할 수 있고, 위치도 제공하기 때문이다. 
    
    - https://hstory0208.tistory.com/catagory
        
        리소스의 실제 위치 ⇒ URL
        
    - https://hstory0208.tistory.com/catagory/12
        
        /12 는 식별자 ⇒ URL을 포함한 URI
        
    - https://hstory0208.tistory.com/category?page=12
        
        query ( ?page=12) ⇒ URL을 포함한 URI  
        

### header / body

HTTP 헤더 

- key: value 형태로 되어 있으면, 추가 정보를 담고 있는 부분이다. 다음과 같은 header 정보가 자주 사용된다.
    - Host : 요청이 전송되는 타겟의 Host Url 을 담고 있다.
    - User-Agent OR Server : 클라이언트면 Request, 서버면 Response 에 대한 정보
    - Connection : 클라이언트와 서버 사이의 커넥션을 연속적으로 유지할 것 인지, 응답이 도착하면 연결을 닫는 형태로 커넥션을 단기 유지할 것인지 지시하는 부분이다.
    - Content-Type: Body의 타입을 의미한다. json 형태로 주고 받는다면, application/json 값을 갖는다.
    - Content-Length : Body의 길이를 나타낸다.

HTTP 바디

- 해당 Request 혹은 Response 의 내용이 담겨있다.  JSON 형식으로 데이터를 보낸다면 다음과 같이 보낼 수 있다.

```
{
    "userId": "keepcalm",
    "message": "hello, world",
    "status": "noraml"
}
```

### Endpoint

endpoint란 정보를 얻어오는 위치이다. API가 서버에서 특정 작업을 수행하기 위해 접근할 수 있는 특정 URI를 가리킨다. 

 예를 들어 특정 유저의 정보를 조회하고자 할 때 `api_site.com/{apikey}` 형식의 API가 있고, 여기에 파라미터를 포함해서 요청을 보낸 `api_site.com/{apikey}/users/{userId}/infos` 라는 구체적인 URL이 Endpoint인 셈이다. 

### HTTP Method

- `GET`  :데이터를 서버에서 받아올 때 사용되는 메소드
- `PUT` : 데이터를 수정 및 생성할 때 사용되는 메소드. 주로 데이터 전체를 수정할 때 사용한다.
- `POST`: 데이터를 수정 및 생성할 때 사용되는 메소드. 주로 데이터를 수정, 생성하기 때문에 request body을 담아서 보내는 경우가 많다.
- `DELETE`: 현재 리소스(Document)를 삭제
- `PATCH` : 데이터를 수정할 때 사용되는 메소드. PUT과의 차이점은, PUT은 자원의 모든 것을 업데이트하고, PATCH는 자원의 일부분을 업데이트한다.

### HTTP Status code

✅ **1XX (정보)** 

- 임시 응답으로 현재 클라이언트의 요청까지는 처리되었으니 계속 진행하라는 의미이다.
- 100 (Continue)  : 계속 진행하라는 의미

✅ **2XX (성공)** 

- 클라이언트의 요청이 서버에서 성공적으로 처리되었다는 의미이다.
- 200 (OK) : 서버가 요청을 성공적으로 처리하였다.
- 201 (Created) : 요청이 처리되어서 새로운 리소스가 생성되었다.
- 202 (Accepted) : 요청은 접수하였지만, 처리가 완료되지 않았다.

✅ **3XX (리다이렉션)** 

- 완전한 처리를 위해 추가 동작이 필요한 경우이다. 주로 서버의 주소 또는 요청한 URI의 웹문서가 이동되었으니 그 주소로 다시 시도하라는 의미이다.
- 301 (Moved Permanently) : 지정한 리소스가 새로운 URI로 이동하였다.
- 303 (See Other) : 다른 위치로 요청한다.
- 3077 (Temporary Redirect) : 임시로 리다이렉션 요청이 필요하다.

✅ **4XX(클라이언트 오류)** 

- 없는 페이지를 요청하는 등 클라이언트의 요청 메시지 내용이 잘못된 경우를 의미한다.
- 400 ( Bad Request) : 요청의 구문이 잘못되었다.
- 401 ( Unauthorized) : 지정한 리소스에 대한 엑세스 권한이 없다.
- 403 ( Forbidden) : 지정한 리소스에 대한 엑세스가 금지되었다.
- 404 ( Not Found) : 지정한 리소스를 찾을 수 없다.

✅ **5XX(서버 오류)** 

- 서버 사정으로 메시지 처리에 문제가 발생한 경우이다. 서버의 부하, DB처리 과정 오류 , 서버에서 익셉션이 발생하는 경우를 의미한다.
- 500 ( Internal Server Error ) : 서버에 에러가 발생하였다.
- 501 ( Not Implemented) : 요청한 URI의 메소드에 대해 서버가 구현하고 있지 않다.
- 502 ( Bad Gateway) : 게이트웨이 또는 프록시 역할을 하는 서버가 그 뒷단의 서버로부터 잘못된 응답을 받았다.