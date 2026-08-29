---
name: network-dns-firewall-port
summary: 고객 환경에서 메시징 연계까지의 DNS, Routing, Firewall, Port 문제를 순서대로 진단한다.
version: "0.1"
---
# Network / DNS / Firewall / Port
## 절차
1. 목적지 Hostname과 DNS 해석 결과를 확인한다.
2. Route/Proxy/NAT 사용 여부를 확인한다.
3. Source → Destination의 허용 Port를 확인한다.
4. TCP Connection 가능 여부와 Timeout 유형을 확인한다.
5. TLS 전 단계 연결과 TLS 오류를 분리한다.
6. 고객 Network와 서비스 측 Network 증적을 시간대로 맞춘다.
## 출력
통신 가능 구간, 차단 추정 구간, 근거, 확인 주체.
