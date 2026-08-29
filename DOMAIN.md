# Domain Definition — Technical Support

## Mission
고객사 발송클라이언트의 설치·설정·연동·장애 대응 지식을 AI가 반복 활용할 수 있는 Skill로 자산화합니다.

## In Scope
- 발송 Client 설치 / 설정
- OS / JDK / DB 호환성
- Network / DNS / Firewall / Port
- TLS / 인증
- 발송 요청 / 응답 분석
- 고객 로그 수집 / 분석
- 장애 원인 분석
- 고객 기술지원 답변

## Out of Scope
- 공통 Agent / Workflow / Rule 변경 → `msg-ai-work/abc`
- Engine 업무 → `abc-engine`
- Web 업무 → `abc-web`
- 프로젝트 한정 지식 → `abc-projects`
- Secret / Credential / 개인정보 원문

## Definition of Done
- 목적과 사용 조건이 명확함
- 입력 / 절차 / 판단 기준이 있음
- Guardrail이 있음
- 최소 1개 실제 또는 Masking된 검증 Case가 있음
- PR Review 완료
