
### HTTP란?

- KEYWORD
	- on demand
	- HTML
	- object
	- host name
	- path
	- Apache
	- stateless protocol

### Persistent & Non-Persistent

- KEYWORD
	- persistent connection
	- non-persistent connection
	- HTTP/1.0
		- 비지속 연결
	- RTT - round trip time
	- 3-way-handshake

- IDEA
	- HTTP 는 지속 연결과 비지속 연결을 모두 지원한다
	- RTT 란 작은 패킷(전송 시간을 무시할 수 있을 정도)이 클라이언트에서 서버까지 갔다가 다시 클라이언트로 돌아오는 데 걸리는 시간
	- HTTP 를 통해 자원 요청을 할 경우 연결 설정부터 자원 획득까지 걸리는 총 시간은 2RTT + 파일 전송 시간 이다.
	- HTTP 기본 모드는 파이프라이닝을 이용한 지속 연결을 사용한다.

### 메시지 형식

- KEYWORD
	- request message
		- request line
			- method
			- url
			- http version
		- header line
	- response message
		- status line
			- HTTP version
			- status code
			- status message
	- method
		- HEAD??
- IDEA
	- Host: 헤더 라인이 필요한 이유
		- TCP 연결에서 이미 IP, port 를 지정하지만 web proxy cache 에서 이를 필요로 한다
	- Connection: 헤더 라인
		- 지속 연결 사용 여부를 명시
	- User-agent: 헤더 라인
		- 서버에게 요청을 하고 있는 브라우저 타입을 명시한다
		- ex) Mozilla/5.0, 파이어폭스 등등
	- 헤더 라인의 끝에는 항상 \r\n 이 들어가야 한다
		- GET 요청일지라도 헤더의 끝을 알리는 \r\n 이 한 번 더 들어가줘야 한다

### 쿠키

- KEYWORD
	- HTTP server - stateless
	- cookie
		- HTTP request message Cookie header line
		- HTTP response message Cookie header line
		- user browser Cookie file
		- BE DB
	- response
		- Set-cookie: 1678
	- request
		- Cookie: 1678
- IDEA
	- 쿠키는 비상태 HTTP 위에 사용자 세션 계층을 생성하는 데 이용될 수 있다
	- 3rd party 쿠키는 referer header 를 통해 사용자의 브라우징 히스토리를 염탐할 수 있다

### Cache

- KEYWORD
	- proxy server
	- origin server
	- local web cache
	- conditional GET
	- hit rate
	- 304 Not Modified
- IDEA
	- 캐시 서버는 보통 ISP 가 설치한다
	- conditional GET 은 캐시 서버가 본인이 가진 캐시의 modified 정보를 확인해 최신화 여부에 따라 응답 포함 여부를 결정하는 방식이다

### HTTP/2

- KEYWORD
	- HOL blocking
	- framing
	- interleaving
	- message prioritization
	- server side push
	- stream
	- HTTP/3
- IDEA
	- HTTP/1.1 브라우저에서는 여러 개의 병렬 TCP 연결을 열어서 HOL 블로킹 문제를 해결했다
		- 이렇게 하면 하나의 페이지를 불러오려는 시도가 링크의 대역폭을 좀 더 많이 할당 받을 수 있게 된다
	- HTTP/1.1 이 TCP 위에서 동작하는 경우 순서 보장을 하는 과정에서 loss 회복을 하느라 뒤에 추가로 잘 도착한 데이터들을 애플리케이션에게 전달하지 못하는 병목이 발생할 수 있다
	- HTTP/3 는 application layer protocol 인 QUIC 위에서 동작하는 프로토콜이며 UDP 위에서 동작한다
		- 더 세밀한 보안과 오류, 흐름 제어를 제공한다