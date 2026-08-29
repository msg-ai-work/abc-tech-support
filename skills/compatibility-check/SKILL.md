---
name: compatibility-check
summary: 발송클라이언트와 OS/JDK/DB 등 고객 실행환경의 지원 가능 여부를 판단한다.
version: "0.1"
---
# Compatibility Check
## 입력
Client 버전, OS/Architecture, JDK, DB/Driver, 연계 방식.
## 절차
1. 지원 Matrix의 공식 지원 조합과 비교한다.
2. EOL/EOS 상태를 확인한다.
3. Driver/JDK bit 및 protocol 호환성을 확인한다.
4. 신규 조합이면 검증 환경과 시험 항목을 정의한다.
5. 미검증 조합은 지원 가능으로 단정하지 않는다.
## 출력
지원/조건부/미검증/미지원과 근거.
