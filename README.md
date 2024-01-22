# AWS_SAA

**Amazon S3 Transfer Acceleration**
클라이언트와 S3 버킷 간의 장거리 파일 전송을 파일을 빠르고 쉽고 안전하게 전송할 수 있다. 가능한한 빨리 집계할때, 운영상의 복잡성 최소화

**Amazon Athena**
Amazon S3에 있는 데이터를 직접 간편하게 분석할 수 있는 대화형 쿼리 서비스, 솔루션 설계자는 기존 아키텍처를 최소한으로 변경하면서 분석 수행한다. 최소한의 운영 오베헤드로 요구 사항 충족 가능

**aws PrincipalOrgID 전역조건**
AWS Organizations를 사용하여 다양한 부서의 여러 AWS 계정을 관리한다. S3버킷에 대한 액세스를 AWS Organizations의 조직 내 계정 사용자로만 제한하려고한다. 
aws PrincipalOrgID : 리소스에 액세스하는 보안 주체가 조직의 계쩡에 속하는지 확인한다. 조직이 속하지 않은 구성원이 리소스에 액세스하는 것을 방지할 수 있다.

**Gateway Endpoint**
게이트워이 엔드포인트를 사용하면 인터넷 게이트웨이 또는 NAT 디바이스가 없어도 S3 및 DynamoDB에 안정적으로 연결할 수 있따. 게이트웨이 엔드포인트 사용에 따르는 추가 요금은 없다. 
회사가 지역 데이터 전송 비용을 피할 수 있는 가장 비용 효율적인 방법 !
 

**Amazon EBS(Elastic Block Store)**
EBS는 EC2인스턴스에 사용할 수 있는 블록 수준 스토리지 볼륨을 제공한다. 인스턴스 수명에 관계없이 지속된다. 데이터에 빠르게 액세스하고 장기적으로 지속해야 하는 경우 EBS를 사용하는 것이 좋다. EBS는 세분화된 업데이트가 필요하고 형식이 지정되지 않은 블록수준의 원시 스토리지에 액세스해야 하는 파일 시스템, 데이터베이스, 애플리케이션의 기본 스토리지로 사용하기에 특히 적합하다. 
임의 읽기 및 쓰기에 의존하는 데이터베이스 스타일의 앱과 장시간의 지속적인 읽기 및 쓰ㅡ기를 수행하는 처리량 집약적 앱에 모두 적합하다. 

**Amazon EFS(Amazon Elastic File System)**
완전히 탄력적인 서버리스 파일 스토리지를 제공하므로 스토리지 용량과 성능을 프로비저닝하거나 관리하지 않고 파일 데이터를 공유할 수 있다.

**NFS(Network File System)**
네트워크상의 효율적인 파일 공유를 위한 파일 액세스 스토리지 프로토콜 또는 규칙

**Amazon SNS(Simple notification Service)**
게시자에서 구독자로 메세지를 전송하는 관리형 서비스이다. 게시자는 논리적 액세스 지점 및 커뮤니케이션 채널인 주제에 메시지를 전송하여 구동자와 비동기식으로 통신한다.

**Amazon SQS(Simple Queue Service)**
내구력 있고 가용성이 뛰어난 보안 호스팅 대기열을 제공하며 이를 통해 분산 소프트웨어 시스템과 구성 요소를 통합 및 분리할 수 있따. SQS를 사용하면 데이터를 대기열에 넣어 앱을 확장할 수 있따.

메세지가 한번만 처리되도록 하려면 솔루션 설계자는 ChangeMessageVisibility API 호출을 사용하여 가시성 제한 시간을 늘려야한다. 가시성 제한 시간은 SQS 대기열에서 수신한 메시지가 다른 소비자에게 숨겨지는 시간을 결정한다.

**FIFO(First In First Out)**
주문이 접수된 순서대로 처리

**AWS Secrets Manager**
수명 주기 동안 데이터베이스 보안 인증, 앱 보안 인증, ..등을 할 수 있고, 보안 인증 정보를 저장하면 앱 또는 구성 요소를 조사할 수 있는 누군가로 인해 손상될 가능성을 방지할 수 있다.
암호에 대한 자동 교체 일정을 구성할 수 있다. 따라서 간기 보안 암호로 장기 보안 암호를 교체할 수 있어 손상 위험이 크게 줄어든다. 보안 비밀에 대한 자동 순환을 지원한다.


**AWS KMS(Key Manager System)**
데이터를 보호하는 데 사용하는 암호화 키를 쉽게 생성하고 제어할 수 있게해주는 관리형 서비스

**Amazon CloudFront**
.html, .css, .js 및 이미지 파일과 같은 정적 및 동적 웹 콘텐츠를 사용자에게 더 빨리 배포하도록 지원하는 웹 서비스이다. CloudFront는 엣지 로케이션이라고 하는 데이터 센터의 전 세계 네트워크를 통해 콘텐츠를 제공한다. CloudFront를 통해 서비스하는 콘텐츠를 사용자가 요청하면 지연 시간이 가장 낮은 엣지 로케이션으로 요청이 라우팅되므로 가능한 최고의 성능으로 콘텐츠가 제공된다. (UDP 지원x)


**Global Accelerator**
전 세계에 분산된 엔드포인트를 연결하는 서비스이다.(UDP Level) 
글로벌 어플리케이션 가용성 및 성능 향상, game, iot, voice와 같은 non HTTP에도 적합하다. 

**AWS Global Accelerator 는 Amazon CloudFront와 어떻게 다를까?**
Aws Global Accerlerator와 Amazon CloudFront는 AWS 글로벌 네트워크와 전 세계 엣지 로케이션을 사용하는 별도의 서비스다. 
CloudFront는 캐시 가능한 콘텐츠(ex: 이미지 및 비디오)와 동적 컨텐츠(ex: API가속 및 동적 사이트 제공) 모두에 대한 성능을 향상시킨다. 
Global Accelerator는 HTTP가 아닌 사용 사례뿐만 아니라 특히 고정 IP주소 또는 결정적이고 빠른 지역 장애 조치가 필요한 HTTP 사용 사례에도 적합하다. 두 서비스 모두 DDoS 보호를 위해 AWS Shield와 통합된다.

**Amazon Aurora**
MySQL 및 PostgreSQL과 호환되는 완전 관리형 관계형 데이터베이스 엔진이다. 오로라는 기존 애플리케이션을 거의 변경하지 않고도 MYSQL의 처리량을 최대 5배 PostgreSQL의 처리량을 최대 3배 제공할 수 있다. 쓰기 요청보다 읽기 요청을 더 많이 처리한다. (Feat. 고가용성 유지 = 다중 AZ배포)

**AWS Network Firewall(클라우드 방화벽)**
네트워크 트래픽을 세부적으로 제어하는 방화벽 규칙을 정의할 수 있다.(트래픽 검사나 필터링 수행) network firewall은 firewall manager와 연동되므로, Network firewall 규칙을 기반으로 정책을 구축한 후 해당 정책을 중앙에서 VPC 및 계정 전반에 적용할 수 있다.

**Amazon QuickSight**
시각화를 제공한다, IAM 제공 XXXXXXXX

**IAM 역할**
EC2인스턴스가 S3 버킷에 액세스할 수 있는지 확인을 해야한다. 
설계자는 S3 버킷에 대한 액세스 권한을 부여하는 IAM 역할을 생성해야한다.

**Gateway Load Balancer**
방화벽, 침입 탐지 및 방지 시스템, 심층 패킷 검사 시스템과 같은 가상 어플라이언스를 배포, 규모 조정 및 관리할 수 있다. 투명한 네트워크 게이트웨이를 결합하고 수요에 따라 가상 어플라이런스를 조정하면서 트래픽을 분산한다. 웹 앱을 어플라이언스와 통합하여 트래픽이 웹 서버에 도달하기 전에 앱에 대한 모든 트래픽을 검사해야 한다.

**Network Load Balancer**
TCP/UDP

**Application Load Balancer**
우선 순위에 따라 리스너 규칙을 평가하여 적용할 규칙을 결정한 다음, 규칙 작업의 대상 그룹에서 대상을 선택한다.ex) HTTP 트래픽을 HTTPS로 리디렉션 -> HTTPS를 사용하도록 모든 요청을 웹사이트로 전달

**Amazon EBS 스냅샷**
amazon EBS 스냅샷이라는 시점 사본을 만들어 Amazon EBS 볼륨의 데이터를 백업할 수 있따.
솔루션 설계자는 프로덕션 데이터를 테스트 환경으로 복제하는 데 필요한 시간을 최소화해야 한다.
이때 EBS FSR(빠른 스냅샷 복원)을 사용하면 생성 시 완전히 초기화된 스냅샷에서 볼륨을 생성할 수 있다. 이렇게 하면 처음으로 블록에 액세스할 때 블록에 대한 I/O 작업의 대기시간이 제거되고 빠른 스냅샷 복원을 사용하여 생성된 볼륨은 프로비저닝된 모든 선능을 즉시 제공한다.

**내구성, 가용성, 비용 효율성**
내구성 - 어떤 조건에서도 데이터가 유지할 수 있는 퍼센트 99.999999% 내구성이란 인프라가 실패하더라도 표준 S3플랫폼에 저장된 데이터의 손실 가능성은 사실상 0에 가깝다는 의미
가용성 - 객체에 대한 지속적인 요청을 처리할 수 있는 능력을 퍼센트
비용 효율성 - 비용을 얼마나 절약할 수 있눈지

**Amazon S3(Amazon Simple Storage Service)**
업계 최고의 확장성, 데이터 가용성, 보안 및 성능을 제공하는 객체 스토리지 서비스.
다양한 사용 사례에서 원하는 양의 데이터를 저장하고 보호할 수 있다.
가장 저렴한 정적 사이트 호스팅 = S3
빠르게 증가하는 수요를 수용할 수 있는 확장 가능한 솔루션

**S3 - Intelligent Tiering(지능형 계층화)**
머신러닝을 통해서 자동으로 파일의 티어(클래서)를 변경하는 서비스이다.
최근에 파일을 자주 접근하면 스탠다드에 옮기고, 접근빈도가 낮으면 IA로 옮기고, 다시 많이 찾으면 스탠다드로 옮기는 형식이다.
사용자가 파일에 무작위로 액세스한다. 지능형 계층화는 객체 크기나 보존 기간과 관계 없이 액세스 패턴이 알 수 없거나 변경되거나 예측할 수 없는 데이터에 이상적인 스토리지 클래스이다.

ex) 일부 파일은 자주 액세스 되는 반면 다른 파일은 예측할 수 없는 패턴으로 거의 액세스되지 않습니다. 

**S3 - IA(Infrequent Access)**
자주 접근되지는 않으나 접근시에 빠른 접근이 요구되는 파일이 많을 시에 저렴한 가격에 IA에 보관하면 유용하다. 일반 S3에 비해 비용은 저렴하나 데이터를 불러올 때마다 추가 비용이 발생한다!

**S3 - One Zone IA(단일영역 IA)**
기본적으로 IA과 같지만 하나의 AZ에만 데이터를 저장하는 클래스이다.
덜 중요하고 자주 사용되지 않는 데이터를 저장하는데 접근 가능

**S3 Glacier // Deep Archive(빙하에 데이터를 꽁꽁 얼려 보관하는 컨셉~)**
자주 액세스되지 않는 데이터를 저장하는데 사용, 아무도 볼거 같지도 않아 쓸모는 없는데 법적인 이유 등으로 보관은 해야하는 데이터들을 보통 취급한다. 데이터 접근시 대략 분~ 시간 소요 될 젇도로 상당히 오래걸린다.

**AWS Cost Explorer**
비용 및 사용량을 보고 분석할 수 있게 해주는 도구이다. 사용량 및 비용을 탐색할 수 있다. 최대 지난 12개월간의 데이터를 보고, 이후 12개월 동안 지출할 것으로 예상되는 금액을 예측하며, 구매할 예약 인스턴스에 대한 추천을 받을 수 있다. Cost Explorer를 사용하여 추가 조사가 필요한 영역을 알아내고, 비용을 이해하는 데 활용할 수 있는 추세를 파악할 수 있따. 

**AWS Config**
AWS 리소스의 구성을 평가, 감사 할 수 있는 서비스, config를 사용하면 S3 버킷 구성의 변경 사항을 모니터링하고 기록할 수 있다.(제한은 불가하다.) Config를 활성화하고 적절한 규칙을 활성화하면 S3버킷에 무단 구성 변경이 발생하지 않도록 할 수 있다. 구성 변경 = Config

**CloudWatch 대시보드 공유**
AWS 계정에 직접 액세스 할 수 없는 사용자와 CloudWatch 대시보드를 공유할 수 있다. 이렇게 하면 팀 간 그리고 이해 관계자 및 조직 외부의 사람들과 대시보드를 공유할 수 있따. 대시보드를 공유 받는 모든 사람에게는 계쩡의 단원에 나열된 권한이 부여된다. 

**SSO(Single Sign-On)**
1회 사용자 인증으로 다수의 앱 및 웹사이트에 대한 사용자 로그인을 허용하는 인증 솔루션이다.
양방향 신뢰가 필요하다.

**Amazon Redshift**
프로비저닝된 데이터 웨어하우스를 구성하지 않아도 데이터를 액세스하고 분석할 수 있따. 리소스가 자동으로 프로비저닝하고 데이터 웨어하우스 용량이 지능적으로 크기 조정되어 가장 까다롭고 예측할 수 없는 워크로드에도 빠른 성능을 제공한다. 매우 대형의 데이터 집합을 처리하고 분석할 수 있음

**Amazon Kinesis Data Streams**
모든 규모의 데이터 스트림을 쉽게 캡처, 처리 및 저장할 수 있는 서버리스 스트리밍 데이터 서비스
대규모의 데이터를 실시간으로 수집 및 처리한다.
stream으로 구성되어 있고, 1개의 stream엔 여러개의 샤드가 존재한다.
데이터가 들어오면 삭제가 불가능하다.

**Amazon Kinesis Data Firehose**
데이터를 S3에 직접 로드할 수 있어 운영상 가장 효율적이다.
수명주기도 관리됨

**CloudTrail**
API

**IAM**
SSH 키나 공유 암호 없이 EC2 인스턴스 및 AWS 서비스에 대한 액세스를 안전하게 제공한다.
인스턴스에 원격으로 안전하게 액세스하고 관리할 수 있음. AWS와 작동하고 well-architected 프레임워크를 따르는 반복 가능한 프로세스임

**Provisioned IOPS SSD 볼륨**
프로비저닝된 IOPS SSD 볼륨은 SSD로 지원된다. 짧은 지연 시간이 필요한 중요하고 IOPS 집약적이며 처리량 집약적 워크로드를 위해 설계된 EBS 스토리지 볼륨이다. 일관되고 예측 가능한 성능을 위해 높은 수준의 I/O 작업을 위해 제작되었다.

**Amazon AppFlow**
클릭 몇 번으로 SaaS(software as a service) 앱과 AWS 서비스 간 양방향 데이터 흐름을 자동화 할 수 있다. 원하는 빈도로 일정에 따라 응답으로 또는 온디맨드로 데이터 흐름을 실행할 수 있다. 

**Direct Connect**
대역폭 제한을 우회하고 인터넷 액세스에 대한 영향을 최소화 할 수 있는 전용의 안전한 고성능 연결을 제공한다. 내부 사용자의 인터넷 연결에 미치는 영행을 최소화 할 수 있는 장기 솔루션 
일관되게 낮은 지연시간을 갖는 고가용성 연결

**회사의 중요한 데이터가 실수로 삭제되지 않기 위해서**
1) S3 버킷에서 버전 관리를 활성화한다.
버전 관리를 활성화하면 여러 버전의 객체가 버킷에 저장된다.

2) S3 버킷에서 MFA 삭제를 활성화한다.
삭제를 확인하고 실수로 삭제되는 것을 방지하기 위한 추가 단계를 구성하는 MFA

3) 객체의 지역 간 복제를 활성화한다.

**Amazon Macie**
기계학습 및 패턴 일치를 사용하여 민감한 데이터를 검색하고 보호하는 데이터 보안 및 데이터 개인 정보 보호 서비스.

**ElastiCache**
AWS에서 제공하는 이 메모리 캐싱 서비스
redis, memcached 두가지 엔진을 지원한다.
높은 확장성과 성능을 제공한다.

**EFS(Elastic File System)**
클라우드 기반 파일 스토리지 서비스
다중 AZ
높은 가용성
window 지원 x
자동 확장

**AWS Systems Manager Run Command**
run command를 사용하여 관리형 노드의 구성을 원격으로 안전하게 관리할 수 있다. 일반적으로 관리 작업을 자동화하고 대규모로 일회성 구성 변경을 수행할 수 있다.

**EventBridge**
AWS에는 다양한 이벤트에 대한 처리를 쉽게 구성하고, 이벤트 처리를 위한 자동화된 경로를 제공한다.
이벤트를 사용하여 애플리케이션 구성 요소를 서로 연결하는 서버리스 서비스로, 확장 가능한 이벤트 기반 앱을 더 쉽게 구축할 수 있다. 타사 인증서는 자동으로 갱신할 수 없음 그때 이벤트 브릿지를 사용해서 타사 인증서 만료가 가까워지면 Amazon EventBridge를 사용하여 알림을 보낸다. 인증서를 수동으로 순환한다.

**매일 아침 같은 시간에 이메일 보내기**
1. Simple email
2. AWS EventBridge with Lambda

**Amazon FSx for Windows File Server**
Windows 파일 공유, 완전히 관리되고 확장 가능하며 신회성이 높은 파일 스토리지 솔루션으로 기본 Windows 파일 서버 경험을 즐길 수 있다.

SG(Security Group)가 프라이빗 서브넷에 대한 입력을 허용한다는 것은 다른 모든 것이 차단된다는 의미
이 SG를 DB인스턴스에 연결하면 필수 EC2 인스턴스가 있는 프라이빗 서브넷 인스턴스를 제뢰한 모든 항목이 차단된다.

**Amazon Rekognition**
사전 훈련된 레이블 감지 모델을 사용하여 이미지에서 부적절한 콘텐프를 감지할 수 있는 클라우드 기반 이미지 및 비디오 분석 프로그램

**Transcribe**
오디오 및 비디오 파일에서 자동으로 음성을 텍스트로 변환한다.

**polly**
텍스트를 음성으로 변환

**Translate**
택스트 번역 서비스로, 다국어 번역이 가능

**Lex**
챗봇, 음성인식 기능을 개발할 수 있는 서비스

**Connect**
콜센터를 쉽게 구축하고 관리할 수 있는 서비스

**Comprehend**
텍스트 분석 서비스로, 감정분석, 언어감지, 토픽 모델링 등의 기능을 제공한다.

**SageMaker**
머신러닝 모델을 쉽게 구축하고 운영할 수 있는 서비스 -> 개발자들이 많이 사용

**AWS Fargate**
Amazon EC2 인스턴스의 서버나 클러스터를 관리할 필요 없이 컴테이너를 실행하기 위해 Amazon ECS에 사용할 수 있는 기술이다. Fargate를 사용하면 더 이상 컨테이너를 실행하기 위해 가상 머신의 클러스터를 프로비저닝, 구성 또는 조정할 필요가 없다. 인프라 관리가 필요 없으므로 빠르게 배포하고 스케일링 할 수 있따.

**AWS Certificate Manager**
ACM은 AWS 웹 사이트와 앱을 보호하는 퍼블릭 및 프라이빗 SSL/TLS 인증서와 키를 만들고, 저장하고, 생신하는 복잡성을 처리한다. ACM에서 직접 발급하거나 서드 파티 인증서를 ACM 관리 시스템으로 가져오는 방법으로 통합 AWS 서비스에 대한 인증서를 제공할 수 있따.






