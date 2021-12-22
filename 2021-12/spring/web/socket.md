WebSocket
===========

웹소켓이란 무엇인가욤?
두 프로그램 간의 메시지를 교환하기 위한 통신 방법중 하나.  
일반적인 단방향 http 통신에서 쌍으로 실시간 통신을 하기위한 양방향 통신의 갈증이 생겨났고  
그래서! 실시간으로 응답과 요청을 받는것이 웹 소켓입니당 

## 특징
#### 양방향 통신(Full-Duplex)
- 데이터 송수신을 동시에 처리할 수 있는 통신 방법
- 클라이언트와 서버가 서로에게 `'원할때' 데이터를 주고 받는다.  
- 통상적인 HTTP통신은 클라이언트가 요청을 보내는 경우에만 서버거 응답하는 '단방향' 통신

#### 실시간 네트워킹 (Real Time-Networking)
- 웹환경에서 연속된 데이터를 빠르게 노출
- 여러 단말기에 데이터를 빠르게 교환한다
- ex)채팅, 주식 비디오 데이터

#### 웹 소켓의 동작 방법 - Hand Shaking
Request(클라이언트 -> 서버)
```
// 웹 소켓 요청 HTTP '헤더'의 예시 (클라이언트 -> 서버)

GET /chat HTTP/1.1 //반드시 Get방식으로만 요청해야 한다. HTTP는 1.1 이상이다
Host: example.com:8000 //웹소켓 서버의 주소
Upgrade: websocket//현재 클라이언트, 서버, 전송 프로토콜 연결에서 다른 프로토콜로 업그레이드 또는 변경하기위한 규칙
Connection: Upgrade //송신자는 반드시 Upgrade 옵션을 지정한 Connection 헤더 필드가 필요하다
Sec-WebSocket-Key: dGhlIHNhbXBsZSBub25jZQ== //클라이언트와 서버간의 서로의 신원을 인증
Origin: http://example.com //이것은 클라이언트의 주소
Sec-WebSocket-Protocol: chat, superchat //여러 서브 프로토콜을 의미한다.
Sec-WebSocket-Version: 13
```
Response(서버 -> 클라이언트)
```
HTTP/1.1 101 Switching Protocols //101 Switching Protocols가 응답으로 오면 웹소켓이 연결되었다는 의미
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: s3pPLMBiTxaQ9kYGzzhZRbK+xOo= //클라이언트로부터 받은 Sec-WebSocket-Key를 사용하여 계산된 값으로 서로의 인증하는 과정에서 필요한 헤더
//클라이언트에서 계산한 값과 일치하지 않으면 연결하지 않는다.
```
1.WebClient는 handshake 요청 메세지를 Web Server에게 보낸다.  
2.서버는 handshake응답 메시지를 web client에게 보낸다.  
3.클라이언트는 data payload frames를 서버에게 보낸다.  
4.서버는 data payloadframes를 클라이언트에게 보낸다.  
5.클라이언트는 closeframe을 webServer에게 보낸다.  
6.서버는 closeframe을 클라이언트에게 보낸다.  




## HandShaking 완료, 데이터 전송
http를 이용하여 HandShaking이 완료 되었으므르ㅗ, 이제 프로토콜이 WS(web socket)으로 변경된다. 이 순간 부터 양방향 통신이 가능해진다.

- ws(80) or wss(433) 으로 통신한다. wss란 https처럼 ws프로토콜에 데이터 보안을 위해 SSl을 적용한 프로토콜이다
- Message : 여러 Frame이 모여서 구성하는 하나의 논리적 메시지 단위. ws 프로토콜을 통해 주고 받는 단위라고 보면 된다.
- Frame : Communication에서 가장 작은 단위의 데이터(작은 헤더 + Payload로 구성) -> 기존의 무거운 헤더의 단점을 보완
- 웹소켓 통신에 사용되는 데이터는 UTF-8 인코딩을 통해서만 지원된다.
- 0x00{보내고 싶은 데이터}와 같은 형태로 데이터를 주고 받는다.

## 프레임
<img src = "https://user-images.githubusercontent.com/80088918/147105420-67e70f20-98af-4947-99c2-8325aeccdd5a.png">  

- FIN(END): 이 프레임이 전체 메시지의 끝인지 나타내는 플래그 
- RSV 1~3 : 프로토콜 별로 사용할 수도 있고 사용할 수도 있지 않는 것들이다.  
OPCODE :
-Continue (0x0) : 전체 메세지의 일부임을 의미

- Text(0x1) :포함된 데이터가 UTF-8 텍스트라는 의미  
- Binary (0x2) : 포함된 데이터가 이진 데이터라는 의미  
- close(0x8) : close 핸드풰이크를 시작한다는 의미  
- legth : 이 프레임에 포함된 데이터의 총 길이를 나타내는 단위  

핸드쉐이크도 완료되었고, 이로 인한 데이터 양방향 전송도 모두 완료 되었다면 이제는 연결 종료해야 한다.  
연결 종료 할때는 close frame을 주고 받으며 종료한다.  


## 정리
<img src = "https://user-images.githubusercontent.com/80088918/147106192-8eab9eaa-b26b-498d-b993-5e5333c3f7dd.png">  
- HTTP 를 이용해 클라이언트와 서버가 핸드 쉐이킹을 한다 (webSocket 사용 가능하뉘 서버야? 서버: 웅 가능)  
- UTF8로 인코딩 된 페이로드를 0x00과 0xff 사이에 넣고 데이터를 주고 받는다. (웹소켓 프로토콜로 양방향 데이터 전송)
- Close Frame을 이용해 연결을 종료한다.

## 웹소켓 프로토콜의 특징
- 최초 접속에서만 http 위에서 hand shaking 을 하기 때문에 HTTP 헤더를 사용한다
- 웹소켓을 위한 별도의 포트는 없음, 기존 포트 http는 80, https는 443을 사용한다.
- 프레임으로 구성된 메시지라는 논리적 단위로 송수신한다.
- 메시지에 포함될 수 있는 교환 가능한 메시지는 `텍스트와 바이너리`이다.



Socket.io
============
그럼 소켓 아이오는 무엇인가요 ?
다양한 방식의 실시간 웹 기술을 손쉽게 사용할 수 있는 모듈 입니다.
WebSocket, FlashSocket, AJAX Long Polling, AJAX Multi part Streaming, IFrame, JSON Polling 등 다양한 방법을 하나의 API로 추상화 한 것이다.  
즉, Socket.io는 JavaScript를 이용하여 브라우저 종류에 상관 없이 실시간 웹을 구현할 수 있도록 한 기술이다.  
