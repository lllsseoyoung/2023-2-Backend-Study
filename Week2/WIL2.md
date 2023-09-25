1. HTTP에 대해 정리하라

-HTTP란? 
HyperText Transfer Protocol의 약자로 서로 다른 시스템들 사이에서 통신을 주고 받게 해주는 application 계층의 프로토콜(규약)

-HTTP 특징
*trasfer layer: TCP/IP 기반으로 서버와 클라이언트 간의 요청과 응답을 전송
*비연결성: 클라이언트와 서버가 한번 연결을 맺은 후에 클라이언트의 요청에 대해 서버가 응답을 마치면 연결을 끊어버림
*무상태성: 비연결성으로 인해 서버가 두 요청간의 어떠한 데이터도 유지하지 않음(정보 저장x)

-HTTP 연결과정
HTTP서버와의 TCP연결을 열어줌-> TCP연결로 HTTP클라이언트가 HTTP요청 메세지를 전송-> HTTP서버가 요청 메세지를 받고 응답 메세지 보냄->서버가 보낸 응답 읽음-> TCP연결 닫거나 다른 요청을 위해 재사용

-HTTP method(요청)
: 클라이언트가 서버에 특정 요청을 보낼 때, 웹서버에게 요청하는 목적 및 그 종류를 알리는 수단으로 HTTP Method를 사용
*주로 사용하는 Method
>GET: 리소스 조회
>POST: 요청 데이터 처리, 주로 등록에 사용
>PUT: 리소스를 대체, 해당 리소스가 없으면 생성
>PATCH: 리소스 부분 변경
>DELETE: 리소스 삭제

-HTTP 상태 코드(응답)
: 서버측에서 클라이언트로 요청에 대한 응답을 보낼 때, 해당 요청에 관한 처리 상태를 알려주는 기능
100-500까지, 번호마다 의미가 다르지만 백의 자리 숫자가 같으면 비슷한 의미 가짐
*1xx(Informational): 요청이 수신되어 처리중
*2xx(Successful): 요청 정상 처리
*3xx(Redirection): 요청을 완료하려면 추가 행동 필요
*4xx(Client Error): 클라이언트 오류(잘못된 문법 등)로 서버가 요청 수행 불가
*5xx(Server Error): 서버 오류로 서버가 정상 요청을 처리하지 못함


2. HTTPS가 무엇인지 정리하고, HTTP와 비교하라

-HTTPS란? 하이퍼텍스트 전송 프로토콜 보안으로 기본 프로토콜인 HTTP의 보안 버전

-차이점: HTTP 메세지는 일반 텍스트이므로 쉽게 접근하고 읽을 수 있는 반면 HTTPS는 모든 데이터를 암호화된 형태로 전송한다


3. 아래 API에 대한 RESTful한 URI을 설계하라

-이벤트 목록 조회: GET  /events
-이벤트 조회: GET   /events/Thanksgiving
-이벤트 등록: POST  /events/Thanksgiving
-이벤트 수정: PUT   /events/Thanksgiving
-이벤트 삭제: DELETE    /events/Thanksgiving
-이벤트 상태 변경: PATCH    /events/Christmas/state
-특정 이벤트의 주문 목록 조회: GET  /events/Christmas/orderlist
-멤버 목록 조회: GET    /members
-특정 멤버 권한 변경: PATCH    /members/Kim/authority
-특정 멤버 정보 조회: GET   /members/Kim/info
-특정 멤버 정보 변경: PATCH    /members/Kim/info
-멤버 등록: POST    /members/Bong