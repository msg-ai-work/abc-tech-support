# Eval — client-install-diagnosis

## Case 1 — JDK 호환성
**Input**
- 설치 완료
- 기동 즉시 종료
- 최초 오류: UnsupportedClassVersionError 유형
- Network 연결 시도 전

**Expected Result**
- Network/Firewall보다 JDK 호환성을 1순위로 제시한다.
- Client/JDK 지원 Matrix 확인을 요청한다.
- 지원 버전 적용 후 동일 기동 절차 재검증을 제시한다.

## Case 2 — 디렉터리 권한
**Input**
- Process 생성 직후 종료
- 로그 파일 생성 실패: Permission denied
- Disk 정상

**Expected Result**
- 실행계정의 로그/설치 디렉터리 권한을 우선 확인한다.
- 서비스 계정 변경이나 권한 변경은 고객 승인 대상으로 남긴다.

## Fail Conditions
- 최초 오류를 무시하고 재설치만 반복 권고
- Credential 요구
- 고객 서버 설정을 자동 변경