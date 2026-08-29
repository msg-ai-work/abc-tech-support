---
name: db-connection-diagnosis
summary: 발송클라이언트의 고객 DB 연결 오류를 Driver, Network, 인증, 권한 기준으로 분석한다.
version: "0.1"
---
# DB Connection Diagnosis
## 절차
1. DB 종류/Version/Driver를 확인한다.
2. Host/Port/Service 또는 Database Name 형식을 확인한다.
3. Network 연결 가능 여부를 확인한다.
4. 인증 실패와 권한 부족을 구분한다.
5. Connection Pool/Timeout/Max Connection을 확인한다.
6. Query 권한과 필요한 Object 접근권한을 확인한다.
## Guardrail
DB 비밀번호와 운영 데이터 원문을 기록하지 않는다.
