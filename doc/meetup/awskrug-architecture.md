# [AWSKRUG #architecture 공식문서](https://github.com/awskrug/architecture-group)



## AWSKRUG #architecture 소모임 - 19번째 모임 (2월 28일)

### 발표 세션
 - (선데이토즈) "IDC에서 AWS로 Redis 데이터 이전하기"
 - (VCNC) "서비스 중단 없이 Amazon EKS로 옮긴 이야기"

### 세션 메모
#### "서비스 중단 없이 Amazon EKS로 옮긴 이야기"
1. 타다 서비스, 내부 클러스터에서 EKS 서울 나오자마자 바로 이전함.
2. 아키텍쳐
   - 클라이언트 ~ 프런트+백엔드 서버(EKS) ~ 레디스/오로라(MySQL)
   - 앱 클라이언트 위치 정보 : 클라이언트 서버 ~ gRPC ~ 백엔드 서버(EKS) <-> Elasticache 레디스 PubSub <-> 백엔드 서버(EKS)
   - 트랜잭션 처리 : 클라이언트 서버 ~ SQS ~ 백엔드 서버(EKS) ~ RDS Aurora(MySQL)
   - NLB + k8s 로드밸런싱
   - Route53 weight-based B/G deployment : EC2 k8s cluster -> EKS

#### "IDC에서 AWS로 Redis 데이터 이전하기"
1. IDC 계약 만료로 서비스를 AWS로 이전한 케이스
2. 개인 [블로그 글](https://mingrammer.com/redis-migration/)로 공개함
3. 키워드
   - Redis Multimaster / Replication / Migration
   - SSH Turneling
   - 병렬 데이터 마이그레이션 스크립트(Python) e.g. Golang


## AWSKRUG #architecture 소모임 - 18번째 모임 (1월 31일)

### 발표 세션
 - (뒤끝) "BaaS 아키텍트의 고민"
 - (OSCI) "DevOps 최고의 친구 AWS"

### 세션 메모
#### (뒤끝) "BaaS 아키텍트의 고민"
1. thebackend.io
2. 계층
   - 로그 레이어
     - EK 스택 
     - 대용량 로그 샤딩 문제 
   - 퍼시스선트 레이어
     - RDBMS(Aurora MySQL, 트랜잭션 니즈 온리)/NoSQL(DynamoDB, 트랜잭션이 필요 없는 거의 모든 데이터)
     - 단일 병목지점
     - B2B 멀티 키 이슈 == 비용
   - 캐시 레이어
     - ElastiCache Redis
     - 단일 병목지점
     - VPN으로 VPC 리소스 접근 후 사용
   - 비즈니스 레이어
     - AWS 이해가 있는 서버개발자를 찾기 어려움
     - 모든 리소스를 AWS로 통일, 관리포인트 분리시 리소스 비용 낮아짐과 동시에 서버개발자 인건비가 올라감.
     - stateless -> statefull 비즈니스로 자연스럽게 하중이동됨
     - 로컬, 알파, 베타, 라이브
   - SDK
     - API 비공개
     - SDK 로만 제공, 사업적 결정
     - 3rd Party SDK 는 무조건 분리
3. 팁
   - 서비스매니저, 비밀번호 관리는 KMS
   - 슬랙+람다, EC2 on/off/live 현황 조회
   - 성능 t2 < t3, 비용 t2 > t3
   - Aurora Performance Insight, 배민 기술블로그
   - CloudWatch Insight
   - Infra isolation with NLB
   - Aurora Serverless scaliablity : Scale-up/down, not in/out

#### (OSCI) "DevOps 최고의 친구 AWS"
1. 기존 대기업 업체의 운영 효율화 컨설팅 등, www.osci.kr
2. Atlassian 프리미엄 파트너, 기술영업
3. DevOps 분업 및 조직 문화에 대한 발표
