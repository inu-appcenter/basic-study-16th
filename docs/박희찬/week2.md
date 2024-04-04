# API란?
- API : Application Programming Interface
- 소프트웨어간 데이터를 통심을 위한 연결 요소
- 소프트웨어끼리 정해진 규칙을 약속하고 지키며 통신한다.

- Rest API, Websocket API이 있다.

# REST API란?
- REST API : 클라이언트가 서버에 요청을 보내고 <br>
서버는 내부 함수를 거쳐 결과를 클라이언트에게 전송한다.
- 클라이언트는 URL과 HTTP Method를 사용해서 서버에 원하는 요청을 보낼 수 있다.
- REST API는 기존 HTTP 웹 표준을 그대로 따른다. 즉 웹에서 사용하는 인프라를 모두 사용 할 수 있다.
- REST의 장점
  1. 웹 인프라를 그대로 사용해서 쉽다.
  2. 서버와 클라이언트가 분리되어있다. 서로에게 관심이 없다.
- REST의 단점
  1. HTTP Method가 제한되어 있다.
  2. 표준이 없다.

# API에서 사용하는 용어들
url / baseurl / uri
header / body
endpoint
HTTP Status code (200, 201, 400...)
HTTP Method (GET, POST, PUT, PATCH, DELETE)