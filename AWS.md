* 클라우드의 종류
  * 클라우드 컴퓨팅 모델
    * IaaS : 인프라만 제공 (주방만 빌리기)
    * PaaS : 인프라 + OS + 런타임 제공 (주방 + 주방기기 + 재료 빌리기)
    * SaaS : 모두 제공 (전부 다 빌리기)
  * 클라우드 컴퓨팅 배포 모델
    * 공개형
    * 폐쇄형
    * 혼합형

* EC2 (Elastic Compute Cloud)
```
서버를 고무줄 처럼 늘였다 줄였다 가능
트래픽이 많이 몰리는 때에 원하는대로 조절 가능
```

* S3 (Simple Storage Service)
```
무한 확장 되는 온라인 창
```

* IaaS (Infrastructure as a Service)
```
인프라만 제공
OS를 직접 설치하고 필요한 소프트웨어를 개발해서 사용
즉 가상의 컴퓨터를 하나 임대하는 것과 비슷함
예 : AWS EC2
```

* Paas (Platform as a Service)
```
인프라 + OS + 기타 프로그램 실행에 필요한 부분 (런타임)
바로 코드만 올려서 돌릴 수 있도록 구성
예 : Firebase, Google App Engine 등
```

* SaaS (Software as a Service)
```
인프라 + OS + 필요한 소프트웨어가 제공됨
서비스 자체를 제공
다른 세팅 없이 서비스만 이용
예 : Gmail, DropBox, Slack, Google Docs
```

* AWS의 구조

![image](https://github.com/user-attachments/assets/5a822dd6-f5b3-4410-84b8-a5abf8ca1b25)

* 리전
```
AWS의 서비스가 제공되는 서버의 물리적 위치
전 세계에 흩어져 있으며 큰 구분 (동남아, 유럽, 북아메리카 등등)으로 묶여 있음
각 리전에는 고유의 코드가 부여됨 (예 : 서울 ap-northeast-2)
리전별로 가능한 서비스가 다름
```

* 글로벌 서비스 & 지역서비스
```
글로벌 서비스
  CloudFront
  IAM
  Route53
  WAF
지역 서비스
  대부분의 서비스
  S3
```

* 루트 유저
```
생성한 계정의 모든 권한을 자동으로 가지고 있음
사용을 자제하고 MFA 설정 필요
루트 유저는 관리용으로만 이용 : 계정 설정 변경, 빌링 등
AWS API 호출 불가 (AccessKey/Secret AccessKey 부여 불가)
```

* IAM 유저
```
IAM (Identity and Access Management)을 통해 생성한 유저
기본 권한 없음 : 따로 권한 부여 필요
꼭 사람이 아닌 어플리케이션 등의 가상의 주체를 대표할 수도 있음
AWS API 호출 가능
  AccessKey : 아이디 개념
  Secret Access Key : 패스워드 개념
빌링 관련 권한은 루트 유저가 허용해야 함
```
