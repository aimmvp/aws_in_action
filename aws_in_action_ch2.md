###Chapter 2. 5분만에 워드프레스 설치하기

* 블로그 인프라 만들기 : ELB, EC2, MySQL용 RDS, 보안그룹
* 시스템 구성 순서
 1. ELB 생성
 2. MySQL용 RDS 생성
 3. 보안 그룹 생성 및 연결
 4. 2개의 웹 서버 생성
   - 2개의 EC2 가상 서버 생성
   - 아파치 서버와 PHP 설치( yum install php, php-mysql, mysql, httpd )
   - 최신 버저의 워드프레스 내려받아 압축 풀기(http://wordpress.org/latest.tar.gz)
   - 생성된 MySQL용 RDS를 사용하기 위한 워드프레스 구성
   - 아파치 서버 시작

* CloudFoundation > Create a Stack
 1. Select Template
   - https://s3.amazonaws.com/awsinaction/chapter2/template.json
   - key-pare 의 이름이 다를 경우 template 파일을 다운 받은 후 Parameters.KeyName.Default 의 값을 key-pare	의 이름으로 변경 후 Upload a template to Amazon S3 을 통해서 Upload 한다.
 2. Specify Details
   - Stack name 과 KeyName 입력
 3. Options
   - System Tag 입력: Key-System, Value-wordpress
 4. Review
   - 입력 결과 확인 : Estimate Cost 도 확인 가능

* 리소스 그룹 생성
  - Resource Groups > Create a Resource Group
  - Group name : wordpress
  - Tags : system - wordpress
  - Regions : US East(N. Virginia) 애매하면 All Regions


