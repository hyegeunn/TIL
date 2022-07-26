# <strong>WebRTC</strong>
<br>

#### 실시간, 영상, 음성, 데이터를 교환할 수 있는 P2P 기술이다.
#### 서로 다른 네트워크에 있는 2개의 클라이언트간 미디어 포맷등을 상호 연동하기 위한 <strong>협의과정 (Negotiation)</strong> 이 필요하다.
<br>

#### 이 프로세스를 <strong>시그널링 (Signalling)</strong> 이라고 부른다.
<br><br>

## <strong> SDP 교환 - Answer, Offer</strong>
<br>

> SDP 는 Session Description Protocol 로 RFC 4566에 규정된 스트리밍 미디어의 초기화 인수를 기술하고 협상하기 위한 것이다.

<br>

### <strong># Example</strong>
<br>

> - Alice 가 SDP 형태의 Offer 메세지를 생성한다.
> - Alice 가 생성된 Offer 메세지를 자신의 LocalDescription 으로 등록한다.
> - Alice 가 Offer 메세지를 Signalling Server 에게 전달한다.
> - Signalling Server 는 상대방 Bob을 찾아 SDP 정보를 전달한다.
> - Bob은 전달받은 SDP 정보를 본인의 RemoteDescription 에 등록한다.
> - Bob은 Answer 메세지를 생성한다.
> - 생성된 Answer 메세지를 본인의 LocalDescription 에 등록한다.
> - Bob은 Answer 메세지를 Signalling Server 로 전달한다.
> - Signalling Server 는 상대방 Alice를 찾아 Answer 메세지를 전달한다.
> - Alice는 전달받은 Answer 메세지를 본인의 RemoteDescription에 등록한다.

<br><br>

## <strong>ICE 협상 (ICE Negotiation)</strong>
<br>

> ICE (Interactive Connerctivity Establishment) 는 P2P 네트워킹에서 두 컴퓨터가 가능한 한 직접 서로 통신하는 방법을 찾기 위해 컴퓨터 네트워킹에 사용되는 기술이다.
<br>
각 ICE 메세지들은 두 개의 컴퓨터를 서로 연결하기 위한 정보들에 덧붙여 프로토콜, IP주소, 포트넘버, 커넥션 타입등을 제안한다.

<br>

> - SDP 를 서로 교환한 후, 각 Peer Alice 와 Bob은 서로의 주소값을 알기 위해 ICE Candidate (ICE 후보) 를 교환한다. 이떄 사용되는 기술은 <strong>NAT Traversal</strong> 이다.

<br><br>

### <strong>WebRTC 에서 Signalling Server 가  하는 일</strong>
<br>

> - 각 Peer 간 SDP 메세지 Offer, Answer 를 전달해주고 ICE 후보를 주고 받을수 있도록 도와주는 서버
> - Peer 관리를 해주는 포워딩 서버

<br><br>




