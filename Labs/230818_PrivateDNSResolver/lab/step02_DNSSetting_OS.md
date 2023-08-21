- 2.1 DNS 설정 방법

  - OS(Linux)단에서 설정
- 2.2 모든 서버 (Hub-VNet, Spoke-VNet, Onprem-VNet) Step1에서 구축한 private DNS 서버로 DNS 서버 설정 

1. VM 생성, VNet Peering (Hub, Spoke, Onprem)
    - mgmt-vm(Hub-VNet) : Private Endpoint nslookup dns 쿼리 조회 
    - web-server(Spoke-VNet) : 웹서버 생성
    - win-client-vm(Onprem-VNet) : 온프렘환경 Private Resolver 적용 확인, 웹서버 접속 확인
2. Hub-VNet에 Container Storage Private Endpoint Link
3. Private DNS Resolver 생성, Hub-VNet에 Inbound Endpoint 및 Outbound Endpoint, 규칙 설정