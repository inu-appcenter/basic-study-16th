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
- url : 웹에서 리소스(html파일, 이미지 등..)에 접근하기 위한 주소
- base url : URL의 기본 경로, 도메인과 포트등
  - 예시 : url이 https://api.kichan.dev/blog/1 이라면 https://api.kichan.dev까지가 base url이다.
- uri : 리소스 각각의 고유한 식별자
- header : kay-value의 구조로 이루어졌고, 클라이언트와 서버가 통신할때 추가정보를 담고있는 부분이다.
- body : JSON형식의 데이터로, 요청과 응답에서 실제 데이터, 메시지르 담고있다.
- endpoint : 클라이언트가 서버에 요청보내는 약속된 URL
- HTTP Status code : 통신의 결과가 어떤지 보여주는 숫자 (200, 404, 502 등)
  - 100번대 : 서버에서 아직 처리중
  - 200번대 : 통신 성공
  - 300번대 : 통신을 완료하려면 추가 동작이 필요하다.
  - 400번대 : 클라이언트측 오류
  - 500번대 : 서버측 오류
- HTTP Method
  - GET : 서버에 데이터를 읽는 요청
  - POST : 서버에 데이터를 생성하는 요청
  - PUT : 서버에 데이터를 수정하는 요청
  - PATCH : 서버에 데이터의 일부만 수정하는 요청
  - DELETE : 서버에 데이터를 삭제하는 요청