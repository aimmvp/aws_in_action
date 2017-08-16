###Chapter 3. 가상 서버 사용하기 : EC2

* EC2 시작하기
  1. AWS 관리자 콘솔( http://console.aws.amazon.com )
  2. Region 확인
  3. 탐색기에서 EC2 서비스 클릭
  4. Launch Instance 클릭 ( 가상서버 실행 마섭사 시작 )
    Step 1. Choose an Amazon Machine Image(AMI)
    Step 2: Choose an Instance Type
	Step 3: Configure Instance Details
	Step 4: Add Storage
	Step 5: Add Tags
	Step 6: Configure Security Group
	Step 7: Review Instance Launch

* 가상서버에 연결하기
  1. Services > EC2 > Instances 이동
  2. Instance 선택 후 "Connect" 클릭
  3. Connect To Your Instance Guide 참고
``` bash
    ssh -i "awskey.pem" ubuntu@ec2-34-229-95-208.compute-1.amazonaws.com
```

* 서버 상태 제어 동작
  - 시작(start) : 중지된 가상 서버를 언제든지 시작 가능. 완전히 새로운 서버를 만들려면 가상 서버를 시작해야 한다.
  - 중지(stop) : 실행중인 가상 서버를 언제든지 중지 가능. 중지된 가상 서버는 비용이 청구되지 않으며 나중에 다시 시작가능. 네트워크 연결 스토리지를 사용하면 데이터는 그대로 남아 있음. 중지된 가상 서버는 네트워크 연결 스토리지 등의 자원을 제외하고는 요금이 부과되지 않음
  - 재부팅(reboot) : 가상 서버를 재부팅하더라도 데이터는 손실되지 않는다. 모든 소프트웨어도 여전히 설치된 상태 그대로 있게 된다.
  - 종료(terminate) : 가상서버의 삭제를 의미. 이미 종료한 가상 서버는 다시 시작할 수 없다. 가상 서버를 삭제하면 네트워크 연결 스토리지, 공용 및 사설 IP주소와 같은 종속성도 함께 삭제됨. 종료된 가성 서버는 요금이 부과되지 않음.
* 가상서버 
  
	