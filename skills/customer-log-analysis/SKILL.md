---
name: customer-log-analysis
summary: 고객사에서 수집한 발송클라이언트 로그의 최초 오류와 근본 원인 후보를 분석한다.
version: "0.1"
---
# Customer Log Analysis
## 절차
1. 분석 시간 범위와 증상 발생 시각을 맞춘다.
2. INFO/WARN/ERROR를 시간순으로 정렬한다.
3. 최초 ERROR와 그 이전 이상 징후를 찾는다.
4. 반복되는 연쇄 오류는 원인과 분리한다.
5. 설정/Network/DB/TLS/서버 응답으로 분류한다.
6. 추가 로그가 필요하면 최소 범위를 명시한다.
## Privacy
전화번호, 메시지 원문, Credential은 Masking된 자료만 사용한다.
