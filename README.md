# Enterprise Messaging Technical Support AI Harness

`abc-tech-support`는 AX채널개발팀 기업메시징의 **Technical Support Domain AI Harness** 저장소입니다.

## 역할

고객사 발송클라이언트의 설치·설정·연동·장애 대응 지식을 Domain Skill로 관리합니다.

## Common Harness

공통 Agent / Workflow / Rule / Guardrail은 `msg-ai-work/abc`를 SSOT로 사용합니다.
이 저장소는 공통 Harness를 복사해서 독립 관리하지 않습니다.

## 주요 영역

- 발송 Client 설치 / 설정
- OS / JDK / DB 호환성
- Network / DNS / Firewall / Port
- TLS / 인증
- 발송 요청 / 응답
- 고객 로그 수집 / 분석
- 장애 원인 분석
- 고객 기술지원 답변

## 운영 원칙

> 팀장은 AI가 일하는 방법을 관리하고, Domain 담당자는 AI가 알아야 할 업무를 관리합니다.

Skill 변경은 Branch → Pull Request → Review → main Merge 순서로 관리합니다.
