# 학생 맞춤형 자세 교정 웹앱 설문

현대중학교 학생의 자세 습관과 신체 불편감을 조사하고, 사진으로 자세를 분석해 맞춤 스트레칭을 알려 주는 웹앱입니다.

- 접속 주소: https://hoonse00000-ux.github.io/posture-correction/
- 응답 저장: Firebase Firestore (프로젝트 `zasegoujung`)
- 자세 분석: Google MediaPipe Pose Landmarker (사진은 서버로 보내지 않고 기기 안에서 분석)

## 구성

| 파일 | 내용 |
|---|---|
| `index.html` | 웹앱 전체 (설문, 자세 분석, 결과, 연구자 페이지) |
| `firestore.rules` | Firestore 보안 규칙 (Firebase 콘솔 > Firestore > 규칙에 붙여 넣기) |

## 사용 방법

1. 참여자: 접속 주소에서 이름(별명)과 동의 → 설문 15문항 → 정면·측면 사진 촬영 → 결과와 추천 스트레칭 확인
2. 연구자: 상단 **연구자** 메뉴에서 등록된 Google 계정으로 로그인 (비밀번호 없음)
   - 응답 결과: 참여자별 점수, 처음/스트레칭 후 비교, 설문과 자세 점수의 관계 그래프, CSV 복사, 응답 삭제
   - 설문 관리: 시작 화면 문구, 설문 문항 추가·수정
   - 판정 기준: 목 각도·좌우 기울기 기준과 감점
   - 설정: 연구자 계정 목록, 로그아웃, AI 연결 확인, 외부 자세 분석 API 연결

## Firebase 설정

- Authentication: **익명**, **Google** 로그인 사용 설정
- Authentication > 설정 > 승인된 도메인: `hoonse00000-ux.github.io` 추가
- Firestore 규칙: `firestore.rules` 전체를 Firestore > 규칙에 붙여 넣고 게시

## 연구자 계정

hoonse00000@gmail.com, sw.almond06@gmail.com, gigayu7@gmail.com, kangminkim121106@gmail.com, binn121015@gmail.com, gksgud4005@gmail.com

연구자를 바꾸려면 `index.html`의 `ADMIN_EMAILS`와 `firestore.rules`의 이메일 목록을 함께 고칩니다.
- 웹 앱 설정은 `index.html` 안의 `FIREBASE_CONFIG`에 들어 있습니다.

## 수정해서 다시 올리기

`index.html`을 고친 뒤 이 저장소에 다시 올리면 1~2분 뒤 접속 주소에 반영됩니다.

이 결과는 의료 진단이 아니라 학생 연구용 자세 균형 지표입니다.
