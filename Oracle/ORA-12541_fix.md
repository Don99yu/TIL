# [Oracle] ORA-12541: TNS:no listener 에러 해결

## 1. 발생 현상
- Oracle XE 설치 후 SQL Developer로 접속 시도 시 ORA-12541 에러 발생
- cmd에서 'lsnrctl status' 확인 시 정상 작동 중이었음

## 2. 원인 분석
- 'lsnrctl status'를 자세히 보니 호스트가 'localhost'가 아닌 특정 IP로 잡혀있음
- SQL Developer는 'localhost'로 요청을 보내서 서로 주소가 엇갈림

## 3. 해결 방법
- SQL Developer 접속 설정에서 호스트 이름을 cmd에서 확인한 실제 IP로 변경
- 테스트 후 접속 성공

## 4. 참고 명령어
- 리스너 상태 확인: 'lsnrctl status'
- 윈도우 서비스 학인: 'service.msc'
