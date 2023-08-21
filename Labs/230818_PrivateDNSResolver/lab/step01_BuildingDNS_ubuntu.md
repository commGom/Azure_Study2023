도메인 주소 : i-am-hwpark.site
사설 도메인 주소 : pri.i-am-hwpark.site

1. bind9, dnsutils 패키지 설치
```bash
sudo apt install -y bind9 dnsutils
```

2. 실행 상태 확인
```bash
sudo systemctl status bind9
```

3. cd /etc/bind 데이터베이스가 파일로 되어있다.
```bash
cd /etc/bind
ls

# zones.rfc1918 에 하려면 named.conf.local에서 주석 지워야함. 
sudo vi /etc/bind/named.conf.local
sudo vi zones.rfc1918 
# named.conf 에 도메인 추가 설정 파일(named.conf.default-zones) 위치에 대한 정보가 있음
cat named.conf
sudo vi named.conf.default-zones
```

4. Domain 레코드를 설정할파일 경로 등록 -정방향, 역방향 (오타 주의)
```bash
# 정방향 i-am-hwpark.site 에 대한 도메인 등록 파일 경로 : /etc/bind/db.i.am.hwpark.zone
zone "i-am-hwpark.site" IN { type master; file "/etc/bind/db.i.am.hwpark.zone"; };
# 역방향 10.150.0.0/24 IP에 대한 도메인 등록 파일 경로 : db.i.am.hwpark.rev
zone "0.150.10.in-addr-arpa" { type master; file "/etc/bind/db.i.am.hwpark.rev"; };

```
5. 레코드 등록
```bash
# 정방향 DNS 쿼리, 레코드(NS, A) 등록
sudo cp db.local db.i.am.hwpark.zone 
sudo vi db.i.am.hwpark.zone
# 역방향 DNS 쿼리, 레코드(PTR) 등록
sudo cp db.i.am.hwpark.zone db.i.am.hwpark.rev
sudo vi db.i.am.hwpark.rev
```
- 정방향 DNS 쿼리를 위한 추가한 레코드 (10.150.0.4가 DNS 서버이자, pri.i-am-hwpark.site 웹서버로 매핑)
```bash
;
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     i-am-hwpark.site. admin.i-am-hwpark.site. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      i-am-hwpark.site.
        IN      A       10.150.0.4
pri     IN      A       10.150.0.4
```
- 역방향 DNS 쿼리를 위한 추가한 레코드 (나중에 역방향 다시 확인 필요)
```bash
;
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     i-am-hwpark.site. admin.i-am-hwpark.site. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      i-am-hwpark.site.
        IN      A       10.150.0.4
4       IN      PTR     pri.i-am-hwpark.site.
~                                                     
```
1. 일시적 DNS 서버 주소 변경 (/etc/resolv.conf)

```bash
sudo vi /etc/resolv.conf
# nameserver 127.0.0.1
```

7. hostname 오류 현상 변경

```
sudo vi /etc/hosts

127.0.0.1 호스트이름
# ex) 127.0.0.1 dns-server
```

8. bind9, named 재시작
```bash
sudo systemctl restart bind9
sudo systemctl restart named
# 캐시 삭제(필요시)
sudo systemd-resolve --flush-caches

# DNS 서비스 재시작: 파일을 수정한 후에는 BIND DNS 서비스를 다시 시작해야 합니다. 이는 서비스의 설정 변경을 적용하기 위해 필요합니다.
sudo systemctl restart bind9
# 설정 검증: DNS 서버의 설정 및 파일이 올바르게 로드되었는지 확인하기 위해 named-checkzone 명령을 사용할 수 있습니다.
named-checkzone 0.150.10.in-addr-arpa /etc/bind/db.i.am.hwpark.rev
# 위의 두 가지 주의 사항을 확인하고 적용한 후에는 주어진 리버스 DNS 존 파일이 올바르게 작동할 것으로 기대됩니다.
```

