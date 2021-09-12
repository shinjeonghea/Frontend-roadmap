# HTTP

:writing_hand: *write by shinjeonghea*


## HTTP

<img src="https://mdn.mozillademos.org/files/13673/HTTP%20&%20layers.png" width=400>

- HyperText Transfer Protocol의 약자
- **W3(World Wide Web) 상에서 정보를 주고받을 수 있는 프로토콜**
  - **클라이언트 - 서버 사이의 요청/응답 프로토콜**
- 주로 HTML 문서를 주고받는다.
- 연결상태를 유지하지 않는 **Stateless 프로토콜** (이후, 단점 해결을 위해 [Cookie와 Session](https://github.com/fake-developers/1st/blob/main/SJH/Cookie%26Session.md) 등장)
- 주로 **TCP** 를 사용하고 HTTP/3 부터는 UDP를 사용한다.
- **80번 포트** 를 사용한다.

<BR>

## HTTP메세지

- 클라이언트 - 서버는 메세지 교환에 의해 통신한다.

- 보통 클라이언트에 의해 전송되는 메세지를 요청(requests), 서버에서 답으로 전송되는 메세지를 응답(responses)라고 부른다.

- **요청(requests)**

  <img src="https://mdn.mozillademos.org/files/13687/HTTP_Request.png" width=500> 

  1. HTTP 메서드
     - 클라이언트가 수행하고자 하는 동작
     - GET : 자료를 요청할 때 사용
     - POST : 자료의 생성을 요청할 때 사용
     - PUT : 자료의 수정을 요청할 때 사용
     - DELETE :자료의 삭제를 요청할 때 사용
  2. Path
     - 가져오려는 리소스의 경로
     -  프로토콜(`http://`), 도메인 (en-US) (여기서는 `developer.mozilla.org`), 또는 TCP 포트 (en-US) (여기서는 `80`)인 요소들을 제거한 리소스의 URL
  3. HTTP 프로토콜 버전
  4. Header
     - 요청에 대한 정보
  5. Body
     - 요청 할 때 함께 보낼 데이터를 담는 부분 (여기는 존재하지 않는다.)

- **응답(responses)**

  <img src="https://mdn.mozillademos.org/files/13691/HTTP_Response.png" width=450>

  1. HTTP 프로토콜 버전
  2. 요청에 대한 상태 코드
     - 크게 5부류로 나타낼 수 있다.
     - 1XX (조건부 응답) : 요청을 받았으며 작업을 계속한다.
     - 2XX (성공) : 클라이언트가 요청한 동작을 수신하여 이해했고 승낙했으며 성공적으로 처리했음을 가리킨다.
     - 3XX (리다이렉션 완료) : 클라이언트는 요청을 마치기 위해 추가 동작을 취해야 한다.
     - 4XX (요청 오류) : 클라이언트에 오류가 있음을 나타낸다.
     - 5XX (서버 오류) : 서버가 유효한 요청을 명백하게 수행하지 못했음을 나타낸다.
  3. 요청에 대한 상태 메세지
     - 요청에 대한 성공 여부
  4. Header
  5. Body
     - 응답에는 대부분 바디가 존재
     - 데이터를 요청하면 응답 메세지에는 요청한 데이터를 담아서 보내주기 때문이다.

<br>

### :bulb:HTTP와 TCP

- 저자는 HTTP와 TCP의 관계에 대해 좀 더 알아보았다.
- 이부분에 대해서는 OSI 7계층에 대해 아는 것이 좋은데, 일단은 간단하게 그림으로 보도록 한다.

<img src="https://images.velog.io/images/jehjong/post/68e38b79-1117-4d48-b7c9-e04454205daa/image.png" width=450>

- HTTP는 네트워크를 사용하는 응용 계층, TCP와 UDP는 시스템을 연결하고 데이터를 전송하는 전송계층에 존재한다.

<img src="https://miro.medium.com/max/823/1*qK2A5ivG6Z9IABU6rgu85g.png" width=400>

- 즉,  클라이언트가 요청을 보낼 때, 
  - HTTP 계층에서 HTTP 메세지 작성
  - TCP 계층에서 HTTP 메세지를 패킷으로 분해
  - IP 계층에서 전송위치를 확인하고 
  - 네트워크를 통해 전송한다.
- 그 이후는 위 과정의 역순으로 진행한다.

<BR>

:pushpin: **HTTP에서는 서버에서 브라우저로 응답할 때 정보가 암호화 되지 않는다. 따라서 데이터가 쉽게 도난 당할 위험이 생겼다. ==> [HTTPS](https://github.com/fake-developers/1st/blob/main/SJH/HTTP&HTTPS.md)의 등장**

-----------

### :clipboard: [참조] Reference

- [MDN - HTTP](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)

- [chrisjune-[WEB] HTTP, TCP/IP, 메시지란?](https://chrisjune-13837.medium.com/web-http-tcp-ip-%EB%A9%94%EC%8B%9C%EC%A7%80%EB%9E%80-4b2721fe296f)

- [joeyful.log-[개발자 인터뷰] TCP/IP 4계층](https://velog.io/@jehjong/%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%9D%B8%ED%84%B0%EB%B7%B0-TCPIP-4%EA%B3%84%EC%B8%B5)

- [sejong202.log- HTTP는 무엇일까요?](https://velog.io/@sejong202/HTTP%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C%EC%9A%94)

