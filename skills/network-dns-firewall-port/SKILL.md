---
name: network-dns-firewall-port
summary: 고객 발송클라이언트에서 메시징 서비스까지 DNS, Route, Proxy/NAT, TCP, Firewall/Port 문제를 계층적으로 진단한다.
version: "0.2"
priority: top-3
---
# Network / DNS / Firewall / Port

## 원칙
'접속 안 됨'을 곧바로 Firewall 문제로 단정하지 않는다. `이름해석 → Route → TCP → TLS → Application` 순서로 계층을 분리한다.

## 입력
Source 구간, 목적지 Hostname/Port, 발생시각, Timeout/Refused 등 오류 유형, Proxy/NAT 사용 여부, Network 변경사항.

## 절차
1. Hostname이 기대한 IP로 DNS 해석되는지 확인한다.
2. Source에서 목적지까지 Route/Proxy/NAT 경로를 확인한다.
3. 목적지 Port의 TCP Connection 결과를 확인한다.
4. `timeout`과 `connection refused`를 구분한다.
5. TCP 성공 후 TLS Handshake 실패인지 분리한다.
6. 고객 측/서비스 측 방화벽 증적을 같은 시간대로 맞춘다.
7. 가능 구간과 최초 실패 경계를 표시한다.

## 판단 기준
| 증상 | 우선 후보 |
|---|---|
| DNS 해석 실패/오답 | DNS/Host 설정 |
| TCP Timeout | Route/Firewall/NACL/중간망 |
| Connection Refused | 목적지 Service Listen/Port |
| TCP 성공 + TLS 실패 | 인증서/Protocol/Cipher |
| TLS 성공 + HTTP 오류 | Application/Auth 영역 |

## 대표 Case
> 비식별 대표 사례이며 실제 고객 장애 기록이 아니다.

**현상:** DNS는 정상이며 목적지 IP도 맞다. TCP 연결은 Timeout이고 서비스 측에는 해당 시각의 연결 로그가 없다.

**판단:** Application보다 중간 Network/Firewall 구간을 우선 확인한다. 고객 Source IP, 목적지/Port, 발생시각을 기준으로 양측 Network 증적을 대조한다.

## 출력
정상 확인 구간, 최초 실패 경계, 근거, 고객/서비스/Network 중 다음 확인 주체.

## Human Gate
방화벽 정책 변경이나 운영 Network 설정 변경은 권한 있는 담당자가 승인·수행한다.