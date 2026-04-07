# FlutterLoginSample

Flutter로 제작한 심플한 로그인/회원가입 UI 샘플입니다. GetX로 상태를 관리하고 Lottie 애니메이션을 사용해 반응형으로 동작하는 온보딩 화면을 제공합니다.

## 주요 기능
- 회원가입 폼: 사용자명, Gmail, 비밀번호 입력 및 유효성 검사
- 로그인 폼: 사용자명/비밀번호 입력 및 유효성 검사
- 비밀번호 가시성 토글: GetX(`SimpleUIController`)로 즉시 상태 반영
- 반응형 레이아웃: `LayoutBuilder`로 600px 기준 대형/소형 화면 대응
- 애니메이션: `assets/coin.json`, `assets/wave.json` Lottie 애니메이션 표시

## 화면 흐름
- 초기 화면: `SignUpView` (회원가입)
- 로그인 이동: 회원가입 화면 하단의 “Already have an account? Login” 선택 시 `LoginView`로 전환
- 회원가입 이동: 로그인 화면 하단의 “Don’t have an account? Sign up” 선택 시 이전 화면으로 복귀
- 현재 두 버튼(`Sign up`, `Login`)은 폼 검증 후 후속 네비게이션만 추가하면 바로 확장 가능하도록 비워둔 상태입니다.

## 기술 스택
- Flutter, Dart
- 상태관리: GetX (`GetMaterialApp`, `Obx`, `Get.put`, `Get.find`)
- UI/폰트: Material, `google_fonts` (Ubuntu)
- 애니메이션: `lottie`

## 프로젝트 구조
- `lib/main.dart`: 앱 진입점, `GetMaterialApp` 설정 및 초기 화면 지정
- `lib/views/signUp_view.dart`: 회원가입 UI, GetX 컨트롤러 초기화
- `lib/views/login_view.dart`: 로그인 UI, 공유 컨트롤러 사용
- `lib/controller/simple_ui_controller.dart`: 비밀번호 필드 가시성 토글 상태
- `lib/constants.dart`: 공용 텍스트 스타일 정의
- `assets/coin.json`, `assets/wave.json`: Lottie 애니메이션 리소스

## 실행 방법
1) 의존성 설치: `flutter pub get`
2) 실행: `flutter run` (Android/웹)
   - iOS 빌드는 현재 미지원(ios is not available)

## 추후 확장 아이디어
- 실제 인증 로직 및 홈 화면 네비게이션 추가
- 소셜 로그인(Google/Facebook) 연동
- 폼 검증 강화 및 에러 메시지 로컬라이즈

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
