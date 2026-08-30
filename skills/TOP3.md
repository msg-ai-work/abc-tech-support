# Technical Support 우선 적용 Top 3

고객사 현장에서 반복되는 설치·통신·로그 분석을 우선 자동화/보조한다.

| 순위 | Skill | 선정 이유 | 1차 성공지표 |
|---:|---|---|---|
| 1 | `client-install-diagnosis` | 설치/기동 초기 문의의 반복성이 높고 진단 순서 표준화 효과가 큼 | 설치/기동/연계 실패 단계 정확히 분리 |
| 2 | `network-dns-firewall-port` | '접속 안 됨' 문제를 Network 계층별로 객관화 가능 | DNS→TCP→TLS→App 최초 실패 경계 제시 |
| 3 | `customer-log-analysis` | 숙련자 경험 의존도가 높은 최초 오류/연쇄 오류 판별 | 최초 이상 시각과 근본 원인 후보 분리 |

## 적용 원칙
- 고객 식별정보와 Credential은 Masking된 자료만 사용한다.
- 고객 환경의 변경 명령은 AI가 자동 실행하지 않는다.
- 지원 완료 후 반복 가능한 진단 절차는 Skill/Eval로 환류한다.
- Top 3의 `SKILL.md`와 `EVAL.md` 구조는 `domain-eval-structure` GitHub Actions Check로 검증한다.
