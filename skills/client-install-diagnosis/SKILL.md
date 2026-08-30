---
name: client-install-diagnosis
summary: 발송클라이언트 설치·기동 실패를 패키지, 호환성, 권한, 설정, 런타임 단계로 분리해 진단한다.
version: "0.2"
priority: top-3
---
# Client Install Diagnosis

## 입력
Client 버전, OS/Architecture, JDK, DB, 실행 계정, 설치 경로, 비민감 오류 로그, 최근 환경변경.

## 절차
1. 설치 패키지 버전/무결성과 설치 대상 버전을 확인한다.
2. OS/JDK/Architecture/DB가 지원 Matrix에 포함되는지 확인한다.
3. 실행 계정의 설치/로그/임시 디렉터리 권한과 Disk 여유를 확인한다.
4. 설정파일 존재, 필수값, 경로, Encoding을 확인한다.
5. 기동 명령과 Process 생성 여부를 확인한다.
6. 기동 로그의 **최초 ERROR**를 찾는다.
7. 설치 실패, 기동 실패, 기동 후 Network/DB 연계 실패를 분리한다.

## 대표 Case
> 비식별 대표 사례이며 실제 고객 장애 기록이 아니다.

**현상:** 설치는 완료되지만 Service 기동 즉시 종료된다. 로그 최초 오류는 `UnsupportedClassVersionError` 유형이고 Network 연결 시도 전이다.

**판단:** Firewall이나 서버 장애가 아니라 JDK 호환성 문제를 1순위로 본다. 지원 JDK Matrix를 확인하고 고객에게 지원 버전 적용 후 동일 기동 절차로 재확인을 요청한다.

## 출력
- 실패 단계
- 확인 환경 Matrix
- 최초 오류와 근거
- 고객 조치사항
- 재확인 명령/절차

## Human Gate
고객 서버의 패키지 제거, JDK 교체, 서비스 계정/권한 변경은 고객 승인 후 수행한다.

## Privacy
계정 비밀번호, DB Credential, 인증서 Private Key는 수집하거나 Git에 기록하지 않는다.