---
name: customer-log-analysis
summary: 고객 발송클라이언트 로그에서 최초 오류와 연쇄 오류를 분리하고 근본 원인 후보와 추가 증적을 제시한다.
version: "0.2"
priority: top-3
---
# Customer Log Analysis

## 입력 준비
- 증상 발생시각과 Timezone
- Client 버전/환경
- 증상 전후 최소 필요 시간대 로그
- 전화번호/메시지/계정/Token 등 Masking 여부

## 절차
1. 고객이 말한 증상 시각과 로그 Timezone을 맞춘다.
2. INFO/WARN/ERROR를 시간순으로 정렬한다.
3. 대량 반복 ERROR보다 **가장 먼저 발생한 비정상 이벤트**를 찾는다.
4. 최초 오류 이전의 Connection/Retry/GC/DB/Network 징후를 확인한다.
5. 이후 반복 Error를 원인과 연쇄 결과로 구분한다.
6. Configuration / Network / DB / TLS / Server Response / Resource로 분류한다.
7. 근거가 부족하면 필요한 추가 로그의 파일·시간대·항목을 최소 범위로 요청한다.

## 대표 Case
> 비식별 대표 사례이며 실제 고객 로그가 아니다.

```text
10:00:01 WARN  db connection slow 3200ms
10:00:04 ERROR db connection timeout
10:00:04 ERROR send queue unavailable
10:00:05 ERROR send failed
```

**판단:** 마지막 `send failed`를 근본 원인으로 보지 않는다. 최초 징후인 DB Connection 지연과 Timeout을 우선 원인 후보로 두고 DB/Network/Pool 증적을 추가 확인한다.

## 출력
- 최초 이상 시각
- Root-cause 후보 / 연쇄 오류
- 근거 로그(민감정보 제거)
- 추가 확인 자료
- 고객 안내용 요약

## Privacy
원본 로그를 Git에 올리지 않는다. 전화번호, 메시지 원문, Credential, Token, 고객 식별정보는 Masking된 데이터만 사용한다.

## 금지사항
근거가 없는 상태에서 고객 환경 또는 메시징 서버 중 한쪽 책임으로 단정하지 않는다.