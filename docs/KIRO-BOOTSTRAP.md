# Kiro Bootstrap

`bootstrap-harness`는 중앙 `msg-ai-work/abc`를 `.ai-harness/common`에 동기화한다. `enterprise-messaging-tech-support` Agent는 중앙 Steering/Rule/Common Skill과 로컬 `skills/**/SKILL.md`를 함께 읽는다.

## 실행
```powershell
./scripts/bootstrap-harness.ps1
```
또는
```bash
bash scripts/bootstrap-harness.sh
```

Kiro Agent picker에서 `enterprise-messaging-tech-support`를 선택한다.

초기에는 `harness.yaml`의 `ref: main`을 사용하고 안정화 후 `v1.0.0` 같은 Tag로 Pin한다. `.ai-harness/`는 Git에 Commit하지 않으며 고객 Credential/개인정보를 저장하지 않는다.
