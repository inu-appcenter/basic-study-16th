### 1. API란?
- Application Programming Interface의 약자
- 정의 및 프로토콜 집합을 사용하여 두 소프트웨어 구성 요소가 서로 통신할 수 있게 하는 메커니즘
- ex) tv와 통신하기 위해 tv에 정의된 규격에 의해 어떤 신호를 보낼 수 있도록 해주는 리모콘
<hr>

### 2. REST API란?

- REST의 의미
	- REpresentational State Transfer의 줄임말
	- 클라이언트가 서버 데이터에 액세스하는데 사용할 수 있는 GET, PUT, DELETE 등의 함수 집합을 정의함

- REST 구성 요소/특징
	1. 자원(Resource) : HTTP URI
		- 모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재함
		- 자원을 구별하는 ID는  `/orders/order_id/1`  와 같은 HTTP URI. 이 URI는 해당 자원을 가리킴

	2. 자원에 대한 행위(Verb) : HTTP Method
		-   HTTP 프로토콜의 Method를 사용함
		-   HTTP 프로토콜은  `GET`,  `POST`,  `PUT`,  `DELETE`와 같은 메서드를 제공함

	3. 자원에 대한 행위의 내용 (Representations) : HTTP Message Pay Load
		-   Client가 자원의 상태 (정보)에 대한 조작을 요청하면 Server는 이에 적절한 응답 (Representation)을 보냄
		-   REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 Representation으로 나타낼 수 있음
		-   현재는 JSON으로 주고 받는 것이 대부분

- REST의 장단점
	- 장점
		-   HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요가 없음
		-   HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해줌
		-   HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능
		-   Hypermedia API의 기본을 충실히 지키면서 범용성을 보장함
		-   REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있음
		-   여러 가지 서비스 디자인에서 생길 수 있는 문제를 최소화함
		-   서버와 클라이언트의 역할을 명확하게 분리함

	- 단점
		-   표준이 자체가 존재하지 않아 정의가 필요함
		-   HTTP Method 형태가 제한적임
		-   브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구됨
<hr>

### 3. API에서 사용하는 용어들

-   **URL / BaseURL / URI**
	- URL (Uniform Resource Locator)
	    - URL은 웹 상에서 특정 자원의 위치를 나타내는 문자열 
	    - 프로토콜(일반적으로 HTTP 또는 HTTPS), 호스트(도메인 이름 또는 IP 주소), 자원 경로를 포함함
	    -   ex) "https://api.naver.com/users"는 "api.naver.com" 호스트에서 "users"라는 자원을 찾기 위한 URL임

	- Base URL
	    - Base URL은 API 엔드포인트의 기본 경로를 나타냄
	    - API에서 모든 요청의 기본이 되는 경로
	    - ex) "https://api.naver.com"이 Base URL이고, 이 URL을 기준으로 모든 API 요청이 이루어짐. 각 엔드포인트의 경로는 Base URL 뒤에 추가됨

	- URI (Uniform Resource Identifier)
	    -   URI는 리소스를 식별하는 데 사용되는 문자열. URL은 URI의 하위 개념으로, URI는 URL과 URN(Universal Resource Name)을 모두 포함함.
	    -   URI는 프로토콜, 호스트, 경로 등을 포함하여 리소스를 고유하게 식별함. URI는 리소스의 위치와 이름을 나타낼 수 있음
	    -   ex) "https://api.naver.com/users"는 "https://api.naver.com" Base URL과 "/users" 경로를 포함하는 URI임

-   **header / body**
	- header
		- 요청이나 응답에 대한 부가적인 정보를 포함함. 이 정보는 키-값 쌍으로 구성되며, 요청이나 응답의 속성을 지정하거나 제어하는 데 사용됨
			-   요청 header
				- 클라이언트가 서버로 보내는 추가 정보를 포함
			-   응답 header
				- 서버가 클라이언트로 보내는 응답에 대한 부가적인 정보를 포함
	- body
		- 메시지의 주요 컨텐츠를 포함. 
			- 요청 body은 클라이언트가 서버로 보내는 데이터를 포함. POST 또는 PUT 요청과 함께 보내는 데이터는 대부분 요청 body에 포함
			- 응답 body은 서버가 클라이언트로 보내는 데이터를 포함. 서버는 클라이언트가 요청한 작업에 대한 결과를 응답 body에 포함하여 클라이언트에게 제공

-   **endpoint**
	- API가 제공하는 특정 리소스나 기능에 대한 경로 또는 URL

	- ex) 사용자 정보 얻기 위한 엔드포인트
		- https://api.naver.com/users/{user_id}
<br>

-   **HTTP Status code (200, 201, 400...)**
	- 1xx(정보)
		- 100 Continue
			- 지금까지의 상태가 괜찮으며 클라이언트가 계속해서 요청을 하거나 이미 요청을 완료한 경우에는 무시해도 되는 것을 알려줌
	- 2xx(성공)
		- 200 OK
			- 성공적으로 처리함
		- 201 Created
			- 요청이 성공적으로 처리되어 리소스가 만들어짐
		- 202 Accepted
			- 요청이 받아들여졌지만 처리되지 않음
	- 3xx(리다이렉션)
		- 301 Moved Permanently
			- 영구적으로 컨텐츠가 이동했을 때 사용
		- 302 Found
			- 일시적으로 컨텐츠가 이동했을 때 사용
		- 304 Not Modified
			- 요청한 자원이 변경되지 않았으므로 클라이언트에서 캐시된 자원을 사용하도록 권함
	- 4xx(클라이언트 오류)
		- 400 Bad Request
			- 요청 자체가 잘못되었을 때 사용
		- 401 Unauthorized
			- 인증이 필요한 리소스에 인증 없이 접근할 경우 발생
		- 403 Forbidden
			- 서버가 요청을 거부할 때 발생한다. 관리자가 해당 사용자를 차단 or 서버에 index.html 이 없을 때 or 권한이 없을 때 발생
		- 404 Not Found
			- 찾는 리소스가 없다는 뜻
		- 408 Request Timeout
			- 요청 중 시간이 초과되었을 때 사용
	- 5xx(서버 오류)
		- 502 Bad Gateway
			- 연결된 서버로부터 잘못된 응답을 받았을 때 사용
		- 503 Service Temporarily Unavailable
			- 서비스를 일시적으로 사용할 수 없을 때 사용
			- 주로 웹서버 등이 과부하로 다운되었을 때 볼 수 있음
		- 504 Gateway Timeout
			- 연결된 서버로부터 응답을 받을 수 없었을 때 사용
<br>

-   **HTTP Method (GET, POST, PUT, PATCH, DELETE)**
	-   `GET`: 리소스 조회  
	-   `POST`: 요청 데이터 처리, 주로 등록에 사용
	-   `PUT`: 리소스를 대체, 해당 리소스가 없으면 생성
	-   `PATCH`: 리소스 부분 변경
	-   `DELETE`: 리소스 삭제
<hr>