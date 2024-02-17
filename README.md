# EIP

1과목
-

GoF(Gang of Four) : 소프트웨어 설계에 있어 공통된 문제들에 대한 표준적인 해법과 작명법을 제안한 책

1. 생성 패턴 : 객체 생성에 대한 패턴
- 추상 팩토리
- 빌더
- 팩토리 메소드
- 프로토타입
- 싱글턴

2. 구조패턴 : 구조가 복잡한 시스템 개발에 도움을 줌
- 어댑터
- 브릿지
- 합성
- 데코레이터
- 파사드
- 플라이웨이트
- 프록시

3. 행동 패턴 : 상호작용이나 책임 분배에 대한 부분을 정의하고 결합도는 최소화 하는 것이 목표
- 책임 연쇄
- 커맨드
- 인터프리터
- 반복자
- 중재자
- 메멘토
- 옵저버
- 상태
- 전략
- 템플릿 메소드
- 방문자

클래스
: 객체지향 프로그램에서 데이터를 추상화하는 단위

객체지향 분석 방법론
1. Rumbaugh*(럼바우) 방법
- 가장 일반적으로 사용되는 방법
- 분석 활동을 객체 모델, 동적모델, 기능 모델로 나누어 수행하는 방법

2. Booch(부치) 방법
- 미시적, 거시적 개발 프로세스를 모두 사용하는 분석 방법
- 클래스와 객체들을 분석 및 식별하고 클래스의 속성과 연산을 정리

3. Jacobson 방법
- Use Case를 사용하여 분석

4. Coad와 Yourdon 방법
- E-R 다이어그램을 사용하여 객체의 행위를 모델링
- 연산과 메세지 연결 정의 등의 과정으로 주로 관계를 분석

5. Wirfs-Brock(워프트 브록) 방법
- 분석과 설계간 구분 없음
- 연속적으로 수행

코드설계 : 데이터를 효율적이고 정확하게 처리하기 위해 부여하는 기호나 숫자의 체계

코드설계 원칙 
1. 간결성
2. 일관성
3. 유연성
4. 명확성

![image](https://github.com/pointmina/EIP/assets/68779817/98f5badf-4892-435e-b679-12f46315ce37)

CASE(Computer - Aided Software Engineering)
: 소프트웨어 개발 시 사용되는 분석 자동화 도구.. 소프트웨어 개발 과정의 일부나 전체를 자동화하는 도구

기능
- 그래픽 지원
- 소프트웨어 생명 주기 전반적인 단계의 연결
- 다양한 소프트웨어 개발 모형을 지원


XP(eXtreme Programing)의 핵심가치
- 용기
- 존중
- 의사소통
- 피드백
- 단순성

  DBMS 분석 시 고려사항
  - 가용성 : 장애 발생 가능성, 안정적인 트랜잭션 처리 능력
  - 성능
  - 상호 호환성
  - 기술 지원
  - 구축 비용

럼바우(Rumbaugh)의 객체지향 분석 절차 
객체 모형 -> 동적 모형 -> 기능 모형

DFD(Data Flow Diagram)
- 자료의 출발지와 목적지를 그림으로 표시한 것이다.
- 데이터 흐름도 또는 자료 흐름도 라고도 한다.

DFD의 구성요소
- 프로세스
- 데이터 흐름
- 데이터 저장소
- 외부엔티티

UML(Umified Modeling Language)
: 분석, 설계, 구현 등 시스템 개발 과정에서 시스템 개발자와 고객 또는 개발자 상호간의 의사소통이 원활하게 이루어지도록 표준화한 대표적인 객체지향모델링 언어이다. 즉, 많은 사람들이 모여 작업을 수행하다 보면 같은 대상물을 보고도 서로 다르게 표현하여 의사소통에 문제가 생기는 경우가 있다. 이런 문제를 해결하기 좋은 방법은 공통된 표현법을 만드는 것이다. 

1. 사물 : 모델을 구성하는 가장 중요한 기본 요소, 다이어그램 안에서 관계가 형성될 수 있는 대상들을 말한다. 
- 구조사물 : 시스템의 개념적, 물리적 요소를 표현, 클래스, 유스캐이스, 컴포넌트, 노드 등
- 행동사물 : 시작과 공간에 따른 요소들의 행위를 표현, 상호작용, 상태머신 등
- 그룹사물 : 요소들을 그룹으로 만들어 표현, 패키지
- 주해사물 : 부가적인 설명이나 제약조건 등을 표현, 노트

2. 관계 : 사물과 사물 사이의 연관성을 표현하는 것
- 






















   
