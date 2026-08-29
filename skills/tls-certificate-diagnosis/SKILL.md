---
name: tls-certificate-diagnosis
summary: TLS handshake, 인증서 만료, Trust Chain, Hostname 오류를 진단한다.
version: "0.1"
---
# TLS / Certificate Diagnosis
## 절차
1. 인증서 유효기간을 확인한다.
2. Subject/SAN과 접속 Hostname을 비교한다.
3. Root/Intermediate Trust Chain을 확인한다.
4. 지원 TLS version/Cipher를 비교한다.
5. Client JDK Truststore 차이를 확인한다.
6. Proxy/SSL inspection 여부를 확인한다.
## Guardrail
개인키나 비밀번호를 수집·저장하지 않는다.
