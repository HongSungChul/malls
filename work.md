
# 1. 테이블 변경 및 추가사항
  ##  1.1 푸시 테이블 생성(회원가입전 앱 실행시 사용자 푸시아이디 저장)
    - CREATE TABLE hs_pushs ( 
        id psq(20) unsigned NOT NULL AUTO_INCREMENT,
        fcmId varchar(200) NOT NULL,
        UNIQUE KEY unique_email (fcmId)  
        PRIMARY KEY (psq)
      );
  ##  1.2 상점테이블
    - 비콘 address (beaconAddr varchar(20) )
      상점 등록시 비콘 mac address를 발췌하여 저장함
    - fcmId ( fcmId varchar(200) )
      상점앱 푸시용 
      
  ##  1.3 주문 테이블  
    - 주문 상태(order_status varchar(1) default 'A' ) - (A:결제완료, B:중빈중, C:주문완료, Z:취소)
      슈퍼 및 상점 관리자 페이지에서 주문상태 변경 기능 추가 
  ##  1.4 회원 테이블 
    - 푸시아이디 ( psq int )
      푸시 테이블의 psq 필드값이 입력됨
      회원 가입시에 앱에서 전단될 psq  값을 회원 가입시 저장해야함
      
# 2. 슈펴 관리자 페이지
  ##  2.1 상점 등록시 비콘 address 입력 필드 추가
  
# 3. 상점 관리자 페이지 
  ##  3.1 상점 관리자 페이지 링크 필요
  ##  3.2 주문 상세 정보에서 주문 상태 변경 기능 추가 
    order_status - (A:결제완료, B:중빈중, C:주문완료, Z:취소)
    
# 4. 비콘 링크
  - 비콘 url http://checkpin.kr/g/상점아이디 형태
  - 하이브리드 링크 http://checkpin.kr/g/상점아이디?psq=12 형태
  - 위의 링크에서 상점 홈으로 이동시키는 페이지 추가
  - 상점아이디는 4자리 영문숫자 조합으로 만듬
  - psq 값은 회원 가입시 회원테이블에 저장해야함
  
  
