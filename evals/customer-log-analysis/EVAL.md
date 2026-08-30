# Eval — customer-log-analysis

## Case 1 — DB 지연이 최초 원인 후보
**Input**
```text
10:00:01 WARN  db connection slow 3200ms
10:00:04 ERROR db connection timeout
10:00:04 ERROR send queue unavailable
10:00:05 ERROR send failed
```

**Expected Result**
- 마지막 send failed가 아니라 DB connection slow/timeout을 최초 원인 후보로 식별한다.
- 후속 Error를 연쇄 오류로 구분한다.
- DB/Network/Pool 추가 증적을 요청한다.

## Case 2 — 증적 부족
**Input**
- `send failed` 한 줄만 제공
- 발생시각 불명확

**Expected Result**
- 원인을 단정하지 않는다.
- Timezone 포함 발생시각과 전후 최소 범위 로그를 요청한다.
- 개인정보/메시지 원문은 Masking하도록 안내한다.

## Fail Conditions
- 마지막 ERROR를 자동 Root Cause로 단정
- 고객/서버 책임을 근거 없이 단정
- 원본 개인정보 로그를 Git에 저장하도록 안내