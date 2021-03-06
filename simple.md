### 자료요청

    - 서버 접근(ssh) 계정
    - 데이타베이스 계정
    - 관리자 페이지 링크 및 계정 정보
    - 서비스 접근 url  
    - 앱등록계정(android ,ios)
    - 네이버 걔발자 계정(단축 url)
    - 상점앱 및 사용자앱 이름 정의하기
    - firebase 계정 만둘기(push 메세지용)
    - 안드로이드,ios 개발자 개정 접속시 본인확인해야함(핸드폰)

## 작업 정리

1. 비콘
    - KBeacon 제품을 사용
    - KBeacon Pro app 을 통해 비콘 설정함
        - eddystone Url 설정
        - url 크기는 17자를 못넘김(네이버 단축 url 문서)
        - 연결 기능 빼고 비콘기능만 이용하면 밧데리 사용기간이 2배로 늘어남(확인필요)
2. 사용자앱
    - 사용자앱 실행시 비콘 eddystone Url 을 5초동안 스캔
    - 별견시 Url로 이동. 비발견시 기본 페이지 이동
    - 사용자가 상품 주문시 해당상점앱에게 주문수신 노티를 보내준다.
    - 상점앱에서 노티 수신
3. ~~상점앱 전용 웹서버 구축~~
    - ~~nodejs 기반 espress 설치~~
    - ~~웹서버에서 proxy 기능 활성화해서 구성~~
    - ~~로그인 api~~
    - ~~주문목록 api~~
    - ~~주문상태 수정 api~~
    - ~~사용자가 주문시 상점앱에 노티전송 api~~
    - ~~단축 url api (커맨드 라인에서 입력하면 출력되게 만듬)~~
    
4. 상점앱
    - ~~3번 상점앱 전용 웹서버와 연동함~~
    - ~~로그인 페이지 구성~~
    - ~~주문 목록 페이지 구성~~
    - ~~주문 처리 기능 구성~~
    - 사용자가 주문시 노티 표시 해야함 
    - <span style="color:blue">상태정보 정리</span>
    
| 상태       |     사용자앱    |  상점앱 |
|---------- |:-------------:|------:|
| A         |  준비중         | 준비중 |
| B         |  완료          |   완료 |
| Z         |  취소          |   취소 | 



5. 기존데이타베이스
    - 상점테이블에 fcmId 필드추가(상점앱에 노티용)
    - 주문테이블에 결과 처리 필드 추가( 가칭 요청/ 완료)


6. 기존웹서버 
    - 사용자가 주문시에 상점앱에 노티보내기 위해 api call 하는 기능 추가 
    - <span style="color:blue">상태변경시 노티 발송</span>
7. 네이버 단축 url 연동
    - https://api.ncloud-docs.com/docs/ai-naver-nshorturl 
    
8. 프린트 기능은 나중에....


