## Security > NHN AppGuard > 릴리스 노트

| Platform | Version  | Release Date | Status |
| -------- | -------- | -----------  | ------ |
| Android  | 1.12.4.8 | 2025. 06. 24.  | latest |
| Android  | 1.12.2.12 | 2024. 12. 03.  | stable |
| iOS      | 1.4.11     | 2025. 06. 24.  | latest |

### 2025. 06. 24.
* [Android] 1.12.4.8
    * 최소 지원 버전 상향(API 19 -> API 21)
    * synchronized 키워드를 포함한 메서드에 대한 제어 흐름 난독화 시 발생하는 문제 수정
    * React Native 0.76.0 이상 버전 지원
* [iOS] 1.4.11
  * React Native Expo 호환성 개선
      * 최초 설치 시 Expo앱이 종료되는 문제를 수정하였습니다.
* [Console]
    * SDK 다운로드 모달 개선
        * Unreal Engine SDK 다운로드 추가
        * 열 기반 그리드 뷰에서 목록 뷰로 UI 개선
* [Unity] 0.4.19
    * (iOS) iOS SDK 1.4.11 업데이트
* [Unreal] 0.1.0
    * NHN AppGuard Unreal SDK 출시

### 2025. 05. 27.
* [Android] 1.12.4.7
    * 가상 환경(클론앱) 탐지 기능 추가
        * 다음과 같은 클론앱 환경을 탐지할 수 있도록 기능을 확장하였습니다:
            * Multi App(Code: 1306)
            * Parallel Space(Code: 1307)
            * DualSpace(Code: 1308)
            * Clone App(Code: 1309)
            * 2 Account(Code: 1310)
            * Dual App(Code: 1311)
            * DualSpace Lite(Code: 1312)
            * DualSpace Pro(Code: 1313)
    * 직장 프로필 탐지 기능 추가(Code: 2301)
        * 콘솔 > NHN AppGuard > 정책 > Android > 직장 프로필 정책 설정을 통해 해당 기능을 활성화할 수 있습니다.
    * 탐지 코드 설정 오류 수정
        * 조건 기반 탐지 시, 탐지 코드가 “00”으로 잘못 설정되던 문제를 수정하였습니다.
    * 탐지 콜백 로직 개선
        * 동일한 탐지 이벤트에 대해 콜백이 중복 호출되지 않도록 처리 로직을 개선하였습니다.
        * Business 플랜 적용 시, Application.onCreate()에서 콜백이 정상 등록되지 않던 문제를 해결하였습니다.
    * User ID 설정 시 재탐지되지 않는 문제 수정
        * User ID 설정 시, 일부 탐지 로직에서 재탐지가 정상적으로 수행되지 않던 문제를 수정하였습니다.
    * 매크로툴 탐지 기능 개선

### 2025. 05. 15.
* [iOS] 1.4.10
    * 후킹 탐지 오탐 수정
        * 디버그 빌드에서 `ENABLE_DEBUG_DYLIB` 설정 여부에 따라 후킹 탐지가 오탐되는 문제를 수정하였습니다.
* [Unity] 0.4.18
    * (iOS) iOS SDK 1.4.10 업데이트
    

### 2025. 04. 29.
* [Android] 1.12.4.6
    * (React Native) Expo Updates 적용 시 앱이 비정상적으로 종료되는 문제 수정
    * 여러 앱을 병렬로 보호할 경우 간헐적으로 문자열 난독화 테이블이 손상되는 문제 수정
    * 문자열 난독화 테이블이 중복 생성되는 문제 수정
    * User ID를 null로 설정할 경우 앱이 비정상적으로 종료되는 문제 수정
    * Callback 메서드를 null로 설정할 경우 앱이 비정상적으로 종료되는 문제 수정

### 2025. 04. 21.
* [iOS] 1.4.9
    * 엔진 보안성 강화
        * 엔진 보호 기능이 강화되었습니다.
* [Unity] 0.4.17
    * (iOS) iOS SDK 1.4.9 업데이트
    
### 2025. 03. 25.
* [Android] 1.12.4.5
    * 구글 자동 보호(Google Automatic Protection) 적용 시 classes.dex 오탐이 발생하는 문제 수정
    * 레거시 테마(@android:style/Theme.Holo.Light 등) 사용 시 종료 팝업의 상단이 비는 문제 수정

### 2025. 03. 11.
* [Android] 1.12.4.4
    * 비정상적으로 종료되는 오류 수정

### 2025. 03. 07.
* [Android] 1.12.4.3
    * 심플 팝업 적용 시 보호 작업에 실패하는 오류 수정

### 2025. 03. 04.
* [Android] 1.12.4.2
    * Unity 최신 버전(6000.0.38f1)에서 보호 작업에 실패하는 문제 수정
* [iOS] 1.4.8
    * 안정성 개선
* [Unity] 0.4.16
    * (iOS) NHN AppGuard iOS 초기화 안정성 개선
* [Gradle Plugin] 1.2.5
    * 보호 작업 중 오류 처리 개선

### 2025. 02. 12.
* [iOS] 1.4.7
    * 엔진 안정성 향상
* [Unity] 0.4.15
    * 네이티브 팝업 활성화 여부 옵션 추가
    * (iOS) 콜백 안정성 개선
    * (iOS) iOS SDK 1.4.7 업데이트

### 2025. 02. 11.
* [Android] 1.12.4.1
    * Dex 암호화 버그 수정

### 2025. 02. 06.
* [iOS] 1.4.6
    * 특정 상황에서 CPU 사용률이 높아지는 문제 수정
* [Unity] 0.4.14
    * (iOS) iOS SDK 1.4.6 업데이트

### 2025. 02. 03.
* [Gradle Plugin] 1.2.4
    * Gradle 빌드 시 로그 수준을 `QUIET(-q | --quiet)`으로 설정하면 NHN AppGuard 로그가 출력되지 않도록 수정

### 2025. 01. 21.
* [Android] 1.12.4.0
    * VPN 탐지 기능 추가
        * 콘솔 > NHN AppGuard > 정책 > Android > VPN 정책 설정을 통해 적용이 가능합니다.
    * NHN AppGuard 시작 메시지 추가
        * 앱 실행 시 NHN AppGuard 활성화 여부를 알리는 메시지가 표시됩니다.
        * CLI에서 `--show-startup-message`를 추가하여 활성화할 수 있습니다.
    * '--google-pairip' 옵션 사용 중단
        * '--google-pairip' 옵션이 더 이상 필요하지 않으며, 해당 기능은 옵션 없이도 자동 활성화됩니다.
* [iOS] 1.4.5
    * VPN 탐지 기능 추가
        * 콘솔 > NHN AppGuard > 정책 > iOS > VPN 정책 설정을 통해 적용이 가능합니다.
    * NHN AppGuard 시작 메시지 추가
        * CLI에서 `--show-startup-message`를 추가하여 활성화할 수 있습니다.
* [Unity] 0.4.13
    * (iOS) AppGuard iOS Settings > ExtraOptions 추가
    * (iOS) iOS SDK 1.4.5 업데이트
* [Console]
    * 블랙리스트의 검색 조건 추가(시작 일자, 만료 일자, 차단 사유)
    * 블랙리스트 조회 페이지 크기 조정 기능 추가
    * 조회한 블랙리스트에 대해 엑셀 다운로드 기능 추가
    * 조회한 블랙리스트에 대해 일괄 재등록, 일괄 해제 기능 추가
    * 블랙리스트 일괄 등록 기능 추가

### 2025. 01. 16.
* [Gradle Plugin] 1.2.3
    * overrideOutputFile 옵션이 정상적으로 동작하지 않는 문제 수정

### 2025. 01. 06.
* [Android] 1.12.3.2
    * 난독화 예외 처리 방식 개선

### 2024. 12. 24.
* [Android] 1.12.3.1
    * 난독화 예외 처리 방식 개선

### 2024. 12. 03.
* [Android] 1.12.3.0
    * 매크로툴 탐지 개선
        * 매크로툴(Code: 1700) 탐지 개선
    * Dex 암호화 개선
* [Android] 1.12.2.12
    * 난독화 문제 수정
* [iOS] 1.4.4
  * 매크로툴 탐지 기능 추가
    * iOS의 스위치 제어 기능을 통한 매크로 행위를 탐지/차단합니다.
* [Unity] 0.4.12
    * (iOS) iOS SDK 1.4.4 업데이트

### 2024. 11. 28.
* [Android] 1.12.2.11
    * 난독화 문제 수정

### 2024. 11. 08.
* [Android] 1.12.2.10
    * 난독화 과정에서 발생한 오류로 인해 보호 작업에 실패하는 문제 수정

### 2024. 11. 05.
* [Android] 1.12.2.9
    * 안정성 개선
* [iOS] 1.4.3
    * 화면 캡처, 화면 녹화 탐지 기능 추가
    * 화면 보호 기능을 위한 API 추가
        * SDK API를 통해 백그라운드 스냅숏, 화면 캡처, 화면 녹화의 화면 보호 기능을 활성화할 수 있습니다.
* [Unity] 0.4.11
    * (iOS) iOS SDK 1.4.3 업데이트

### 2024. 10. 30.
* [Android] 1.12.2.8
    * 디버그 모드 앱에서 비정상 종료되는 문제 수정

### 2024. 10. 25.
* [Android] 1.12.2.7
    * 일부 저사양 디바이스에서 비정상 종료되는 문제 수정

### 2024. 10. 15.
* [Android] 1.12.2.6
    * 가상 환경 탐지 패턴 추가
        * Black Box(Code: 1304) 탐지 추가
        * KGO(Code: 1305) 탐지 추가
    * 에뮬레이터 탐지 패턴 추가
        * UgPhone(Code: 212) 탐지 추가
    * 매크로툴 탐지 패턴 추가
        * Auto Clicker - Automatic tap(Code: 1710)
* [Gradle Plugin] 1.2.2
    * Android Gradle Plugin 8.1.0 이상 버전 지원
* [Console]
    * 대시보드의 이상 행위 탐지 현황 테이블에 위치 조작 칼럼 추가
    * (iOS) 대시보드의 이상 행위 탐지 현황 테이블에 블랙리스트 칼럼 추가
    * 로그 조회에서 OS 검색 조건을 iOS로 선택했을 때 블랙리스트 조건이 표시되도록 추가
    * iOS 보호 이력의 AppGuard 버전을 SDK 버전만 표출하도록 수정
    * 로그 조회에서 Gamebase의 device_key로 활용 가능한 ANDROID ID 칼럼 조회 추가

### 2024. 09. 27.
* [Android] 1.12.2.5
    * 구글 자동 무결성 보호(Google Automatic Integrity Protection) 사용 시 유니티 변조(Code: 405) 오탐 문제 수정
    * 어뷰징 앱 탐지(Code: 1600) 오탐 문제 수정

### 2024. 09. 10.
* [Android] 1.12.2.4
    * 앱 로딩 속도 개선
    * android:extractNativeLibraries="false" 설정 시 SDK API가 정상 동작하지 않는 문제 수정
    * 녹스 앱플레이어 Android 5 버전에서 앱이 비정상 종료되는 문제 수정
    * Unity 또는 Unreal의 디버그 모드 앱에서 비정상 종료되는 문제 수정

### 2024. 08. 27.
* [Console]
    * 로그 조회 결과에 디바이스 모델 정보 추가

### 2024. 08. 26.
* [Android] 1.12.2.3
    * 앱 업데이트 시 비정상 종료되는 문제 수정

### 2024. 08. 20.
* [Android] 1.12.2.2
    * Android 14(API 34) 타깃 앱이 일부 저사양 디바이스에서 비정상 종료되는 문제 수정

### 2024. 08. 13.
* [Android] 1.12.2.1
    * 앱 로딩 속도 개선
    * Android 14(API 34) 에뮬레이터 탐지 추가
    * 구글 자동 무결성 보호(Google Automatic Integrity Protection) 옵션 호환성 개선
    * 앱 서명 옵션("--as") 개선
        * 두 개 이상의 서명 정보를 입력하였을 때 KeyStore의 서명 값이 포함되어 있어도 오류가 발생하지 않도록 개선되었습니다.

### 2024. 07. 23.
* [Android] 1.12.2.0
    * 루팅 탐지 기능 강화
* [Console]
    * 알람 설정 실패 문구 세분화
    * 블랙리스트 차단 기준을 변경하여 재등록하는 기능 추가

### 2024. 07. 09.
* [Android] 1.12.1.1 
    * 구글 자동 무결성 보호(Google Automatic Integrity Protection) 옵션 사용 시 NHN AppGuard 변조 오탐 이슈 수정
        * 구글 자동 무결성 보호 옵션: "--google-pairip"
* [Android] 1.12.1.0
    * Android 5.1 이하 버전에서 크래시가 발생하는 문제 수정
    * 일부 탐지 로직이 정상적으로 동작하지 않는 문제 수정
    * Google PAD와 NHN AppGuard Unity SDK 호환성 버그 수정
* [iOS] 1.4.2 
	* (React Native) Codepush를 적용할 때 롤백되는 문제 수정
    * 엔진 안정성 향상
* [Unity] 0.4.10
    * (SecureValue) 성능 및 보안 취약점 개선
    * (SecureValue) 직렬화 및 역직렬화 기능 추가
        * Newtonsoft 및 Photon RPC를 지원합니다.

### 2024. 06. 07.
* [iOS] 1.4.1
    * 엔진 안정성 개선
        * 특정 상황에서 가상 메모리 사용이 증가되는 문제를 개선하였습니다.
* [Unity] 0.4.9
    * (iOS) iOS SDK 1.4.1 업데이트

### 2024. 06. 05.
* [Android] 1.12.0.1
    * NHN AppGuard 보안 강화

### 2024. 05. 31.
* [Android] 1.12.0.0
    * 위치 조작 탐지 기능 추가
        * 콘솔 > NHN AppGuard > 정책 > Android > 위치 조작 정책 설정을 통해 적용이 가능합니다.
    * Google PAD와 NHN AppGuard Unity SDK 간 호환성 이슈 수정
* [Android] 1.11.1.1
    * 앱 실행 시 간헐적 비정상 종료 이슈 수정
* [iOS] 1.4.0
    * 위치 조작 탐지 기능 추가
        * 콘솔 > NHN AppGuard > 정책 > iOS > 위치 조작 정책 설정을 통해 적용이 가능합니다.
        * iOS 15 이상에서 탐지 가능합니다.
* [Unity] 0.4.8
    * (iOS) iOS SDK 1.4.0 업데이트

### 2024. 05. 14.
* [Console]
  * 설정 탭 추가
  * 탐지/차단 알람 설정 기능 추가

### 2024. 04. 18.
* [iOS] 1.3.20
    * 초기화 호출 시점에 따라 발생할 수 있는 엔진 오동작 이슈 수정
* [Unity] 0.4.7
    * (iOS) iOS SDK 1.3.20 업데이트
    
### 2024. 04. 16.
* [Android] 1.11.1.0
    * Flutter 앱 보호 지원
        * CLI로 보호 작업 시 `--flutter` 옵션을 추가해야 합니다.
    * LDPlayer 탐지 개선
    * NHN AppGuard 보안 강화
* [iOS] 1.3.19
    * Flutter 앱 보호 지원
        * CLI로 보호 작업 시 `--flutter` 옵션을 추가해야 합니다.
* [Unity] 0.4.6
    * Device ID 획득 API 추가
    * (iOS) iOS SDK 1.3.19 업데이트
* [Flutter] 0.1.0
    * NHN AppGuard Flutter SDK 출시
* [Console] 
    * 정책 탭 개별 차단 기능 추가
    * 보호 탭 SDK 다운로드 내 Flutter SDK 다운로드 추가

### 2024. 04. 03.
* [Android] 1.11.0.1
    * Android 10 디바이스에서 비정상 종료 이슈 수정

### 2024. 04. 02.
* [Andorid] 1.11.0.0
    * React Native 앱 보호 기능 추가
        * CLI로 보호 작업 시 `--react-native` 옵션을 추가해야 합니다.
    * 안티 디버깅 기능 강화
* [iOS] 1.3.18
    * React Native 앱 보호 지원
* [Unity] 0.4.5
    * (iOS) NHN AppGuard iOS 라이브러리를 xcode 프로젝트에 추가 시 상대 경로에 추가될 수 있도록 개선
    * (iOS) iOS SDK 1.3.18 업데이트
* [React Native] 0.1.0
    * NHN AppGuard React Native SDK 출시

### 2024. 03. 12.
* [Android] 1.10.6.0
    * 중요 라이브러리(.so) 보호 기능 추가
        * Unity, Unreal 등의 게임 엔진 외 중요 라이브러리(.so)를 보호할 수 있는 기능이 추가되었습니다.
    * HUAWEI AppGallery 지원
        * CLI 보호 작업 시 "--huawei" 옵션을 사용해야 합니다.
    * NHN Android AppGuard SDK 연동 후 보호 작업 없이 정상 실행되도록 개선
    * 탐지 팝업 화면이 깨지는 이슈 수정
    * 커스텀 팝업 설정 후 탐지 팝업이 나타나는 이슈 수정
    * Device ID 획득 API 추가
        * 콘솔 > NHN AppGuard Android SDK 다운로드 화면에서 .aar 파일을 업데이트해야 합니다.
* [iOS] 1.3.17
    * 탐지 시간 단축
    * Modulemap 추가
* [Unity] 0.4.4
    * (iOS) iOS SDK 1.3.17 업데이트

### 2024. 02. 23.
* [Android] 1.10.5.5
    * 악성 행위 탐지 팝업 디자인 개선
    * 보안성 개선
    * 매크로툴 탐지 패턴 추가
        * Auto Click - Automatic Clicker(Code: 1708) 탐지 추가
        * Auto Tapper: Auto Clicker(Code: 1709) 탐지 추가
    * 원격제어 탐지 패턴 추가
        * TeamViewer Host(Code: 1401) 탐지 개선
        * AnyDesk(Code: 1403) 탐지 추가
    * DEX 암호화 적용 시 용량이 크게 증가하는 문제 수정
* [iOS] 1.3.16
    * [Unity] iOS 15 환경에서 앱 실행 시 비정상 종료 이슈 수정
* [Unity] 0.4.3
    * (iOS) 탐지 알림창이 나타나지 않는 이슈 수정
    * (iOS) iOS SDK 1.3.16 업데이트

### 2024. 02. 16.
* [Unity] 0.4.2
    * (iOS) NHN AppGuard iOS 빌드 이슈 수정
        * Package Manager 사용 시 iOS 빌드가 실패하는 이슈를 수정하였습니다.
    * (iOS) iOS SDK 1.3.15 업데이트

### 2024. 02. 15.
* [iOS] 1.3.15
    * iOS 최소 지원버전 상향(iOS 11 이상)
    * i386, armv7s, armv7 아키텍쳐 지원 종료
    * 기본 탐지 알림창 개선
    * 개인정보 보호 매니페스트 추가
    * 서명 추가 (NHN Cloud Corp.)
    
### 2024. 01. 23.
* [Android] 1.10.5.3
    * 난독화 기능 개선
        * 함수 호출 숨김(Hide Call) 기능을 개선합니다.

### 2024. 01. 09.
* [Android] 1.10.5.2
    * DEX 암ㆍ복호화 개선
    * MEmu 에뮬레이터 탐지 개선
        * MEmu 9.0.9 버전에서도 탐지되도록 개선했습니다.
    * LDPlayer9 에뮬레이터 탐지 개선
        * LDPlayer9 9.0.63 버전에서도 탐지되도록 개선했습니다.
    * 구글 자동 무결성 보호(Google Automatic Integrity Protection) 지원 옵션 추가
        * 구글 자동 무결성 보호 사용 시 "--google-pairip" 옵션을 사용해야 합니다.
* [iOS] 1.3.14
    * 엔진 안정성 개선
* [Unity] 0.4.1
    * (iOS) iOS SDK 1.3.14 업데이트

### 2023. 12. 28.
* [Android] 1.10.5.1
    * StackOverflowError 이슈 수정

### 2023. 12. 19.
* [Android] 1.10.5.0
    * Android 14 대응
        * Android 14(API 34) 이상을 타기팅하는 앱에서 NHN AppGuard 적용 시 비정상 종료될 수 있는 문제를 수정했습니다.
    * 멀티프로세스 대응
        * 애플리케이션 구성 요소에 android:process 특성이 있을 때 간헐적으로 비정상 종료되는 오류를 수정했습니다.
    * armeabi 아키텍처 오류 수정
        * armeabi 아키텍처만을 사용하는 앱에서 발생하는 비정상 종료 오류를 수정했습니다.
* [iOS] 1.3.13
    * 엔진 보안성 강화
    * AppKey 설정 전 탐지 시 로그가 누락되는 문제 개선
        * AppKey 설정 전 Private API에서 악성행위 탐지 시 로그가 누락되는 문제가 수정되었습니다.
        * 보호 작업 설정 시 적용됩니다.
    * 일부 클래스 심볼 난독화 시 보호 작업에 실패하는 문제 개선
    * CLI 인자 개선
        * `--latestVersion` 인자가 기본으로 적용됩니다.
* [Unity] 0.4.0
    * [iOS] NHN AppGuard iOS 초기화 작업 개선
        * Diresu.D 함수는 더 이상 사용되지 않습니다(deprecated).
    * (iOS) iOS SDK 1.3.13 업데이트
* [Gradle Plugin] 1.2.1
    * 서명 키 비밀번호 설정 오류 수정
        * 스토어 비밀번호와 키 비밀번호가 다를 경우 서명에 실패하는 오류를 수정했습니다.

### 2023. 12. 06.
* [iOS] 1.3.12
    * 엔진 보안성 강화
* [Unity] 0.3.1
    * (iOS) iOS SDK 1.3.12 업데이트

### 2023. 11. 24.
* [Android] 1.10.4.1
    * NHN AppGuard 보안 취약점 개선

### 2023. 11. 21.
* [Android] 1.10.4.0
    * Amazon Appstore 서명 검증 활성화
        * "--amazon" 옵션을 사용하여 앱 보호 시 앱 서명 검증이 활성화됩니다.
        * Amazon Appstore는 "--as" 옵션을 사용하여 Appstore 서명의 SHA-256 Hexadecimal 정보를 설정해야 합니다.
        * Appstore 서명은 Amazon Developer > My apps > Appstore Certificate Hashes에서 확인할 수 있습니다.
    * SecureValue 변조(Code: 409) 탐지 기능 추가
    * DEX 로딩 방식 개선
    * NHN AppGuard 보안 강화
* [iOS] 1.3.11
    * 탈옥 환경 탐지 강화
    * Unreal Engine용 정적 라이브러리 배포 추가
    * Unreal Engine 지원 개선
    * 엔진 보안성 강화
* [Unity] 0.3.0
    * (Android) SecureValue 변조(Code: 409) 탐지 기능 추가
    * (iOS) iOS SDK 1.3.11 업데이트

### 2023. 10. 24.
* [iOS] 1.3.10
    * 난독화 플러그인이 적용된 유니티 앱을 보호할 때 보호 실패하는 이슈 수정
* [Unity] 0.2.2
    * iOS SDK 1.3.10 업데이트

### 2023. 10. 19.
* [Android] 1.10.3.3
    * NHN AppGuard 엔진 보안성 강화
    * MEmu 에뮬레이터 탐지 기능 추가
    * 저사양 디바이스 안전성 개선
    * 파일명에 특정 문자열이 포함될 경우 보호 작업이 실패하는 오류 수정
* [iOS] 1.3.9
    * 유니티 앱 보호 강화
    * User ID 변경 시 탐지 로그를 재전송하도록 개선
    * CLI에서 재서명 실행 시 출력 메시지 개선
    * 안정성 개선
* [Unity] 0.2.1
    * iOS SDK 1.3.9 업데이트

### 2023. 09. 26.
* [Android] 1.10.3.2
    * 서명 변조 오탐 수정
        * 앱 보호 시 사용하는 keystore의 서명을 변조로 판단하는 문제 수정
    * 서명 중복 여부 확인
        * `--as` 옵션과 keystore의 서명이 동일할 경우 오류를 반환하도록 수정
* [Unity] 0.2.0
    * Certificate Fingerprints 비활성화 옵션 추가
* [Gradle Plugin] 1.2.0
    * Certificate Fingerprints 옵션 추가

### 2023. 09. 13.
* [Android] 1.10.3.1
    * 앱 서명 변조 오탐 이슈 수정
* [Unity] 0.1.8
    * iOS SDK 1.3.8 업데이트

### 2023. 09. 12.
* [Android] 1.10.3.0
    * [CLI] 앱 서명(SHA-256) 추가 옵션을 필수 항목으로 변경
        * Google Play, 원스토어 등의 스토어 서명 방식을 사용하는 경우 `--as` 옵션 필수
        * apk 또는 aab에 서명된 정보 외의 서명을 허용하지 않을 경우 `--no-as` 옵션 필수
    * 디바이스 용량 부족으로 앱 실행 불가 시 메시지 노출
    * 구글 자동 무결성 보호(Google Automatic Integrity Protection) 지원
    * 녹스 에뮬레이터 탐지 개선
    * NHN AppGuard 엔진 보안성 강화
    * 식별자 난독화 개선
    * 후킹 탐지 기능 개선
    * Auto Click Assistant(Code: 1707) 탐지 추가
    * 저사양 태블릿 안전성 개선
* [iOS] 1.3.8
    * 앱 복호화 방지 기능 강화
    * 안정성 개선

### 2023. 08. 17.
* [Android] 1.10.2.2
    * 후킹 탐지 기능 강화
    * 엔진 안정성 개선
    * [Unity] Android 4.4(API 19)에서 비정상적으로 종료되는 오류 수정
* [iOS] 1.3.7
    * 엔진 보안성 강화
    * 앱 복호화 방지 기능 강화
    * CLI에 재서명 기능 추가
        * 기존 제공되던 재서명 스크립트는 더 이상 제공되지 않습니다.
* [Unity] 0.1.7
    * iOS SDK 1.3.7 업데이트

### 2023. 07. 21.
* [Android] 1.10.2.1
    * 앱 실행 시 비정상 종료 이슈 수정
    * 난독화 개선
        * 난독화 대상 메서드가 65K를 초과 시 보호 작업에 실패하는 이슈 대응
    * 정책 변조 대응 개선

### 2023. 07. 11.
* [Android] 1.10.2.0
    * 어뷰징 앱 탐지 기능 강화
    * NHN AppGuard 기본 정책 개선
    * 블랙리스트 버그 수정
* [Gradle Plugin] 1.1.2
    * Firebase Crashlytics Gradle 2.8.1 이상에서 mapping.txt 파일이 업로드되지 않는 이슈 수정
* [iOS] 1.3.6
    * 엔진 보안성 강화
    * Info.plist 변조 탐지 개선
    * 앱 복호화 방지 기능 추가
    * 기본 정책 기능 개선
    * f 함수 Deprecated
* [Unity] 0.1.6
    * 안정성 개선
    * iOS SDK 1.3.6 업데이트

### 2023. 07. 06.
* [Android] 1.10.1.2
    * 루팅 탐지 기능 강화
    * 안정성 개선

### 2023. 06. 16.
* [Unity] 0.1.5
    * iOS SDK 1.3.5 업데이트

### 2023. 06. 15.
* [iOS] 1.3.5
    * Info.plist 변조 오탐 개선
* [iOS] 1.3.4
    * 엔진 보안성 강화
* [Unity] 0.1.4
    * iOS SDK 1.3.4 업데이트

### 2023. 06. 13.
* [Android] 1.10.1.0
    * 매크로툴 탐지 개선
    * 아마존 앱스토어 지원
* [iOS] 1.3.3
    * 리소스 변조 탐지 기능 추가(Info.plist 변조 대응)
    * 탐지 콜백 데이터 형식 개선(사용자 가이드 참조)
    * 탐지 코드 형식 개선(사용자 가이드 참조)
    * 재서명 스크립트 실행 시 경로에 공백이 포함된 경우 재서명 실패 버그 수정
    * 엔진 보안성 개선
    * AdSupport.framework 필수 프레임워크 제외
* [Unity] 0.1.3
    * Xcode 라이브러리 의존성 제거
    * AdSupport.framework 필수 프레임워크 제외 반영
    * iOS SDK 1.3.3 업데이트

### 2023. 05. 30.
* [Android] 1.10.0.5
    * 식별자 난독화 오류 수정

* [Gradle Plugin] 1.1.1
    * extraOptions 오류 수정

### 2023. 05. 11.
* [iOS] 1.3.2
    * 엔진 보안성 강화(Unity)

* [Unity] 0.1.2
    * 리눅스 운영체제에서 CLI 보호 작업이 실행될 수 있도록 개선
    * iOS SDK 1.3.2 업데이트

### 2023. 05. 02.
* [Android] 1.10.0.4
    * 권한 변조(400_106_0) 오탐 이슈 수정

### 2023. 04. 25.
* [Android] 1.10.0.3
    * AndroidManifest.xml의 android:debuggable 속성 변조 탐지 추가
    * 라이브러리 패킹 오류 수정
    * 비정상 행위 차단 시 앱 종료 로직 개선
    * [CLI] 보호 작업 실패 처리 개선
    * [CLI] 보호된 앱 다운로드 개선
    * [Unity] il2cpp 암호화 개선
    * [Unity] 게임 메모리 무결성 검증 개선
    * [Cocos2d] Crashlyitcs에서 심볼 분석이 되지 않는 이슈 수정

* [iOS] 1.3.1
    * 엔진 보안성 강화
    * 조건 차단 정책 연동
    * framework의 info.plist 제거

* [Unity] 0.1.1
    * iOS SDK 1.3.1 업데이트

### 2023. 04. 14.
* [Android] 1.10.0.2
    * 32bit 에뮬레이터에서 비정상적으로 종료되는 오류 수정
    * 문자열 난독화 개선

### 2023. 04. 10.
* [Android] 1.10.0.1
    * 문자열 암호화 오류 수정

### 2023. 03. 28.
* [Android] 1.10.0.0
    * 외부 공격 탐지 시 앱 종료 로직 개선
    * 요금 플랜 변경(Business, Enterprise, Game)

* [iOS] 1.3.0
    * 엔진 보안성 강화
    * 요금 플랜 변경(Business, Enterprise, Game)

* [Unity] 0.1.0
    * NHN AppGuard Unity SDK 출시

* [Gradle Plugin] 1.1.0
    * 요금 플랜 옵션 변경(Business, Enterprise, Game)

### 2023. 02. 28.
* [Android] 1.9.13.5
    * 어뷰징 앱 라이선스 탐지 개선
    * 조건 차단 정책이 적용되지 않는 이슈 수정
    * Unity 앱 실행 시 크래시가 발생하는 문제 수정
    * Unity 무결성 검증 오탐 수정(405_49_0)

* [iOS] 1.2.10
    * 엔진 보안성 강화
    * iOS 15 호환성 개선
   
### 2023. 02. 08.
* [Android] 1.9.13.1
    * 덱스 난독화 이슈 수정

### 2023. 01. 31.
* [Android] 1.9.13.0
    * 암호화 API 헤더 변경
    * 앱 번들 이슈 수정
    * 보안 기능 강화
    * x86, x86_64 이슈 수정
    
* [iOS] 1.2.9
    * 기본 정책 기능 추가
    * 엔진 보안성 강화
    * 시뮬레이터 오탐 개선
    * xcframework 지원
    * AppGuard CLI 기능 개선

### 2022. 12. 27.
* [Android] 1.9.12.0
    * 클라이언트 정책 지원 종료
    * 기본 정책 기능 추가
    * 경고창 미발생 이슈

* [iOS] 1.2.8
    * 엔진 보안성 강화
    * iOS 16 호환성 개선

### 2022. 12. 13.
* [Android] 1.9.11.2
    * API 노출 이슈 수정
    * LifecycleCallback 이슈 수정
    * 특정 보호 기능 크래시 및 오탐 이슈 수정
    * x86 크래시 이슈 수정

### 2022. 12. 07.
* [Android] 1.9.11.1
    * 변조 오탐 이슈 수정

### 2022. 11. 29.
* [Android] 1.9.11.0
    * 프레임 드롭 이슈 수정
    * SSL 피닝 우회 미 탐지 이슈 수정
    * Google Play 게임즈 지원
    * 크래시 이슈 수정

* [iOS] 1.2.7
    * API 후킹 탐지 로직 강화
    * 정책 관련 이슈 해결
    * AppGuard CLI 기능 개선

### 2022. 11. 09.

* [Android] 1.9.10.2
    * 백그라운드 크래시 이슈 수정

### 2022. 11. 02.

* [Android] 1.9.10.1
    * 크래시 이슈 수정

### 2022. 10. 28.
* [iOS] 1.2.6
    * 엔진 보안성 강화

### 2022. 10. 25.
* [Android] 1.9.10.0
    * 에뮬레이터 탐지 기능 강화
    * 치팅 툴 탐지 기능 강화

### 2022. 10. 14.
* [Android] 1.9.9.2
    * LDPlayer4 64bit 에뮬레이터 지원
    * 한국어 경고 창 추가
    * 초기화 속도 개선
    * 에뮬레이터 크래시 이슈 수정
    * 엔진 보안성 강화

### 2022. 10. 07.
* [Android] 1.9.9.1
    * 해당 버전 제거

### 2022. 10. 04.
* [Android] 1.9.9.0
    * 해당 버전 제거

* [iOS] 1.2.5
    * 엔진 보안성 강화
    * 네트워크 관련 버그 패치
    * 리패키징 관련 보안성 강화


### 2022. 09. 08.
* [Android] 1.9.8.1
    * 메니페스트 이슈 수정

### 2022. 08. 23.
* [Android] 1.9.8.0
    * 크레마 단말기 지원 
    * 블루스택, 녹스, LDPlayer9 64bit 에뮬레이터 지원
    * SafetyNet 지원 중단
    * 엔진 보안성 강화
    * Unity 보호작업 이슈 수정

* [iOS] 1.2.4
    * 엔진 보안성 강화
    * 트윅 탐지 기능 추가

### 2022. 07. 26.
* [Android] 1.9.7.0
    * 엔진 보안성 강화
    * 메니페스트 버그 수정
    * 미탐 버그 수정

* [iOS] 1.2.3
    * 엔진 보안성 강화
    * Device ID 관련 API 추가

* [Gradle Plugin] 1.0.2
    * CLI 콘솔 로그 출력

### 2022. 07. 06.
* [Android] 1.9.6.1
    * ANR 이슈 수정
    * 엔진 보안성 강화

### 2022. 06. 30.

#### 기능 개선/변경
* [Android] 1.9.6.0
    * 해당 버전 제거

* [iOS] 1.2.2
    * 위변조 탐지 기능 강화
    * Unity 전용 보안 API 추가
    * 엔진 보안성 강화

* [Gradle Plugin] 1.0.1
    * variants별로 보호된 파일 저장 경로를 지정하는 옵션 추가
    * 서명 키 비밀번호, 별칭(alias)에 공백 포함 가능하도록 개선

### 2022. 05. 24.

#### 기능 개선/변경
* [Android] 1.9.5.0
    * 블랙리스트 차단 기능 개선
    * 일부 크래시 이슈 수정
    * 블루스택(BlueStacks) 에뮬레이터 검증 강화
    * 엔진 보안성 강화

* [iOS] 1.2.1
    * NHN AppGuard iOS CLI 추가

* [Console] 탐지 로그 검색 가능 기간 변경(30일 -> 90일)

### 2022. 05. 10.

#### 기능 개선/변경
* [Android] 1.9.4.1
    * ANR 및 크래시 이슈 개선
    * 콜백 데이터 개선
    * 에뮬레이터 탐지 기능 강화
    * 엔진 보안성 강화

### 2022. 04. 26.

#### 기능 개선/변경
* [Android] 1.9.4.0
    * 해당 버전 제거

* [iOS] 1.2.0
    * Unity 프레임워크 관련 보안성 강화
    * 엔진 보안성 강화

* [Gradle Plugin] 1.0.0
    * groupId, 패키지명 변경

### 2022. 03. 29.

#### 기능 개선/변경
* [Android] 1.9.3.0
    * 덱스 암호화 개선
    * 치팅툴 정책의 매크로툴 정책 분리
    * 다수 서명에 대한 검증 기능 추가
    * 모드앱 탐지 개선
    * 언리얼 SDK 개선

* [iOS] 1.1.10
    * 보호작업 버그 패치
    * 재서명 스크립트 기능 개선
    * 버전 확인 관련 기능 개선
    * 가이드문서 수정

* [Gradle Plugin] 0.2.1
    * apk 파일 탐색 로직 개선
    * 프로텍터 버전 정규표현식 개선

### 2022. 02. 22.

#### 기능 개선/변경
* [Android] 1.9.2.0
    * 어뷰징앱 탐지 기능 강화
    * 대용량 앱 보호작업 개선
    * 매크로툴 상세 정보 노출
    * CLI 버그 수정
    * 실시간 정책 탐지 버그 수정
    * 보호작업 실패 이슈 수정

* [iOS] 1.1.9
    * 버전 확인 관련 기능 개선
    * 가이드문서 수정

* [Gradle Plugin] 0.2.0
    * 그래들 buildTypes, productFlavors, variants 별 옵션 지원
    * overrideOutputFile 옵션 추가

### 2022. 01. 25.

#### 기능 개선/변경
* [Android] 1.9.1.0
    * isolated 프로세스 처리 개선
    * 해킹툴 탐지 기능 강화
    * 변조 탐지 기능 강화

* [iOS] 1.1.8
    * 클래스 난독화 신규 기능 추가
    * 블랙리스트 기능 개선

* [Gradle Plugin] 0.1.0
    * NHN AppGuard Gradle Plugin 신규 출시

### 2021. 12. 28.

#### 기능 개선/변경
* [Android] 1.9.0.0
    * NHN AppGuard 버전 지정하여 보호작업하도록 수정
    * 해킹툴 탐지 기능 강화
    * 원격제어 패키지 탐지 기능 개선
    * 특정 에뮬레이터 크래시 이슈 수정

* [iOS] 1.1.7
    * 엔진 보안성 강화

#### 버그 수정
* [iOS] 1.1.7
    * 프로텍터 버그 패치
    * 리사이너 버그 패치

### 2021. 12. 02.

#### 버그 수정
* [Android] 1.8.9.1
    * 경고창 크래시 수정

### 2021. 11. 23.

#### 기능 개선/변경
* [Android] 1.8.9.0
    * 엔진 보안성 강화
    * 새로운 구조의 CLI 배포

#### 기능 개선/변경
* [iOS] 1.1.6
    * 엔진 보안성 강화
    * 프로텍터 기능 개선

### 2021. 11. 04.

#### 버그 수정
* [iOS] 1.1.5
    * 프로텍터 앱네임 추출 관련 버그 수정

### 2021. 10. 26.

#### 기능 개선/변경
* [Android] 1.8.8.0
    * 엔진 보안성 강화
    * 암호화 API 기능 개선

### 2021. 10. 8.

#### 버그 수정
* [Android] 1.8.7.1
    * 구글 Play Asset Delivery 지원기능 오류 수정

### 2021. 9. 28.

#### 기능 개선/변경
* [Android] 1.8.7.0
    * 엔진 보안성 강화
    * Google SafetyNet 악성 앱 탐지 기능 추가

#### 기능 개선/변경
* [iOS] 1.1.4
    * 엔진 보안성 강화
    * AppGuard 프로텍터를 통한 보호 기능 강화

### 2021. 9. 1.

#### 버그 수정
* [Android] 1.8.6.1
    * SQLite를 사용하는 Unity 크래시 수정
    * Unreal 일부 보안 기능 수정

### 2021. 8. 24.

#### 기능 개선/변경
* [Android] 1.8.6.0
    * 엔진 보안성 강화
    * Unreal 보안 기능 개선
    * 보호작업 시간 개선
    * CLI macOS M1 지원
    
### 2021. 7. 27.

#### 기능 개선/변경
* [iOS] 1.1.2
    * 엔진 보안성 강화
    * 프로텍터 업데이트
    
* 웹 콘솔 페이지 변경
    * 앱 보호 작업이 비동기로 변경되었습니다.

### 2021. 7. 13.

#### 기능 개선/변경
* [Android] 1.8.5.1
    * 구글 Play Asset Delivery 적용 앱 지원 기능 개선

### 2021. 6. 29.

#### 기능 개선/변경
* [Android] 1.8.5.0
    * 엔진 보안성 강화
    * Unity 보안 기능 개선
    * CLI 오류 처리 개선
  
* [iOS] 1.1.1
    * 엔진 보안성 강화
    * IAP 어뷰징 탐지 추가
    * 내부 테스트 로직 개선
  
### 2021. 5. 25.

#### 기능 개선/변경
* [iOS] 1.1.0
    * 엔진 성능 개선
    * 엔진 안정화

### 2021. 5. 24.

#### 기능 개선/변경
* [Android] 1.8.4.0
    * 엔진 보안성 강화
    * 엔진 안정화
    * Unity 2020 특정버전 크래시 이슈 개선
     
### 2021. 5. 11.

#### 기능 개선/변경
* [Android] 1.8.3.1
	* 원격제어 탐지기능 추가
	
### 2021. 4. 27.

#### 기능 개선/변경
* 서비스명 변경 (AppGuard -> NHN AppGuard)
* [Android] 1.8.3.0
	* NHN AppGuard 엔진 보안성 강화
* [iOS] 1.0.18
	* 악성행위 탐지 후 핸들링 로직 변경
	* NHN AppGuard 엔진 보안성 강화
	* NHN AppGuard 엔진 안정화
 
### 2021. 4. 12.

#### 버그 수정
* [iOS] 1.0.17
    * NHN AppGuard 후킹 탐지 로직 추가

### 2021. 4. 09.

#### 버그 수정
* [Android] 1.8.2.2
	* Cocos2d 엔진 에뮬레이터 크래시 이슈 개선
	
### 2021. 3. 31.

#### 버그 수정
* [Android] 1.8.2.1
	* 페이스북 SDK 일부기능 충돌 오류 수정
	
### 2021. 3. 23.

#### 기능 개선/변경
* [Android] 1.8.2.0
	* NHN AppGuard 엔진 보안성 강화
* [iOS] 1.0.16
	* NHN AppGuard 엔진 보안성 강화

### 2021. 2. 23.

#### 기능 개선/변경
* [Android] 1.8.1.0
	* CLI 기능 개선
	* NHN AppGuard 엔진 안정화
	* NHN AppGuard 엔진 보안성 강화
	* 가상환경 패턴 추가 (F1VM)
* [iOS] 1.0.15
	* NHN AppGuard 엔진 안정화

### 2021. 1. 26.

#### 기능 개선/변경
* [Android] 1.8.0.1
	* 서드 파티 스토어 지원용 옵션 추가
	* 게임 핵 탐지 기능 강화

### 2020. 12. 29.

#### 버그 수정
* NHN AppGuard 엔진 안정화

### 2020. 08. 25.

#### 기능 개선/변경
* [Android] 가상 환경 탐지 기능 개선
* [iOS] 탈옥 탐지 고도화
* [iOS] 게임 핵 탐지 고도화

### 2020. 07. 28.

#### 기능 개선/변경
* [Android] 가상 환경 탐지 기능 추가
* [iOS] 탈옥 탐지 고도화
* [iOS] 강제 종료 고도화
* [iOS] 블랙리스트 차단 기능 추가

#### 버그 수정
* [Android] Unity Mono 에뮬레이터 7 버전 크래시 이슈 개선
* [iOS] GAMEPOT(게임팟) 프레임워크 충돌 오류 개선

### 2020. 06. 23.

#### 기능 개선/변경
* NHN AppGuard 용량 축소 개선
* NHN AppGuard 엔진 보안성 강화

#### 버그 수정
* Unreal 엔진 보호 버그 수정

### 2020. 05. 26.

#### 기능 개선/변경
* 난독화 신청 기능 추가

#### 버그 수정
* NHN AppGuard 엔진 안정화

### 2020. 04. 28.

#### 기능 개선/변경
* SSL Pinning 공격 탐지 기능 추가

### 2020. 03. 24.

#### 기능 개선/변경
* Android 7.0 버전 에뮬레이터 지원

### 2020. 02. 25.

#### 기능 개선/변경
* 변조앱 대응 로직 추가

### 2020. 01. 21.

#### 기능 개선/변경
* NHN AppGuard 엔진 안정화

### 2019. 12. 24.

#### 기능 개선/변경
* Cocos2d-x 엔진 암호화 모듈 추가

### 2019. 11. 26.

#### 기능 개선/변경
* NHN AppGuard 버전 선택 기능 추가

#### 버그 수정
* 문자열 난독화 버그 수정

### 2019. 10. 29.

#### 기능 개선/변경
* 안티 디버깅 기능 개선
* 게임 핵 탐지 기능 개선
* 메모리 검색 탐지 기능 추가

#### 버그 수정
* NHN AppGuard 엔진 안정화

### 2019. 09. 24.

#### 기능 개선/변경
* NHN AppGuard Android Q 안정성 향상

### 2019. 08. 27.

#### 기능 개선/변경
* Android Q 지원
* 웹 콘솔 조건 차단 및 블랙리스트 기능 추가
* NHN AppGuard iOS 실시간 정책 설정 기능 추가
* 기계 학습 기반 Unity 게임 매크로 탐지 기능 추가 및 웹 콘솔 지원
* NHN AppGuard 모듈 무결성 검증 개선
* 웹 콘솔 감사 로그 기능 추가

### 2019. 07. 23.

#### 기능 개선/변경
* Android App Bundle 지원
* Unity 라이브러리 패킹 기능 추가
* Unity MONO 매크로 탐지 기능 추가

#### 버그 수정
* dex 무결성 검사 버그 수정

### 2019. 06. 25.

#### 기능 개선/변경
* NHN AppGuard 64비트 라이브러리 보호 기능 강화
* NHN AppGuard 제어 흐름 난독화 기능 추가
* 크래시 리포트 기능 추가

#### 버그 수정
* NHN AppGuard 경로 권한 변경 검사 버그 수정

### 2019. 05. 28.

#### 기능 개선/변경
* Google 가이드에 따라 기본으로 64비트 라이브러리 추가하도록 변경
	* 기존 방식: 사용자 ABI를 확인해 32비트 또는 64비트 라이브러리 추가
	* 변경 방식: 32/64 비트 라이브러리 모두 추가
* 매크로 탐지 기능 개선

#### 버그 수정
* [Android] 에뮬레이터 미탐지 버그 수정
* [iOS] 무결성 검사 버그 수정

### 2019.04.23

#### 기능 개선/변경
* Unity IL2CPP 메소드 암호화 기능 추가
	* CLI 옵션 "--il2cpp-encryption"으로 적용
* Unity MONO 메소드 암호화 기능 추가
	* NHN AppGuard level3으로 적용
* 에뮬레이터 탐지 패턴 추가
	* Memu Player 최신 버전(6.1.1)

#### 버그수정
* Android OS 4.X 버전에서 멀티 덱스 중복 설치 오류 수정

### 2019.03.26

#### 기능 개선/변경
* Unity 라이브러리 난독화 적용
* NHN AppGuard 자체 API / Method 난독화 기능 추가

### 2019.02.26

#### 기능 개선/변경
* NHN AppGuard 자체 모듈 난독화 적용
* Unity 최신버전(2018) 호환성 개선
	* MONO, IL2CPP 빌드 암호화 기능
* 에뮬레이터 탐지 패턴 추가
	* NOX 최신 버전(6.2.7.0)

### 2019.01.29

#### 기능 개선/변경
* Unity 최신버전 호환성 개선

### 2018.12.27

#### 기능 개선/변경
* NHN AppGuard 자체 보호 기능 강화
* Dex Loader 난독화 기능 추가
* 후킹 탐지 패턴 추가
* 루팅 탐지 패턴 추가
* 에뮬레이터 탐지 패턴 추가
* Unity IL2CPP 빌드 보호 기능 강화
	* IL2CPP Dumper 툴 방지기능

### 2018.11.27

#### 기능 개선/변경
* Unity il2cpp 빌드 암호화 기능 강화
* 후킹 탐지 기능 강화

### 2018.10.23

#### 기능 개선/변경
* NHN AppGuard 적용 확인 기능 추가
* 루팅 탐지 기능 강화
* 디버깅 탐지 기능 강화

### 2018.08.28

#### 버그수정
* NHN AppGuard Unity SDK
	* Unity 5 이하 버전에서 에디터 연동 버그 수정

### 2018.07.24

#### 기능 개선/변경
* Unreal Engine 4 지원
	* Unreal Engine 4의 게임코드에 대한 보호를 지원

### 2018.06.26

#### 기능 개선/변경
* Android P(9.0) 호환성 개선
* NHN AppGuard Unity SDK
    * UNITY 2018 버전 지원

### 2018.05.29

#### 기능 개선/변경
* 메모리 조작 탐지 강화
    * 치팅 툴을 이용한 메모리 조작에 대한 탐지 기능을 강화
#### 버그 수정
* level 3에 적용된 안티디버깅 기능이 배터리를 과도하게 소모하는 현상 수정

### 2018.04.24

#### 기능 개선/변경
* Unity 엔진 il2cpp 빌드 게임코드 암호화 지원
    * Mono 빌드만 지원했던 게임코드 암호화를 il2cpp 빌드도 지원하도록 확장
* 안티 디버깅(앱 분석 방지 기술) 개선
    * 기능 강화 및 안정성 향상

### 2018.02.20

#### 버그 수정
* 모모 앱 플레이어 1.2.1 버전에서 NHN AppGuard Level2가 적용된 앱이 정상 실행되지 않는 오류 수정

### 2018.01.24

#### 버그 수정
* Android 8.x 특정 단말에서 Unity2017버전으로 개발된 앱에 Level2를 적용할 경우 실행 되지 않는 오류 수정

### 2017.12.21

#### 기능 개선/변경
* Unity 스피드핵 탐지 기능 강화
#### 버그 수정
* Unity Personal 최신버전 (2017.x.x 버전)에서 보호작업시 오류 수정
* 멀티덱스(3개이상)인 앱을 보호했을 때 불필요하게 apk크기가 증가하는 현상 수정

### 2017.08.24

#### 기능 개선/변경
* 유/무료 선택창 제거(9월 1일 적용)
* Android 8.0 지원
#### 버그 수정
* NHN AppGuard CLI(AppGuard.exe)를 자동으로 업데이트 해주는 모듈(CLIUpdater.exe) 수정, 업데이트 필수
* 최신 SDK의 CLI 사용 필요 (자동 업데이트기능을 원하지 않는 경우 CLI 옵션으로 --noUpdate를 추가)

### 2017.07.20

#### 기능 개선/변경
* Level 1~3 적용시 Callback 함수가 탐지시 호출되지 않는 오류 수정
* Level 1~3 적용시 용량최적화 기능 옵션화

### 2017.06.22

#### 기능 개선/변경
* 64bit 아키텍처 x86_64, arm64-v8a 용 jni 사용시 아키텍쳐에 해당되는 NHN AppGuard 모듈이 포함됨
* Android, iOS(Beta) SDK 다운로드 경로 분리
* iOS(Beta) 버전은 무료로 제공
* NHN AppGuard 자체 모듈 변조 탐지 기능 강화
* Unity3D DLL 파일 암호화 대상 확장
* Unity 기본 DLL 파일 및 추가적인 DLL 파일 암호화 (Level3)

### 2017.05.25

#### 기능 개선/변경
* Android 버전 적용 방식 단순화
* 기존 : SDK 연동 후 보호작업
* 변경 : 보호작업 만으로 적용 가능 (유저 ID 식별자 등록 필요시 선택적으로 SDK 연동이 필요하나 기존보다 간단함)
* 앱 보호 레벨 개편
* Level 1 : 앱에 대한 비정상 행위 및 패턴 기반의 기본 보안 탐지 기능
* Level 2 : Level1 + 코드 암호화, 앱 변조 방지 등 향상된 보안 기능
* Level 3 : Level2 + 강화된 보안 기능 (특정 서비스에서는 안정성 검증이 필요할 수 있어, 별도 적용 가이드를 받은 경우에만 사용 권장)
* Level ex : SDK 연동이 필수로 필요한 버전, Level1과 2  사이의 보안성 제공 (타 보안솔루션과 충돌시에만 사용 권장)

### 2017.04.20

#### 버그 수정
* 앱변조 방지기능 적용시 일부 앱 설치 문제 수정
* 앱변조 방지기능 적용시 외부 리소스 사용앱에 대한 호환성 강화
* Unity3d 5.6 버전에서 NHN AppGuard 빌드 오류 수정

### 2017.04.04

#### 버그 수정
* 앱 변조 방지 기능 multidex 버그 수정

### 2017.03.23

#### 기능 개선/변경
* [SDK] Unity3d il2cpp 빌드 지원 기능 추가

#### 버그 수정
* 정책 업데이트가 늦어지는 경우, 차단 로직이 정상적으로 수행되지 않던 문제 수정
* Android 로그에 불필요한 익셉션이 출력되는 문제 수정

### 2017.01.19

#### 기능 개선/변경
* [SDK] NHN AppGuard iOS SDK 신규 배포
* apk 변조 방지 기능 강화

#### 버그 수정
* 정책 설정과 탐지 로직 간 동기화 오류 수정
* 네트워크 상황에 따른 크래쉬 이슈 수정 (로그 전송 라이브러리 업데이트)

### 2016.12.22

#### 기능 개선/변경
* 치팅툴 탐지 패턴 추가
* [Console] 탐지 로그에 NHN AppGuard 엔진 버전 정보 추가

### 2016.12.08

#### 기능 개선/변경
* 루팅 탐지 패턴 추가
* [SDK] NHN AppGuard에서 차단시 표시되는 메시지 다국어 설정 API 추가

#### 버그 수정
* [Console] 보호가 실패하였는데 웹 콘솔상에 성공으로 표시되는 오류 수정

### 2016.11.24

#### 기능 개선/변경

* [SDK] NHN AppGuard SDK(tcag.jar) 업데이트
* [Console] NHN AppGuard Web Console에 공지사항 추가

### 2016.10.20

#### 기능 개선/변경

* [API] NHN AppGuard SDK 연동 함수 매개변수 변경
* [SDK] NHN AppGuard CLI(Command Line Build) 툴 자동 업데이트 기능 추가

### 2016.09.29

#### 버그 수정

* [Console] 약관 동의 창 위치, 링크 오류 수정
* [Console] 앱 보호시 UI 깨짐 현상 수정

### 2016.09.08

#### 버그 수정

* Android 7.0 스피드핵 오탐 수정

### 2016.08.18

#### 기능 개선/변경

* 탐지 패턴 업데이트
* Android N 지원
* [Console] iOS 로그 조회 기능 추가
* [Console] 한 페이지에 표시되는 로그 수 변경 기능 추가 (15 고정 -> 15/30/50 선택 가능)

### 2016.08.04

#### 기능 개선/변경

* 스피드조작 탐지 강화

#### 버그 수정

* Timer로 인한 일부 오류 수정
