### Step 3. Private Endpoint 생성(Hub-VNet)
- 3.1 Storage 계정 생성 후 Blob Storage에 대한 Private Endpoint 생성 및 Hub-VNet과 Private Link 연결
- 3.2 Hub-VNet, Spoke-VNet, Onprem-VNet Private Endpoint에 대한 DNS 조회 확인

1. Storage 계정 생성 및 Container 스토리지 Private Endpoint 생성 Hub-VNet과 Private Link 설정
- 사진 3-1 스토리지 계정 생성
- 사진 3-2 스토리지 계정의 Private Endpoint 
(privatestorageonhub.blob.core.windows.net, 10.0.0.6)


2. Hub-VNet의 VM에서 Private Endpoint 조회 결과 nslookup privatestorageonhub.blob.core.windows.net
-> Hub(조회 O), 그 외 DNS Resolver 생성 전(조회 X)
2-1. Hub-VNet의 VM에서 Private Endpoint 조회 결과 
- 사진 3-3 (dns서버 10.150.0.4 설정) : 조회 안됨 
- 사진 3-4 (dns서버 별도 설정 X) : 조회 됨
2-2. Spoke-VNet의 VM에서 Private Endpoint 조회 결과 
- Hub Spoke 네트워크 통신 설정을 못해 확인 못하였으나, 예상 결과 : 조회 안 됨
- 통신 설정 후 추가 확인 (조회 됨, VNet간 peering 되어 있으면 dns 조회되나 private IP)
2-3. Onprem-VNet의 VM에서 Private Endpoint 조회 결과 -> 조회 안됨
- 사진 3-5
- 사진 3-6 win-client-vm

