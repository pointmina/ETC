# database

<h2>Chap2</h2>

1. 데이터베이스 관리 시스템
   <<DBMS의 발전 배경>>
   - DBMS : Database Management System 
   - 기존에는 화일 중심의 데이터 처리 시스템이었다.
     -> 데이터의 종속성(dependency)와 중복성(redundancy)를 야기했다.

   <<데이터의 종속성과 중복성>>
   1) 데이터 종속성 : 응용 프로그램과 데이터 간의 상호 의존관계
   - 데이터의 구성 방법이나 접근 방법의 변경시에 응용 프로그램도 동시에 변경해야한다.
     -> 관리가 귀찮다.
   2) 데이터 중복성 : 한 시스템 내에 같은 내용의 데이터가 여러 파일에 중복 저장되어 있다.
      - 일관성(consistency)
      - 보안성(security)
      - 경제성(economics)
      - 무결성(integrity)

  2. 데이터베이스 관리 시스템과 응용 프로그램
   - DBMS : Database Management System
   -> 응용 프로그램과 데이터 사이에 중재자 역할

  <<데이터베이스 관리 시스템의 필수 기능>>
  1) 정의 기능
   - 하나의 저장구조를 여러 사용자의 요구를 지원할 수 있도록 데이터를 조직
   - 데이터의 논리적 구조를 명세
   - 데이터의 물리적 구조를 명세
   - 물리적/논리적 사상을 명세

  2) 조작기능
   - 사용자와 데이터베이스 간의 접속(interface)을 위한 수단
   - 체계적 데이터베이스 접근 및 조작
     - 검색(retrieve)
     - 갱신(update)
     - 삽입(insert)
     - 삭제(delete)
   - 데이터 언어로 표현
  
  3) 제어기능
   - 데이터의 정확성(correctness)과 보안성(security)을 유지하는 기능
   - 제어 기능의 요건
     - 무결성(integrity) : 데이터에 오류 없는 상황 유지
     - 보안(security)
     - 권한(authority) 검사
     - 병행수행 제어(concurrency control) : 여러 사람이 사용해도 괜찮아야함

    <<DBMS의 장단점>>
     1) 장점
      - 데이터 중복의 최소화
      - 데이터 sharing
      - 일관성 유지
      - 무결성 유지
      - 보안 보장
      - 표준화 용이
     2) 단점 -> 굳이 따진 단점이라고 하심
      - 운영비 증대
      - 특정 프로그램의 복잡화
      - 복잡한 백업과 회복
      - 시스템의 취약성

![image](https://github.com/pointmina/database/assets/68779817/037bcf98-8702-4f12-8df7-241c186e02ac)

  <<DBMS의 궁극적 목표>> : **데이터독립성(data independency)**
  
    ⓐ 논리적 데이터 독립성(logical data independency)
      
      - 응용 프로그램에 영향을 주지 않고 논리적 데이터의 구조 변경이 가능
      - 응용 프로그램의 효율적 개발이 가능
      
    ⓑ 물리적 데이터 독립성(physical data independency)
 
      - 응용 프로그램과 논리적 데이터 구조에 영향을 주지 않고 물리적 데이터 구조의 변경이 가능
      - 저장 장치의 효율적 개발이 가능
    
    ⓒ 데이터 독립성 구현 기법
      
      - 사상(mapping)

3. 데이터베이스 시스템 : 데이터를 데이터베이스로 저장 관리하여 정보를 생성하는 컴퓨터 중심 시스템

   <<3단계 데이터베이스>>
   - 스키마(schema)
     - DB의 구조(개체, 관계) 명세
     - 제약조건 명세
   - 3단계 DB 구조에 기반
     - 외부스키마
     - 개념스키마
     - 내부스키마
    
       ![image](https://github.com/pointmina/database/assets/68779817/edad4efe-2d0e-480b-87fb-04b974db3938)
       ![image](https://github.com/pointmina/database/assets/68779817/8f07cf47-bc69-4eb2-be93-885ee646c798)

4. 데이터 언어

<<데이터 정의어 : DDL(Data Definition Language)>> : create, alter, drop, truncate
- 데이터베이스 구조를 정의(definition)하고 변경(alter)하는데 사용
- 데이터 정의의 내용
   - 논리적 데이터 구조의 정의
      - 스키마, 외부 스키마 명세     논리적 데이터 구조 => 외부스키마
   - 물리적 데이터 구조의 정의
      - 내부 스키마 명세
      - 데이터 저장 정의어  
   ![image](https://github.com/pointmina/database/assets/68779817/a55e0304-907d-49e1-ac63-88bb4f60d2c6)

<<절차적 데이터 조작어 vs 비절차적 데이터 조작어>> : select, insert, update, delete
1) 절차적(procedural) DML:
   - 저급 데이터 언어
   - What과 **How**를 명세
   - 한번에 하나의 레코드만 처리
   - 응용 프로그램 속에 삽입 되어 사용

2) 비절차적(non-procedural) DML :
   - 고급 데이터 언어
   - **WHAT** 만 명세하고 how는 시스템에 위임
   - 한번에 여러 개의 레코드를 처리
  
<<데이터 제어어 DCL(Data control language)>> : commit, grant, revoke, rollback
  - 데이터베이스 관리를 위해 데이터 제어를 정의하고 기술한다.
  - 데이터 제어 내용
     - 데이터 보안(security)
     - 데이터 무결성(integrity)
     - 데이터 회복(recovery)
     - 병행수행(concurrency)
  - DB 관리 목적으로 DBA가 사용 
   
    ![image](https://github.com/pointmina/database/assets/68779817/3267835a-2c93-42ef-987f-b16e8bb8e714)
























         
