# computer_structure

으아 다 날라갔어어어어어어어

<h2>ca02. 컴퓨터의 발전과 가능성</h2>

1. 폰노이만 아키텍처(Von Neumann Architecture)
   ![image](https://github.com/pointmina/computer_structure/assets/68779817/f625ef7a-2ea4-4eec-9b14-e01bf232057b)

   - 프로그램 내장식 컴퓨터 : 프로그램과 데이터를 메모리에 저장하고 명령을 순차적으로 꺼내서 CPU에서 해독하고 실행
   - 소프트웨어 개념 등장
   - 폰노이만 병목 현상 : CPU와 메모리 사이의 트래픽이 성능 지연에 미치는 영향
   => 메모리와 CPU가 빨라야하는데 버스가 복잡해짐 -> 하버드 아키텍처

3. 컴퓨터의 성능 : 응답시간과 처리율
   - 성능 = 1 / CPU실행시간
   - M1에 대한 M2의 성능 비율 => n = M2의 성능 / M1의 성능 = M1의 실행시간 / M2의 실행시간
  
     <<암달의 법칙(Laws of Gene Amdhal)>>
    -  시스템 일부분을 개선할 때 전체 시스템 성능이 얼마나 향상되는지 계산하는 방법
    -  병렬화로 일부 시스템을 개선했다해도 성능 향상이 되지 않은 부분(1/(1-f))에 의해 전체 시스템의 성능이 제한된다.
    -  병렬화에 인한 시스템 성늘 향상의 한계를 지적하는데 사용한다.!
  
    -  시스템의 일부분 f를 병렬화하여 성능을 n배 향상시키고, 나머지 부분 (1-f)는 그대로 두었다고 가정하고,
    -  성능 향상 전의 기계를 M1, 성능이 향상된 기계를 M2라고 하면, 시스템 전체 성능 향상 s는
    -  ![image](https://github.com/pointmina/computer_structure/assets/68779817/4983f8f3-c924-4917-bea7-1c3b7e101be3)

    - M1의 실행시간을 m이라 할 때, M2의 실행시간은
  ![image](https://github.com/pointmina/computer_structure/assets/68779817/91b2523b-56d1-488f-9609-5110b867b976)
    - **결과적으로 시스템 전체 성능 향상 s는 개선되지 않은 부분의 역수가 된다.**

4. CPU 성능 분석

<<성능에 영향을 미치는 요소>>
-  클록 속도가 중요하다. 하지만 빠르다고 무조건 좋은 것은 아니다.
-  클록 속도 이외의 다른 성능 요인도 살펴보아야 한다.

<<CPU 실행시간의 분해>>
- CPU의 성능은 프로그램 실행 시간으로 구분 가능
- 프로그램의 CPU 실행시간 = 명령어 개수 X 평균 CPI X 사이클 시간
- ![image](https://github.com/pointmina/computer_structure/assets/68779817/a4c5858d-65c5-4c03-8476-8f98f3ecd0b2)

- CISC(Complex Instruction Set Computer, 복합 명령어 집합 구조) =  프로그램 크기가 줄어들지만 평균 CPI와 사이클 시간이 커진다.
- RISC(Reduced Instruction Set Computer, 축약 명령어 집합 구조) =  명령어 개수가 늘어나지만 평균 CPI와 사이클 시간이 줄어든다.
- 시스템 병렬화 = 평균 CPI가 줄어들지만 사이클 시간이 늘어날 수 있다.
- 집적도를 높이면 사이클 시간이 줄어들지만 비용이 높아진다.


<h2>ca03. 명령어 집합</h2>

1. 명령어 집합
- 고급 언어(high-level language)
   - 높은 생산성, 컴파일 오류 탐지, 유지 보수에 용이함
   - 컴파일러 또는 인터프리터에 의해 변환되어 컴퓨터에서 실행
     
- 기계 명령어(machine instruction)
   - 컴퓨터 CPU에서 실행되는 명령어를 2진수 코드로 정의한 것
         
- 어셈블리어(assembly language)
   - 인간이 읽기 쉽도록 기계어를 기호로 표현한 언어
   - 기계어와 일대일로 대응
 
2. 명령어 특성
- 명령어란? 컴퓨터가 수행할 수 있는 동작을 2진 코드로 정의한 것
- 명령어의 구성
   - 연산 부호(opcode) : CPU가 실행할 동작을 의미 : 덧셈, 뺄셈, 저장, 분기 등
   - 피연산자(operand) : 연산의 대상이 되는 데이터 또는 데이터의 위치 : 메모리 주소, 레지스터 번호, 상수값, 입출력 포트
 
<<명령어 길이 형식>>

- 고정길이(fixed-length) 명령어 형식
   - 명령어의 종류/구성요소와 관계없이 모두 동일한 길이의 명령어 형식
   - 해석이 쉬워 프로세서 결계가 단순해짐
   - 짧게 표현 가능한 명령어도 고정 길이에 맞춰야하므로 낭비되는 부분이 발생
   - RISC에서 사용(명령어 많, 평균CPI외 사이클 시간 적)
 
- 가변길이(variable-length) 명령어 형식
   - 명령어의 종류/구성요소에 따라 다양한 길이의 명령어 형식
   - 프로그램에 낭비되는 부분 없이 강력한 명령어 도입 가능
   - 해석이 어려워 프로세서 설계가 복잡해짐
   - CISC(Complex Instruction Set Computer)에서 사용 

<<3-주소 명령어 형식>>
![image](https://github.com/pointmina/computer_structure/assets/68779817/a2ea54d7-5ec4-492b-9ce3-6502dad3088a)
![image](https://github.com/pointmina/computer_structure/assets/68779817/320d6676-94fb-4e6d-a0d0-3e02405a9824)
- 명령어의 길이가 길어진다.
- 프로그램을 구현하는 명령어의 수가 적어진다.

<<2-주소 명령어 형식>>
![image](https://github.com/pointmina/computer_structure/assets/68779817/f73297bf-d722-4acf-aff4-a855524f55dc)
![image](https://github.com/pointmina/computer_structure/assets/68779817/443bf324-fe66-4699-9f29-9760ee05fe79)
- 첫번째 source와 target 피연산자를 동일하게 사용한다.
- 명령어의 길이가 짧아진다.(3주소에 비해)
- 프로그램을 구현하는 명령어의 수가 증가한다.

<<1-주소 명령어 형식>>
![image](https://github.com/pointmina/computer_structure/assets/68779817/7a3d9ead-233a-4183-9bde-d83f45699cc9)
- 누산기(Acc, Accumulator)를 사용한다.
- 명령어 표현에서 Acc를 생략하여 명령어의 길이가 매우 짧아진다.
- 명령어의 수가 가장 많아진다.
- 초기 컴퓨터에서 사용하였으나, 지금은 찾아보기 힘들다.

<<0-주소 명령어 형식>>
- 스택을 사용하는 계산기에서 사용하는 명령어 형식
  - ADD, MUL 등의 연산자는 stack에서 두 개의 데이터를 pop하여 계산하고 그 결과를 push한다.
![image](https://github.com/pointmina/computer_structure/assets/68779817/5b77694c-0b09-4af0-b880-9fbb4ccc34c6)

<<피연산자와 관련하여 명령어 길이를 줄이는 방법>>
- 메모리 주소 대신 레지스터 주소 사용 (레지스터는 3비트 메모리 주소는 16비트)
- 2-주소 명령어 형식 : 3-주소 명령어 형식보다 명령어 길이가 짧아진다.
- 1-주소 명령어 형식의 묵시적 피연산자(implicit operand) 사용 : 피연산자에서 누진기를 생략함으로써 명령어 길이가 짧아진다.

3. 명령어 사이클

   <<가상컴퓨터 AccCom의 CPU 구성>>
   - 제어장치
      - PC(program counter) : 프로그램 계수기 (다음번에 실행해야할 주소를 가지고 있음)
      - IR(instruction register) : 명령어 레지스터 (명령어를 잠시 보관해줌)
   - 연산장치
      - Acc(accumulator) : 누산기
   - 메모리 인터페이스
              
   <<명령어 사이클의 종류>>
   - 인출 사이클 : 메모리에서 CPU로 명령어를 가져오는 단계 : 실행할 명령어를 메모리 -> CPU 단계
   - 실행 사이클 : CPU에서 명령어를 실행하는 단계
   - 인터럽트 사이클 : 인터럽트 발생시 서비스 루틴을 실행하는 단계

    피피티 20쪽까지함












