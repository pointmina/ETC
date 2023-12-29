# AWS_SAA

IAM : Identity amd Access Management, Global service
-
- 그룹에는 user만 배치할 수 있으며, 다른 그룹은 포함할 수 없다.
- AWS 최소권한 규칙을 원칙으로 한다.
- 사용자들은 자신만의 자격증명을 통해 서비스에 접근한다.

![image](https://github.com/pointmina/AWS_SAA/assets/68779817/29d8a0a4-efd2-40c3-8263-9805feafbc37)

*문장구성요소*
1. sid : 문장 id : 문장의 식별자
2. effect : 문장이 특정 api에 접근하는 걸 허용할지 말지에 대한 내용
3. principal : 특정 정책이 적용될 사용자, 계정, 혹은 역할로 구성
4. action : effect에 기반해 허용 및 거부되는 api 호출 목록
5. resource : 적용될 action의 리소스 목록

<IAM - Password Policy>
- MFA : Multi Factor Authentication : 비밀번호 + 보안 장치
- 루트 어카운트를 무조건 지켜야 IAM users도 지킬 수 있음
- 그래서 MFA를 사용하는 건데 이거가 좋은게 비번이 털려도 계정은 ㄱㅊ아
- ex) Google Authenricator, Authy, Yubikey....
- Access Key가 겁나 중요함, 그 누구랑도 공유해서는 안된다!

EC2 : Elastic Compute Cloud
-
- AWS에서 제공하는 서비스형 인프라 스트럭처, 클라우드는 필요할 때마다 언제든지 컴퓨팅을 대야할 수 있고 EC2가 바로 그예시이다.
- bootstrapping : 머신이 작동될 때 명령을 시작하는 것

<EC2 Instances Types>
1. General Purpose
: 웹서버, 코드 저장소와 같은 다양한 작업에 적합하다. (ex. t2.micro)
2. Compute Optimized
: when require high performance processors (ex. Media transcoding, High performance....)
3. Memory Optimized
: Big data 대규모 data sets을 처리하는 유형에 적합
4. Storage Optimized
: require high, swquential read and write access to large data sets

- Security Group
: 여러 인스턴스에 연결할 수 있으며 일대일 관계일 필요는 없다.
- 한 보안그룹을 SSH access에서 분리시켜 놓는 것이 바람직하다.
- inbound traffic은 기본적으로 blocked되어 있고
- outbound 는 기본적으로 허용되어 있따.

<Classic Ports to Knows>
- 22 = SSH(Secure Shell) : log into a Linux instance (서버 내부와 연결_
- 21 = FTP(File Transfer Protocol) : upload files into a file share
- 22 = SFTP(Secure File Transfer Protocol) : upload file using SSH
- 80 = HTTP : access unsecured websites
- 443 = HTTPS : access secured websites
- 3389 = RDP (Remote Desktop Protocol) : log into a Windows instance

<EC2 Instances Purchasing Options>
- On-Demand Instances : short workloads, predictable pricing, pay by second, un-interrupted workloads, no upfront payment
- Spot Instances : short workloads, cheap, can lose instances (less reliable), MOST cost-efficient, Not suitable for critical jobs or databases
...

<Spot Fleets> : set of Spot Instance + (optional) On-Demand Instances
- try to meet the target capacity with price constraints
- Spot Fleets allow us to automatically request Spot Instances with the lowest price
- 긍까 플릿이 가장 적합한 런치풀을 선택하고 용량이나 원하는 목표에 다다르면 인스턴스 중지
- lowestPrice: from the pool with the lowest price (cost optimization, short workload)
- diversified: distributed across all pools (great for availability, long workloads)
- capacityOptimized: pool with the optimal capacity for the number of instances
-  priceCapacityOptimized (recommended): pools with highest capacity available, then select 
the pool with the lowest price (best choice for most workloads)
- 여러개의 런치풀과 인스턴스 유형을 정의할 수 있다.

- 간단한 스팟 인스턴스 요청은 요구사항(instance유형, AZ)을 정확히 알때
- 스팟플릿은 충족하는거 모두 선택
  
IP
-

<Private vs Public IP (IPv4)>
1) Public IP :
- 기기가 인터넷 상에서 식별될 수 있다.
- 전체 웹에서 유일한 것 (ID느낌?)
- 구글 검색으로 IP 지리적 위치를 쉽게 찾을 수 있다.
- If your machine is stopped and then started, the public IP can change


2) Private IP
- 기기가 오직 사설 네트워크 안에서만 식별 될 수 있따.
- 사설 네트워크 안에서만 유일한 것이면 된다.
- 두개의 다른 사설 네트워크는 같은 IP를 가질 수 있다.
- 지정한 범위의 IP만 사설 IP로 사용될 수 있따.

3) Elastic IP
- 원하는 기간만큼 소유할 수 있고, *고정적인 공용 IPv4(Fixed pulbic IP)* 를 할당하고 싶을 때 사용한다.
- attach it to one instance at a time
- 이거 사용하는 것보다 그냥 Public IP에 DNS 이름을 할당하는 것이 좋다.


Placement Group
-

1) Cluster : 클러스터 배치 그룹
![image](https://github.com/pointmina/AWS_SAA/assets/68779817/8a4757cb-7bf7-473f-b33e-2a536532de6f)

- 동일한 Rack에 배치 => Great Network
- Rack에 실패 발생하면, 모든 EC2 인스턴스 실패 ㅋㅋ
- 실패가 전파 될 수 있음
- Use case : Big Data job that needs to complete fast, Application that needs extremely low latency and high network throughput

2) Spread : 분산배치그룹

![image](https://github.com/pointmina/AWS_SAA/assets/68779817/c5e35edf-ccf1-41e5-b95b-73320d28f6fd)

- 여러 AZ에 걸쳐 있을 수 있고, 동시 실패 위험 감소
- AZ당 인스턴스 7개로 제한
- Use case : Application that needs to maximize high availability, Critical Applications where, each instance must be isolated from failure from each other

3) Partition : 분할 배치 그룹

![image](https://github.com/pointmina/AWS_SAA/assets/68779817/5a5c8704-f6ed-4c63-b23b-ae7a91aa8ccc)

- Up to 7 partitions per AZ
- 여러 파티션은 동일 리전의 여러 가용영역에 걸쳐 있을 수 있다.
- Up to 100s of EC2 instances
- 다른 파티션의 Rack과 분리된다.
- Use cases: Big Data APP (HDFS, HBase, Cassandra, Kafka)

ENI : Elastic Network Interfaces : 탄력적 네트워크 인터페이스
-
-  EC2 인스턴스가 네트워크에 액세스 할 수 있게 해준다.
-  Primary private IPv4, one or more secondary IPv4
- One Elastic IP (IPv4) per private IPv4
- One Public IPv4
- One or more security groups
- A MAC address
- EC2 인스턴스와 독립적으로 ENI를 생성하고, 즉시 연결하거나 장애조치를 위해 EC2인스턴스에서 이동시킬 수 있따.
- AZ에서 바운딩하고, 특정 AZ에서만 사용가능하다.
- *장애조치를 위해 instance간 ip를 이동시킬수 있다.*







