## Security > NHN AppGuard > Gradle Plugin Guide

### Overview

NHN AppGuard Gradle Plugin supports build automation so that protection operations can be included in Android Gradle build steps. If you are using ProGuard and Firebase Crashlytics, you can read and apply ProGuard mapping files to use with NHN AppGuard obfuscation.

### Supported Environment

- Android Gradle Plugin (AGP) 3.0.1 or higher

- firebase-crashlytics-gradle 2.2.0~2.8.0

- Gradle Plugin implementation is not supported in Unity environment.

### Library Settings

Add the NHN AppGuard Gradle Plugin as a buildscript dependency to your project-level build.gradle file.

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        // ...

        // Add the NHN Cloud AppGuard Gradle Plugin
        classpath 'com.nhncloud.android:appguard-gradle-plugin:1.2.0'
    }
}
```

Apply the NHN AppGuard Gradle Plugin to your app-level build.gradle file.

```groovy
apply plugin: 'com.nhncloud.android.appguard'
```

### NHN AppGuard Gradle Plugin Options

To use the plugin functions, you must specify the Appkey and NHN AppGuard version.

You can specify the folder of SDK downloaded from the console. If the NHN AppGuard SDK is not installed in that path, download and unzip the NHN AppGuard SDK to the specified folder path. If no option is specified, install the NHN AppGuard SDK in the appguard folder relative to your project root.

If you do not specify a download path for protected files, the built Android app files will be overwritten.

You can also set whether to apply the app bundle, whether to apply NHN AppGuard obfuscation, the level of obfuscation, and other options. The options are as follows:

| Option                        | Description                            | Required |
| ----------------------------- | ----------------------------- | ----- |
| enabled                       | Whether to apply the AppGuard Gradle plugin            | Y     |
| appBundle                     | Whether to apply the app bundle                    | Y     |
| obfuscate                     | Whether to apply AppGuard obfuscation                 | Y     |
| plan                          | 보호 플랜(Business, Enterprise, Game)  | Y     |
| appKey                        | Appkey that can be found in the console          | Y     |
| version                       | AppGuard version                        | Y     |
| certificateFingerprintEnabled | 앱 서명 검증을 위한 인증서 지문 활성화<br>(활성화 기본 설정)    | N      |
| certificateFingerprints       | 앱 서명 검증을 위한 인증서 지문 (SHA-256)<br>(최대 10개까지 입력 가능)| N <br> (certificateFingerprintEnabled 활성화 시 필수)      |
| appGuardSDKFolderPath         | AppGuard SDK folder path                 | N     |
| overrideOutputFile            | Whether to overwrite protected files                | N     |
| extraOptions                  | Add options used in CLI (contact us if necessary)      | N     |
| outputFilePath                | Storage path for the protected file (variants scope) | N     |

### Setting the NHN AppGuard Gradle Plugin Options

Write appguard options in your app-level build.gradle file.

Options that are not required can be omitted.

```groovy
appguard {
    enabled = true
    appBundle = true
    obfuscate = false
    plan = game
    appKey = "Appkey issued from the web console"
    version = "Protector version"
    certificateFingerprintEnabled = true // optional, true 기본 설정
    certificateFingerprints = [
        "xx:xx:xx..",
        "xx:xx:xx..",
        ...
    ] // optional, certificateFingerprintEnabled = true 설정 시 필수
 /*   
    appGuardSDKFolderPath = "AppGuard SDK folder path" // optional
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

### Setting the Protected File Path

From version 1.0.1, you can set a protected file storage location for each variants.

**(It cannot be set in root, buildTypes, and productFlavors scope.)**

For variants with outputFilePath unset, the original file will be overwritten or the protected file is saved as a file with `_protected` appended, depending on the value of the overrideOutputFile option.

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

### Applying Obfuscation When Using Proguard and Firebase Crashlytics

#### Prerequisites

1. You must be using AppGuard obfuscation in your project.

2. You must be using [Proguard](https://www.guardsquare.com/manual/home) in your Android project.

3. You must be using the [FireBase Crashlytics](https://firebase.google.com/docs/crashlytics) upload feature. Obfuscation can be applied even if the feature is not used.

#### How to Apply

Write the appguard options in your app-level build.gradle file like the following:

```groovy
appguard {
    // ...
    enabled = true
    obfuscate = true
}
```

### 앱 서명 무결성 검증을 위한 인증서 지문 설정
1.2.0 버전부터 인증서 지문 활성화 여부와 검증에 사용될 인증서 지문(SHA-256)를 추가할 수 있습니다.<br>
**앱 서명 검증을 위한 인증서 지문은 활성화가 기본값이며, 활성화 시에는 인증서 지문을 반드시 입력해야 합니다.**

#### 적용 방법
앱 수준의 build.gradle 파일에 다음과 같이 appguard 옵션을 작성합니다.

- 서명 무결성 검증 활성화 
```groovy
appguard {
    certificateFingerprintEnabled = true 
    certificateFingerprints = [
        "xx:xx:xx..",
        "xx:xx:xx..",
        ...
    ]
}
```
- 앱 서명 무결성 검증 비활성화
```groovy
appguard {
    certificateFingerprintEnabled = false
}
```