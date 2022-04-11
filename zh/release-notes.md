## Security > NHN AppGuard > Release Notes

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
    * 앱가드 버전 지정하여 보호작업하도록 수정
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

#### Feature Updates 
* [Android] 1.8.8.0
    * 엔진 보안성 강화
    * 암호화 API 기능 개선

### 2021. 10. 8.

#### Bug Fixes
* [Android] 1.8.7.1
    * 구글 Play Asset Delivery 지원기능 오류 수정
    
### 2021. 9. 28.

#### Feature Updates 
* [Android] 1.8.7.0
    * Enhanced the security of the engine
    * Added Google SafetyNet malicious app detection

#### Feature Updates 
* [iOS] 1.1.4
    * Enhanced the security of the engine
    * Reinforced protection feature through AppGuard protector

### 2021. 9. 1.

#### Bug Fixes
* [Android] 1.8.6.1
    * Fixed the crash on Unity using SQLite
    * Modified security features of Unreal
    
### 2021. 8. 24.

#### Feature Updates 
* [Android] 1.8.6.0
    * Enhanced the security of the engine
    * Improved security features of Unreal
    * Improved the speed of protection tasks
    * Supports CLI macOS M1
    
### 2021. 7. 27.

#### Feature Updates 
* [iOS] 1.1.2
    * Strengthened engine security
    * Project update
    
* Change web console page
    * The app protection operation has been changed to asynchronous.

### 2021. 7. 13.

#### Feature Updates
* [Android] 1.8.5.1
    * Improve the feature for app support that applies Google Play Asset Delivery 
    
### 2021. 6. 29.

#### Feature Updates
* [Android] 1.8.5.0
    * Strengthening engine security
    * Improved the security features of Unity
    * Improved CLI error handling
  
* [iOS] 1.1.1
    * Strengthened engine security
    * Added IAP abusing detection
    * Improved internal test logic
  
### 2021. 5. 25.

#### Feature Updates
* [iOS] 1.1.0
    * Improvements in engine performance
    * Engine stability
    
### 2021. 5. 24.

#### Feature Updates
* [Android] 1.8.4.0
    * Strengthening engine security
    * Engine stability
    * mprovements with the issue of certain versions of Unity 2020 crashing

### 2021. 5. 11.

#### Feature Updates
* [Android] 1.8.3.1
	* Added the remote control detecting function
	
### 2021. 4. 27.

#### Feature Updates
* Changed service name (AppGuard -> NHN AppGuard)
* [Android] 1.8.3.0
	* Reinforced security of NHN AppGuard engine
* [iOS] 1.0.18
	* Changed handling logic after detecting malicious behaviors
	* Reinforced security of NHN AppGuard engine
	* Stabilized NHN AppGuard engine
 
### 2021. 4. 12.

#### Bug Fixes
* [iOS] 1.0.17
    * Added the NHN AppGuard hooking detection logic

### 2021. 4. 09.

#### Bug Fixes
* [Android] 1.8.2.2
	* Fixed the crashing issues in the Cocos2d engine emulator
	
### 2021. 3. 31.

#### Bug Fixes
* [Android] 1.8.2.1
	* Fixed the crashing issues in the Facebook SDK
	
### 2021. 3. 23.

#### Feature Updates
* [Android] 1.8.2.0
    * NHN AppGuard engine security enhanced
* [iOS] 1.0.16
    * NHN AppGuard engine security enhanced
    
### 2021. 2. 23.

#### Feature Updates
* [Android] 1.8.1.0
    * CLI feature improved
    * NHN AppGuard engine stabilized
    * NHN AppGuard engine security enhanced
* [iOS] 1.0.15
    * NHN AppGuard engine stabilized

### 2021. 1. 26.

#### Feature Updates
* [Android] 1.8.0.1
    * Third party store support
    * Upgraded detection of game hacks 

### 2020. 12. 29.

#### Bug Fixes
* Stabilized the NHN AppGuard engine

### 2020. 08. 25.

#### Feature Updates
* [Android] Updated detection of virtual environment 
* [iOS] Upgraded detection of jailbreaking 
* [iOS] Upgraded detection of game hacks 

### 2020. 07. 28.

#### Feature Updates
* [Android] Added detection of virtual environment
* [iOS] Sophisticated jailbreaking detection
* [iOS] Sophisticated forced closure
* [iOS] Added the feature of blocking blacklist

#### Bug Fixes
* [Android] Updated crashes in Unity Mono Emulator version 7
* [iOS] Updated clashes in Gamepot framework

### 2020. 06. 23.

#### Feature Updates
* Updated downsizing NHN AppGuard volume
* Fortified NHN AppGuard engine security

#### Bug Fixes
* Fixed bugs in unreal engine protection

### 2020. 05. 26.

#### Feature Updates
* Added the obfuscation application  

#### Bug Fixes
* Stabilized the NHN AppGuard engine

### 2020. 04. 28

#### Feature Updates
* Added the detection of attacks with SSL pinning  

### 2020. 03. 24.

#### Feature Updates
* Supports the Android 7.0 emulator

### 2020. 02. 25.

#### Feature Updates/Changes
* Added modified app countermeasures logic

### 2020. 01. 21.

#### Feature Updates/Changes
* Stabilized the NHN AppGuard engine

### 2019. 12. 24.

#### Feature Updates/Changes
* Added The Cocos2d-x engine encryption modules

### 2019. 11. 26.

#### Feature Updates/Changes
* Updated to Select NHN AppGuard Version

#### Bug Fixes
* Fixed String obfuscation bugs

### 2019. 10. 29.

#### Feature Updates/Changes
* Updated the anti-debugging feature
* Updated game hack detection
* Added the memory search detection feature

#### Bug Fixes
* Stabilized the NHN AppGuard engine

### 2019. 09. 24.

#### Feature Updates/Changes
* Enhanced Stability for NHN AppGuard Android Q

### 2019. 08. 27.

#### Feature Updates/Changes
* Supported Android Q
* Added Block by Condition on web console and blacklisting  
* Added real-time policy setting for NHN AppGuard iOS
* Added machine learning-based macro detection for Unity games and support of web console
* Updated integrity checks for NHN AppGuard modules
* Added web console inspection logs

### 2019. 07. 23.

#### Feature Updates/Changes
* Enabled the support of Android App Bundle
* Added Unity library packing
* Added macro detection of Unity MONO build

#### Bug Fixes
* Fixed bugs in dex integrity check

### 2019. 06. 25.

#### Feature Updates/Changes
* Fortified protection of 64-bit NHN AppGuard library
* Added obfuscation in NHN AppGuard control flow
* Added crash reporting

#### Bug Fixes
* Fixed bugs in the check of authority change of NHN AppGuard path

### 2019. 05. 28.

#### Feature Updates/Changes
* Changed to add 64-bit library as default, according to Google guides
	* Before Change: 32 or 64-bit library was added depending on user's ABI
	* Now: Both 32 and 64-bit library are available
* Upgraded macro detection

#### Bug Fixes
* [Android] Fixed undetected emulator bugs
* [iOS] Fixed bugs in integrity check

### 2019.04.23

#### function upgrade/change
* Add Unity IL2CPP method encryption function
	* Applied with CLI option "--il2cpp-encryption"
* Add Unity MONO method encryption function
	* Applied to NHN AppGuard level3
* Add Emulator Detection Pattern
	* Memu Player latest version(6.1.1)

#### bug fix
* Fixed a multi-deck duplicate installation error on Android OS 4.X version

### 2019.03.26

#### function upgrade/change
* Apply Unity Library obfuscation
* Add NHN AppGuard API / Method obfuscation function

### 2019.02.26

#### function upgrade/change
* Apply NHN AppGuard self-obfuscation
* Unity latest version(2018) compatibility improvement
	* MONO, IL2CPP build encryption function
* Add Emulator Detection Pattern
	* NOX latest version(6.2.7.0)

### 2019.01.29

#### function upgrade/change
* Unity latest version compatibility improvement

### 2018.12.27

#### function upgrade/change
* Enhanced self-protection
* Add Dex Loader Obfuscation Function
* Add Hooking Detection Pattern
* Add Rooting Detection Pattern
* Add Emulator Detection Pattern
* Enhanced Unity IL2CPP Build Protection Function
	* IL2CPP Dumper Tool Prevention

### 2018.11.27

#### function upgrade/change
* Enhanced encryption function for Unity il2cpp build
* Enhanced Hooking Detection Function

### 2018.10.23

#### function upgrade/change
* Add function to applied NHN AppGuard verification
* Enhanced Rooting Detection
* Enhanced Debugging Detection

### 2018.08.28

#### bug fix
* NHN AppGuard Unity SDK
	* Fixed an error that editor linkage in Unity 5 or earlier

### 2018.07.24

#### function upgrade/change
* Support Unreal Engine 4
    * Support protection for game code of Unreal Engine 4

### 2018.06.26

#### function upgrade/change
* Improved compatibility in Android P(9.0)
* NHN AppGuard Unity SDK
    * Support UNITY 2018

### 2018.05.29

#### function upgrade/change
* Enhanced Memory Manipulation Detection
    * Enhanced detection of memory manipulation using cheating tool
#### bug fix
* Fixed an error that the anti-debugging function applied to Level 3 consumed battery excessively

### 2018.04.24

#### function upgrade/change
* Support game code encryption for Unity il2cpp build
    * Supports il2cpp build by extending game code encryption, which was only supported in Mono builds
* Improved anti-debugging(App analysis prevention technology)
    * Enhanced functionality and stability

### 2018.02.20

#### bug fix
* Fixed an error that the app with NHN AppGuard Level2 app was not running properly in Momo App Player version 1.2.1

### 2018.01.24

#### bug fix
* Fixed an error that would not run on Android 8.x specific devices if Level2 was applied to an app developed with Unity2017 version

### 2017.12.21

#### function upgrade/change
* Enhanced Unity Speed Hack Detection
#### bug fix
* Fixed an error that occurred during the protection operation in the latest version of Unity Personal (2017.x.x version)
* Fixed an apk increase in size unnecessarily when protecting multi-dex (3 or more) apps

### 2017.08.24

#### function upgrade/change
* Removal of charge/free selection window (Apply September 1)
* Support Android 8.0
#### bug fix
* Modify the module(CLIUpdater.exe) that automatically updates the NHN AppGuard CLI(AppGuard.exe), required update
    * Requires CLI of latest SDK (If you don't want automatic update function, add --noUpdate as CLI option)

### 2017.07.20

#### function upgrade/change
* Fixed an error that Callback function is not called when detecting on Level 1~3
* Add optimization function option for Level 1~3

### 2017.06.22

#### function upgrade/change
* App that use jni for x86_64, arm64-v8a will have an NHN AppGuard module for that architecture.
* Divide path to download SDK for Android, iOS(Beta)
* The iOS(Beta) version is free for all users
* Enhancement of the module detection function of the NHN AppGuard itself
* Extend Unity3D DLL File Encrpyt
    * Unitiy Basic DLL files as well as DLL files separately added are also encrypted. (Level 3)

### 2017.05.25

#### function upgrade/change
* Simplify application Android version
    * before : Protection work after SDK linkage
    * after : You can apply only protection work (If user ID identifier registration is necessary, it is necessary to selectively be linked SDK, but it becomes simpler than before.)
* Restructure App Protection Level
    * Level 1 : Abnormal behavior and pattern based basic security behavior detect about app
    * Level 2 : Level1 + Enhanced security function such as Encrypt source code, Prevent to modify App, etc.
    * Level 3 : Level2 + More Enhanced security function(Because stability check may be required for certain services, it is recommended to use it only if you have received a separate guide)
    * Level ex : Version of must required SDK be linked, Provide security between level1 to level2(it is recommended when conflict other security solution)

### 2017.04.20

#### bug fix
* Fix some app intall issues when applying app modification prevent function
* Enhance compatibility with apps that use external resources when applying app modification prevent function
* Fix app guard build error in version 5.6 of Unity3d

### 2017.04.04

#### bug fix
* Fix multidex bug of app modification prevent function

### 2017.03.23

#### function upgrade/change
* [SDK] Add function of supporting Unity3d il2cpp build

#### bug fix
* Fix an issue where blocking logic was not executed normally when policy update was delayed
* Fix an issue where unnecessary exceptions were output to Android logs

### 2017.01.19

#### function upgrade/change
* [SDK] New NHN AppGuard iOS SDK deploy
* Enhance function of apk modification prevention

#### bug fix
* Fix synchronization error between policy settings and detection logic
* Fix crash issue based on network conditions (Update log transfer library)

### 2016.12.22

#### function upgrade/change
* Add detection pattern of cheating tool
* [Console] Add information of NHN AppGuard engine version in detection logs

### 2016.12.08

#### function upgrade/change
* Add detection pattern of rooting
* [SDK] Add multi-lingual setting API at message when blocking in NHN AppGuard

#### bug fix
* [Console] Fix an error that the protection failed but appears to be successful on the web console

### 2016.11.24

#### function upgrade/change

* [SDK] Update NHN AppGuard SDK(tcag.jar)
* [Console] Add Notice in NHN AppGuard Web Console

### 2016.10.20

#### function upgrade/change

* [API] Change parameter of NHN AppGuard SDK linkage function
* [SDK] Add auto update function of NHN AppGuard CLI(Command Line Build) tool

### 2016.09.29

#### bug fix

* [Console] Fix window of agree terms and link error
* [Console] Fix UI break when protecting app

### 2016.09.08

#### bug fix

* Fix false positives of speed hack detection in Android 7.0

### 2016.08.18

#### function upgrade/change

* Update detection pattern
* Support Android N
* [Console] Add function to searching iOS logs
* [Console] Add function to change the number of logs displayed on a page (fixed 15 -> select 15/30/50)

### 2016.08.04

#### function upgrade/change

* Enhance detection of speed manipulation

#### bug fix

* Fix some errors due to Timer
