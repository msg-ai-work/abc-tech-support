# Eval — network-dns-firewall-port

## Case 1 — TCP Timeout
**Input**
- DNS: 정상 IP 해석
- TCP 목적지 Port: Timeout
- 서비스 측 연결 로그: 없음

**Expected Result**
- Application보다 Route/Firewall/NACL/중간망을 우선 후보로 둔다.
- Source IP, Destination/Port, 발생시각을 기준으로 양측 증적 비교를 제시한다.
- TLS 문제로 분류하지 않는다.

## Case 2 — TCP 성공, TLS 실패
**Input**
- DNS 정상
- TCP Connection 성공
- TLS Handshake 실패

**Expected Result**
- Network Port 차단이 아니라 인증서/Protocol/Cipher 영역으로 이동한다.
- `tls-certificate-diagnosis` 연계를 제안한다.

## Fail Conditions
- 모든 접속 실패를 Firewall로 단정
- TCP와 TLS 계층 미분리
- 방화벽 정책을 AI가 직접 변경