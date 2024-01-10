Email: 23dj30@ywdcloud.com
계정 ID: 23dj307
UserPW: Aicore30!

강사 URL: https://github.com/digicope/aws_cp

로그인 URL: https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fconsole.aws.amazon.com%2Fconsole%2Fhome%3FhashArgs%3D%2523%26isauthcode%3Dtrue%26nc2%3Dh_ct%26src%3Dheader-signin%26state%3DhashArgsFromTB_eu-north-1_998509523725e187&client_id=arn%3Aaws%3Asignin%3A%3A%3Aconsole%2Fcanvas&forceMobileApp=0&code_challenge=IuNYfpvOjSqx-bxhNiAMpn0n6dT40O923ECJRgR1uAw&code_challenge_method=SHA-256

개요
- 클라우드의 개념과 네트워크 기초
- AWS 클라우드 및 가치 제안 정의
- AWS 클라우드의 경제적 측면 파악
- 클라우드 아키텍처의 다양한 설계 원리 나열
---

![[스크린샷 2023-12-22 091142.png]]

---
AWS  Certified Cloud Practitioner 과정 응시 안내서
- https://aws.amazon.com/ko/certification/certified-cloud-practitioner/
![[Pasted image 20231222102936.png]]

# AWS 아키텍처 설계
## Chapter 01. AWS 소개

01. On-premise 환경

- On-premise 환경 = Local 환경
- 컴퓨팅 자원, 스토리지 자원, 네트워크 연결 (공유기)
- 이러한 자원을 직접 구현하여 사용하는 것을 On-premise 환경이라고 칭함

02. Cloud 환경
03. AWS

**클라우드 컴퓨팅의 장점**

- 자본 비용을 가변 비용으로 대체 가능
	- 고정 비용 (인건비, 임대료, 장비 비용) -> 가변 비용 (클라우드 비용)
- 규모의 경제로 얻게 되는 이점이 많음
	- 개인이 서버를 구축하는 비용보다 AWS 같은 빅테크 기업의 서버를 쓰는 것에 대한 비용적인 규모
- 용량 추정할 필요가 없음
	- 용량 부족이 생길 일이 없음
- 속도 및 민첩성 개선
	- 에러 발생 시, 가상 머신을 다시 만들기만 하면 됨
- 중요한 문제에 집중
	- 서버를 운용하기 위한 투자 시간 감축 가능
- 몇 분 만에 전 세계에 배포

### 1. AWS Global Infrastructure
- AWS 글로벌 클라우드 인프라는 업계에서 가장 안전하고 광범위하고 안정적인 클라우드 플랫폼
- 전 세계 데이터 센터를 통해 완전한 기능을 갖춘 200가지가 넘는 서비스를 제공 
- 클릭 한 번으로 전 세계 모든 위치에 애플리케이션 워크로드를 배포하거나 한 자릿수 밀리초의 지연 시간으로 최종 사용자에게 더 가까운 위치에 특정 애플리케이션을 배포해야 하는 경우 언제 어디서나 필요할 때 AWS의 글로벌 인프라를 사용 가능
- AWS는 전 세계적으로 수백만 명의 활동 고객과 수만 개의 파트너로 이루어진 가장 큰 규모의 가장 역동적인 에코시스템을 갖춤
- 스타트업, 엔터프라이즈, 공공 부문의 조직을 비롯해 규모에 상관없이 거의 모든 산업의 고객이 AWS에서 다양한 사용 사례를 운영하고 있습니다.



Availability Zone (가용 영역), Region (지역)
- Cloud의 공통적인 용어로 전 세계의 데이터 센터
- 알파벳 A, B, C, D로 지역에 위치한 데이터 센터를 구분
- 서비스 지역을 가용 영역, 지역 중 선택을 고려해야 함
- 예) 미국 동부 (버지니아 북부) : us-east-1, 아시아 태평양 (서울) ap-northeast-2

Edge Location
- cache (disk cache), 직접 액세스 하기엔 시간이 많이 걸리기에 주변 국가에 caching을 미리 해둠
- 트래픽이 많으면 인터넷 속도를 보장할 수 없음
- 인터넷이기에 보안에 취약함
- caching할 서버를 만듦


## Chapter 02. Amazon S3

- 스타트업 기업이 업무에 필요한 데이터를 쉽고 안전하게 저장, 배포, 분석할 수 있는 스토리지 서비스를 필요로 하고 있음

### 1. Amazon S3 (Simple Storage Service)

Amazon S3 특징
- Object  Storage (객체 스토리지)
	- Block Storage vs Object Storage
- 최고의 성능, 확장성, 가용성, 내구성
- 이벤트 트리거 기능 제공
	- 어떠한 사고가 발생하는 것을 감지 가능

Amazon S3 접근 방법
- Management Console + CLI + SDK -> API -> Amazon S3 bucket

Amazon S3 사용사례
- 콘텐츠와 미디어 파이일 저장 및 배포
- 정적 웹사이트 호스팅
- 백업 및 복원
- 데이터 레이크와 빅데이터 분석
	- 바깥에서 수집된 데이터를 실시간으로 저장하는 기능도 수행

Amazon S3 접근 권한
- 버킷 소유자 <-> 기본 설정 <-> 비공개
- 버킷 소유자 <-> 공개 <-> 공개
- 버킷 소유자 <-> 접근 정책 <-> 일부 공개

Amazon S3 Transfer Acceleration

Amazon S3로 대용량 데이터 이동
- AWS Snowball - 테라바이트/페타바이트 규모 데이터 이동
- AWS Snowmobile - 엑사바이트 규모 데이터 이동

### 2. Amazon S3 요금 및 스토리지 클래스

S3 Standard - 자주 접근하는 데이터 보관

S3 Standard-IA - 자주 접근하지는 않지만 필요할 때 빠른 접근이 필요한 데이터 보관

S3 One-Zone-IA - 재생산이 가능하고 자주 접근하지 않는 데이터 보관

S3 Glacier - 아카이빙 데이터 보관
- 데이터 아카이빙 및 장기 백업을 위한 안전하고, 내구성이 뛰어나며 매우 저렴한 스토리지 클래스
- AWS 리전 내의 최소 3개의 가용 영역에 데이터를 자동 분산 저장
- S3 Gracier는 3가지 검색 옵션을 제공
- S3 Glacier는 3가지 검색 옵션을 제공
	- 신속 검색 / 표준 검색 / 대량 검색
- S3 Glacier Deep Archive는 2가지 검색 옵션을 제공
	- 표준 검색 / 대량 검
S3 Glacier Deep Archive - 아카이빙 데이터 보관, 가장 저렴한 스토리지

Amazon S3 사용이 적합한 경우
- 한 번 쓰고 여러 번 읽어야 하는 경우
- 콘텐츠가 다양하고, 데이터 양이 지속적으로 증가하는 경우
- 사용자가 많고, 데이터 접근이 일시적으로 급증하는 경우

Amazon S3 사용이 적합하지 않은 경우
- 여러 번 쓰기 작업을 해야 하는 데이터
- 블록 스토리지가 필요한 경우


## Chapter 03. Amazon EC2

- AWS 클라우드 환경을 사용하려는 회사에서 기존 온프레미스 환경의 서버 역할을 수행할 서비스를 사용하고자 함 
-> Amazon EC2 (Elastic Compute Cloud)

### 1. Amazon EC2 (Elastic Compute Cloud)

- 온프레미스 환경의 서버 역할을 수행
	- 웹 서비스 / 데이터베이스 등
- 안전하고 크기 조정이 가능한 컴퓨팅 용량 제공
	- 몇 분 이내 용량 증설 또는 감축 가능
- 기본적으로 온디맨드 요금제 사용
	- 사용한 용량 만큼 지불
- EC2 인스턴스 사용 시 다음과 같은 장점 제공
	- Fast Fail / 데이터 기반 의사 결정 / 빠른 반복

AWS CloudShell 내의 명령어
- https://docs.aws.amazon.com/ko_kr/cli/latest/userguide/cli-services-s3-commands.html
```bash
# cpu 명령어
cat /proc/cpuinfo

# memory 명령어
cat /proc/meminfo
```

사용자 데이터
- 사용자 데이터를 지정해 부팅할 때 명령을 실행할 수 있음
- 사용자 데이터를 사용하면 필요한 상태로 인스턴스를 구성할 수 있

EC2 인스턴스 메타데이터
- 메타데이터는 정의한 키에 대한 값을 가지고 있어 필요한 정보를 호출하여 정보를 파악할 수 있음
- EC2 인스턴스의 다양한 메타데이터를 활용해 구동 중인 인스턴스 설정 및 관리를 수행하는 것이 가능

### 2. Amazon EC2 관련 스토리지 서비스

Amazon EBS (Elastic Block Store)
- EC2 인스턴스에 연결할 수 있는 블록 스토리지가 필요

1. 인스턴스 스토어
- 호스트 컴퓨터에 물리적으로 연결된 디스크에 위치. 특정 유형 인스턴스에 제공
- 인스턴스를 중지/최대 절전 모드/종료하면 데이터가 손실
- 버퍼, 캐시, 스크래치 데이터 및 기타 임시 콘텐츠와 같이 자주 변경되는 정보

2. Amazon EBS
- 네트워크 연결 블록 스토리지. 독립적인 데이터 라이프 사이클
- 연결 해제 후 다른 인스턴스 연결 / 인스턴스 당 다중 볼륨 연결 가능
- EBS 볼륨은 특정 가용 영역 내에 위치. 그 안에서 자동으로 복제
- EBS 스냅샷을 사용하여 Amazon S3에 볼륨 백업이 가능ㄷ

Amazon EBS 유형
- SSD 기반
	- 범용 SSD
	- 프로비저닝 된 IOPS SSD
- HDD 기반
	- 처리량에 최적화된 HDD
	- 콜드 HDD

Amazon EBS Optimized 인스턴스
- Amazon EBS 최적화 인스턴스는 최적화 된 구성 스택 사용
- Amazon EBS I/O를 위한 전용 대역폭을 제공
- 인스턴스 유형에 따라 기본 적용/선택 적용/지원 불가로 구분]





## Chapter 04. Database

Serverless vs Managed




## Chapter 05. AWS Network 1


**VPC (Virtual Private Cloud)**
- AWS를 사용하는 수많은 다른 고객들의 리소스와 조직의 리소스를 격리할 수 있는 논리적인 네트워크 환경이 필요함
- AWS 서비스 중 이러한 요구 사항을 충족할 수 있는 서비스

**Amazon VPC**
- 사용자가 정의하는 논리적으로 격리된 가상 네트워크
- AWS 리소스에 대한 논리적인 격리 제공
- AWS 리소스에 대한 Access Control 및 보안 구성 제공
- AWS 계정 전용 가상 네트워크 환경
- VPC 특정 CIDR 범위를 지정 (IPv4, IPv6)
- VPC에 접근하는 트래픽에 대해 Inbound / Outbound Access 규칙을 적용

**VPC 배포 범위**
- VPC는 리전을 선택하여 배포
	- 해당 리전의 모든 가용 영역을 선택하여 리소스를 배치할 수 있음



























