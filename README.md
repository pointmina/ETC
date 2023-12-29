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

IP
-

<Private vs Public IP (IPv4)>
1) Public IP :
- 기기가 인터넷 상에서 식별될 수 있다.
- 전체 웹에서 유일한 것 (ID느낌?)
- 구글 검색으로 IP 지리적 위치를 쉽게 찾을 수 있다.

2) Private IP
- 기기가 오직 사설 네트워크 안에서만 식별 될 수 있따.
- 사설 네트워크 안에서만 유일한 것이면 된다.
- 두개의 다른 사설 네트워크는 같은 IP를 가질 수 있다.
- 지정한 범위의 IP만 사설 IP로 사용될 수 있따.

3) Elastic IP
- 원하는 기간만큼 소유할 수 있고, <u>고정적인 공용 IPv4(Fixed pulbic IP)</u>를 할당하고 싶을 때 사용한다.
- attach it to one instance at a time
- 이거 사용하는 것보다 그냥 Public IP에 DNS 이름을 할당하는 것이 좋다,

- 









