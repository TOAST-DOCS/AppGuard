## Security > NHN AppGuard > Gradle Plugin 가이드

### 개요

NHN AppGuard Gradle Plugin에서는 Android Gradle 빌드 단계에 보호 작업이 포함될 수 있도록 빌드 자동화를 지원합니다. ProGuard와 Firebase Crashlytics를 사용하는 경우 ProGuard 매핑 파일을 읽고 적용하여 NHN AppGuard 난독화와 함께 사용할 수 있습니다.

### 지원 환경

- AGP(Android Gradle Plugin) 3.0.1 이상

- firebase-crashlytics-gradle 2.2.0~2.8.0

### 라이브러리 설정

프로젝트 수준의 build.gradle 파일에 NHN AppGuard Gradle Plugin을 buildscript 의존성 항목으로 추가합니다.

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        // ...

        // Add the NHN Cloud AppGuard Gradle Plugin
        classpath 'com.nhncloud.android:appguard-gradle-plugin:1.0.1'
    }
}
```

앱 수준의 build.gradle 파일에 NHN AppGuard Gradle Plugin을 적용합니다.

```groovy
apply plugin: 'com.nhncloud.android.appguard'
```

### NHN AppGuard Gradle Plugin 옵션

플러그인 기능을 사용하려면 Appkey와 NHN AppGuard 버전을 반드시 명시해야 합니다.

콘솔에서 다운로드한 SDK 폴더를 지정할 수 있습니다. 해당 경로에 NHN AppGuard SDK가 설치되어 있지 않으면 지정된 폴더 경로에 NHN AppGuard SDK을 다운로드하고 압축을 해제합니다. 옵션이 지정돼 있지 않으면 프로젝트의 상대 경로 appguard 폴더에 NHN AppGuard SDK를 설치합니다.

보호된 파일의 다운로드 경로를 지정하지 않으면, 빌드된 Android 앱 파일을 덮어씁니다.

앱 번들 적용 여부, NHN AppGuard 난독화 적용 여부, 난독화 레벨, 기타 옵션도 설정할 수 있습니다. 옵션은 다음과 같습니다.

| 옵션                    | 설명                            | 필수 여부 |
| --------------------- | ----------------------------- | ----- |
| enabled               | 앱가드 그래들 플러그인 적용 여부            | Y     |
| appBundle             | 앱 번들 적용 여부                    | Y     |
| obfuscate             | 앱가드 난독화 적용 여부                 | Y     |
| plan                  | 보호 플랜(business, enterprise, game)  | Y     |
| appKey                | 콘솔에서 확인할 수 있는 Appkey          | Y     |
| version               | 앱가드 버전                        | Y     |
| appGuardSDKFolderPath | 앱가드 SDK 폴더 경로                 | N     |
| overrideOutputFile    | 보호된 파일 덮어쓰기 여부                | N     |
| extraOptions          | CLI에서 사용하던 옵션 추가(필요시 문의)      | N     |
| outputFilePath        | 보호된 파일 저장 경로(variants scope) | N     |

### NHN AppGuard Gradle Plugin 옵션 설정

앱 수준의 build.gradle 파일에 appguard 옵션을 작성합니다.

필수가 아닌 옵션은 생략 가능합니다.

```groovy
appguard {
    enabled = true
    appBundle = true
    obfuscate = false
    plan = game
    appKey = "웹 콘솔에서 발급받은 Appkey"
    version = "프로텍터 버전"
 /*   
    appGuardSDKFolderPath = "앱가드 SDK 폴더 경로" // optional
    overrideOutputFile = false // optional
    extraOptions = "" // optional
    variants {
        alphaRelease {
            outputFilePath = "~/A/B/C/example.apk"
        }
    }
*/
}
```

### 보호된 파일 경로 설정

1.0.1 버전부터 variants별로 보호된 파일 저장 위치 설정이 가능합니다.

**(root, buildTypes, productFlavors Scope에서는 설정이 불가합니다.)**

outputFilePath가 설정되지 않은 variants의 경우 overrideOutputFile 옵션에 따라, 원본 파일을 덮어쓰거나 _protected가 붙은 파일로 저장됩니다.

```groovy
def outputFolderPath = "~~/A/B/C/"
appguard{
    // ...
    variants {
          AlphaRelease {
              outputFilePath = outputFolderPath + "alpha-release.apk"
          }     
          BetaRelease {
              outputFilePath = outputFolderPath + "beta-release.apk"
          }  
    }     
}
```

### Proguard와 Firebase Crashlytics를 사용할 경우 난독화 적용

#### 사전 준비

1. 프로젝트에서 앱가드 난독화를 사용중이어야 합니다.

2. 안드로이드 프로젝트에서 [Proguard](https://www.guardsquare.com/manual/home)를 사용중이여야 합니다.

3. [FireBase Crashlytics](https://firebase.google.com/docs/crashlytics) 업로드 기능을 사용 중이어야 합니다. 사용하지 않더라도 난독화는 적용할 수 있습니다.

#### 적용 방법

앱 수준의 build.gradle 파일에 다음과 같이 appguard 옵션을 작성합니다.

```groovy
appguard {
    // ...
    enabled = true
    obfuscate = true
}
```
