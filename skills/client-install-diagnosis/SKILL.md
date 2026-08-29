---
name: client-install-diagnosis
summary: 발송클라이언트 설치·기동 실패를 환경, 권한, 파일, 설정 기준으로 진단한다.
version: "0.1"
---
# Client Install Diagnosis
## 절차
1. Client 버전과 설치 패키지 무결성을 확인한다.
2. OS/JDK/Architecture와 지원 Matrix를 비교한다.
3. 실행 계정 권한, 디렉터리 권한, Disk를 확인한다.
4. 설정파일 존재와 필수값을 확인한다.
5. 기동 로그의 최초 오류를 확인한다.
6. 설치 실패와 기동 후 연계 실패를 분리한다.
## 출력
실패 단계, 근거, 필요한 고객 조치, 재확인 방법.
