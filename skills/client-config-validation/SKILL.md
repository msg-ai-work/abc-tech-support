---
name: client-config-validation
summary: 발송클라이언트 설정파일의 누락, 형식, 상호의존 오류를 사전 점검한다.
version: "0.1"
---
# Client Config Validation
## 절차
1. 필수 Key 존재 여부를 확인한다.
2. 값 형식, 범위, Encoding을 확인한다.
3. 환경별 URL/Port/DB Driver 설정을 확인한다.
4. Timeout/Retry/Thread 등 운영 Parameter를 기준과 비교한다.
5. 서로 종속된 설정의 모순을 확인한다.
6. Password/Secret은 값 자체가 아니라 설정 여부만 확인한다.
## Guardrail
Credential 원문을 출력하거나 Git에 기록하지 않는다.
