# database

<h2>Chap2</h2>

핵심내용
-
1) 데이터 종속성과 중복성
2) DB 관리 시스템의 장단점
3) 논리적 데이터 독립성과 물리적 데이터 독립성
4) 데이터 정의어, 조작어, 제어어
5) 데이터베이스 관리자

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
![image](https://github.com/pointmina/database/assets/68779817/21f2afb8-e508-43ee-ac4e-515adda31577)

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


<<데이터베이스 관리자 : DBA(Database Administrator)>>
- DDL과 DCL을 통해 DB를 정의하고 제어하는 사람
- DB시스템의 관리, 운영에 모든 책임을 지는 사람
- DB설계와 운영
- 행정 및 불평 해결
- 시스템 감지 및 성능 분석

<h2>Chap3</h2>

핵심내용
-
1) 관계 데이터 모델
2) 릴레이션
3) 관계 데이터베이스
4) 키
5) 무결성 제약

1. 관계 데이터 모델(relational data model)
   - 수학에서의 릴레이션과 집합 이론에 기초
   - 테이블의 열 = 관계 데이터 모델의 애트리뷰트(attribute)
   - 테이블의 행 = 관계 모델의 튜플(tuple)
   - 릴레이션 : 튜플의 집합(순서가 없다.)
   
   <<애트리뷰티와 도메인>>
   - 도메인(domain) : 애트리뷰트가 취할 수 있는 값들의 집합
   - 애트리뷰트(attribute) : 도메인의 역할 이름
   - 한 릴레이션 내에서 애트리뷰트 이름들은 모두 달라야단다.
   - 단순 도메인 : 단순 애트리뷰트 : 원자 값(생일, 주소 같은 쪼갤수 있는거 말고 분해할 수 없는!)
   - 애트리뷰트 이름과 도메인 이름이 같을 수도 있당
   
   <<Relation Schema>>
   - 릴레이션의 이름, 각 속성의 이름과 타입, 그리고 속성 값의 도메인을 정의하는, 즉 릴레이션에        데이터를 넣을 수 있도록 하는 릴레이션 틀
   - 정적 성질
     - 시간에 무관
   - 릴레이션 타입과 같은 의미
   
    <<Relation Instance>>
    - 어느 한 시점에서 릴레이션 R이 포함하고 있는 튜플들의 집합
    - 동적 성질
       - 삽입, 삭제, 갱신으로 시간에 따라 변함
   
    <<Relation R>>
    - 릴레이션 R : 카티션 프로덕트의 부분집합
    - 릴레이션 스키마 + 릴레이션 인스턴스
   
   
    <<릴레이션의 특성>>
    ⓐ 튜플의 유일성 : 모든 튜플은 서로 다른 값을 갖는다.
    ⓑ 튜플의 무순서성
    ⓒ 애트리뷰트의 무순서성
    ⓓ 애트리뷰트의 원자성 : 쪼개질 수 없다.
    - 정규화 릴레이션(normalized relation)
      = 애트리뷰트 값이 only 원자값만 허용되는 relation
    - 비정규화 릴레이션은 분해를 통해 정규화 -> 이때 정보의 추가나 소실이 있어서는 안됨
    - 널 값도 원자 값으로 취급
   
   
   **DBMS에서 Relation과 Relationship의 차이점은**
   - Relation 은 관계형 모델 데이터베이스의 테이블
   - Relationship 은 관계형 모델 데이터베이스의 두 테이블이 서로 연결되는 방식을 가리킨다.


2. 무결성 제약
- 데이터베이스의 **정확성, 일관성**을 보장하기 위해 저장, 삭제, 수정 등을 제약하기 위한 조건
- 데이터베이스에 저장된 데이터의 무결성을 보장하고 데이터베이스의 상태를 일관되게 유지하는 것

  1) 개체 무결성(entity integrity)
     - 기본 키 값은 언제 어느 때고 null 값을 가질 수 없다.
   2) 참조 무결성(referential integrity)
      - 외래 키 값은 반드시 피참조 릴레이션의 기본 키 값이거나 null이다.
      - 긍까 외래 키 값은 무조건 PK여야 한다는뜻..? ㅇㅇ맞는듯

3. 키

   1) 후보 키(candidate key)
      - 릴레이션에 대한 애트리뷰트의 집합으로 두 성질을 만족한다.
        ① 유일성
        ② 최소성
      - 요기서 DBA가 원하는 거로 PK키 지정
   2) 슈퍼키(super key)
      - 유일성(uniqueness)은 만족하지만 최소성(minimality)을 만족하지 않는 애트리뷰트의 집합
   3) 기본키(primary key)
      - 후보키(candidate key) 중에서 지정된 하나의 키를 DBA가 지정
      - null 값이 허용되지 않음!
   4) 대체키(alternate key)
      - 후보 키 중에서 기본 키를 제외한 나머지 후보키


<h2>Chap4</h2>

핵심내용
-
1) 절차적 질의와 비절차적 질의
2) 관계대수

1. 관계 대수
   <<관계 대수(Relation Algebra)>>
![image](https://github.com/pointmina/database/assets/68779817/014a254f-670f-480b-b15c-62d8b2a92f17)
   - 폐쇄 성질(closure property)
      - 피연산자와 연산 결과가 모두 릴레이션(튜플의 집합)
      - 중첩된 수식의 표현이 가능

     <<일반 집합 연산자>>
     - 합집합, 교집합, 차집합 은 attribute의 개수, 도메인이 같아야한다.
     - 합,교,카 는 결합적이다. 결합 순서가 상관없다.
     - 합,교,카 는 교환적이다. 
     - 카티션은 달라도됨

   <<셀렉트 select>>
   - ex) 시그마학과 = '컴퓨터'(학생)
   - 선택도(selectivity) : 선택 조건에 의해 검색되는 튜플의 비율
   - select해서 나온 결과 몇퍼센트인가 -> 선택도 더 작은거부터 실행한다.

   <<나머지는 아는거라 다 생략함!>>

   <<기본 연산(primitive operations)>>
   - 다른 연산으로 대체할 수 없는 하나의 논리적 기능을 수행하는 연산
   -  ∩ , – , ×, 프로젝트, 시그마(셀렉트), ρ(료:이름바꾸는거)
  
   <<절차적 언어(procudural language)와 비절차적 언어(non-procedural language)>>
   1) 절차적 언어(procedural language)
      - 순서를 명확한 계산법으로 쉽게 표현할 수 있는 문제 지향 언어
      - 순서를 명확하게 기술하면서 처리를 쉽게 실행하는 언어
   2) 비절차적 언어(non-procedural language)
      - 컴퓨터의 실행 순서에 관계없이 처리 내용을 기술할 수 있는 프로그램 

디비전은 몰랐던거라 추가!
![image](https://github.com/pointmina/database/assets/68779817/f0c92aad-0702-48ad-b6a9-eb1bc75a75f2)

<h2>Chap5</h2>

핵심내용
-
1) 튜플 관계해석
2) 도메인 관계해석
3) QBE
4) SQLite 

<<관계 해석(Relational Calculus)>>
- Predicate calculus에 기반
   - Predicate : 실행 결과가 반드시 참(true)나 거짓(false)인 함수
- 비절차적(non-procedure) : 원하는 정보가 무엇이라는 것만 선언















   











         
