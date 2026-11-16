# B3-1 제출 증빙 점검

원문 `미션 3-1.docx`의 최소 제출물은 아래 4종입니다. 모든 클릭을 캡처하는 요구는 없습니다.

## 최종 제출물

- [ ] `docs/architecture.png` 또는 `docs/architecture.pdf`: VPC, Public Subnet, Internet Gateway, EC2, Security Group 및 외부에서 서비스까지의 흐름
- [ ] 외부 접속 결과 스크린샷 1장 이상: 브라우저 `http://<퍼블릭IP>` 또는 `GET /health`; 선택한 방식과 URL/IP를 `README.md`에 기록
- [ ] `docs/troubleshooting.md`: 실제 오류 1건의 증상, 가설, 검증, 조치, 결과, 재발 방지
- [ ] `docs/cleanup-checklist.md`: 실습 자원 종료·삭제 확인과 근거; Billing 캡처는 선택

## 구성 확인용 화면

아래는 필수 기능을 검증할 때 남길 화면입니다. 캡처에 계정 번호, 개인정보, 비밀키가 보이면 가린 뒤 `docs/screenshots/`에 저장합니다. 현재 대화에 올린 캡처는 이 폴더에 자동 저장되지 않았습니다.

- [ ] 새 VPC 상세: 이름, CIDR, 서울 리전
- [ ] Public Subnet 상세: VPC 연결, CIDR, 퍼블릭 IP 설정
- [ ] Internet Gateway 상세: 새 VPC에 Attached
- [ ] Public Subnet Route Table: `0.0.0.0/0 → Internet Gateway`와 서브넷 연결
- [ ] Security Group 인바운드: HTTP 80 전체, SSH 22 내 IP만
- [ ] IAM 사용자 또는 Role: 실습 범위 권한, `AdministratorAccess` 없음
- [ ] EC2: 새 서브넷 배치, 퍼블릭 IP, 실행 상태
- [ ] SSH 접속 및 웹 서버 실행, `curl http://localhost`의 200 응답
- [ ] EC2 아웃바운드 통신 결과
- [ ] 외부 접속 성공 화면

## 현재 확인 상태

- VPC `b3-1-vpc`와 서브넷 `b3-1-public-subnet`은 AWS 화면에서 생성 확인됨. 제출용 로컬 캡처 파일은 아직 없음.
- 현재 콘솔 로그인 주체를 확인해야 함. 원문은 실습용 IAM 사용자 또는 Role로 콘솔에 접근하고 루트 계정으로 실습하지 않도록 요구함.
- Internet Gateway는 생성 전 단계. 로그인 주체 확인 전에는 추가 리소스를 생성하지 않음.
