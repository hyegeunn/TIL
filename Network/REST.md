# HTTP 통신 - axios
<br>

>## axios 란? 
>### 브라우저, node.js 를 위한 Promise API를 활용한 HTTP 통신 라이브러리이다.
<br><br>

>## Promise 란?
>### 서버에 데이터를 요청하여 받아오는 동작과 같은 <u>**비동기 로직 처리에 유용한 자바스크립트 라이브러리**</u> 이다.
>### 자바스크립트는 단일 스레드로 특정 로직이 끝날 때까지 기다려주지 않으므로 데이터를 받아서 화면에 보여주는 로직을 처리할때 <u>**Promise**</u> 를 사용한다.
<br><br>

# REST
<br>

>### 웹에서 데이터를 전송하고 처리하는 방법을 정의한 인터페이스
<br><br>

## REST 구성요소
<br>

>### 1. URI 로 자원 구분 : http://localhost:8080/ ~~
>### 2. Method 로 자원에 대한 행위 구분
>- GET : 조회 (Read)
>- POST : 생성 (Create)
>- PUT : 전체 수정 (Update)
>- FETCH : 일부 수정 (Update)
>- DELETE : 삭제 (Delete)
>### 3. Representation 으로 나타내기 : XML, JSON, RSS 포맷 등
<br><br>

# REST API 
<br>

>### REST 의 원리를 따르는 API 로 REST 서비스를 구현한 것이다.
<br><br>

## REST URI 설계 조건
<br>

>### 1. URI 는 동사보다 명사, 대문자보다 소문자를 사용해야 한다.
>### 2. 마지막에 / 를 포함하지 않는다.
>### 3. _ 대신 - 을 사용한다.
>### 4. 파일 확장자는 URI에 포함하지 않는다.
>### 5. 행위를 포함하지 않는다.
<br><br>

# RESTful
<br>

>### REST 아키텍처를 준수한 것이다.
>### 모든 CRUD 기능을 POST로 처리 하는 API 또는 URI 규칙을 올바르게 지키지 않은 API는 REST API 를 사용했지만 RESTful 하지 못한 시스템이라고 할 수 있다.



