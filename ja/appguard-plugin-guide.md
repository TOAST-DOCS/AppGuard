## Security > NHN AppGuard > Gradle Pluginガイド

### 概要

NHN AppGuard Gradle PluginではAndroid Gradleビルド段階に保護作業が含まれるようにビルド自動化をサポートします。 ProGuardとFirebase Crashlyticsを使用する場合、ProGuardマッピングファイルを読み込んで適用してNHN AppGuard難読化と一緒に使用できます。

### サポート環境

- AGP(Android Gradle Plugin) 3.0.1以上

- firebase-crashlytics-gradle 2.2.0~2.8.0

- Unity環境ではGradle Plugin方式をサポートしません。

### ライブラリ設定

プロジェクトレベルのbuild.gradleファイルにNHN AppGuard Gradle Pluginをbuildscript依存関係項目に追加します。

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        // ...

        // Add the NHN Cloud AppGuard Gradle Plugin
        classpath 'com.nhncloud.android:appguard-gradle-plugin:1.2.2'
    }
}
```

アプリレベルのbuild.gradleファイルにNHN AppGuard Gradle Pluginを適用します。

```groovy
apply plugin: 'com.nhncloud.android.appguard'
```

### NHN AppGuard Gradle Pluginオプション

プラグイン機能を使用するにはAppkeyとNHN AppGuardバージョンを必ず指定する必要があります。

コンソールからダウンロードしたSDKフォルダを指定できます。該当パスにNHN AppGuard SDKがインストールされていない場合は指定されたフォルダパスにNHN AppGuard SDKをダウンロードして解凍します。オプションが指定されていない場合はプロジェクトの相対パスappguardフォルダにNHN AppGuard SDKをインストールします。

保護されたファイルのダウンロードパスを指定しない場合は、ビルドされたAndroidアプリファイルを上書きします。

アプリバンドルを適用するかどうか、NHN AppGuard難読化を適用するかどうか、難読化レベル、その他オプションも設定できます。オプションは次のとおりです。

| オプション                       | 説明                                  | 必須かどうか |
| ----------------------------- | ------------------------------------ | ------ |
| enabled                       | AppGuard Gradleプラグインを適用するかどうか  | Y      |
| appBundle                     | アプリバンドルを適用するかどうか              | Y      |
| obfuscate                     | AppGuard難読化を適用するかどうか            | N      |
| plan                          | 保護プラン(Business, Enterprise, Game)  |  Y     |
| appKey                        | コンソールで確認できるAppkey                | Y      |
| version                       | AppGuardバージョン                      | Y      |
| certificateFingerprintEnabled | アプリ署名検証のための証明書指紋が有効<br>(有効が基本設定)    | N      |
| certificateFingerprints       | アプリ署名検証のための証明書指紋 (SHA-256)<br>(最大10個まで入力可)| N <br> (certificateFingerprintEnabledが有効の場合は必須)      |
| appGuardSDKFolderPath         | AppGuard SDKフォルダパス                  | N      |
| overrideOutputFile            | 保護されたファイルを上書きするかどうか            | N      |
| extraOptions                  | CLIで使用していたオプションを追加(必要なときはお問い合わせください)    | N      |
| outputFilePath                | 保護されたファイルの保存パス(variants scope)   | N      |

### NHN AppGuard Gradle Pluginオプション設定

アプリレベルのbuild.gradleファイルにappguardオプションを作成します。

必須ではないオプションは省略可能です。

```groovy
appguard {
    enabled = true
    appBundle = true
    obfuscate = false
    plan = "game"
    appKey = "Webコンソールで発行されたAppkey"
    version = "プロテクターのバージョン"
    certificateFingerprintEnabled = true // optional, true基本設定
    certificateFingerprints = [
        "xx:xx:xx..",
        "xx:xx:xx..",
        ...
    ] // optional, certificateFingerprintEnabled = true設定時に必須
 /*   
    appGuardSDKFolderPath = "AppGuard SDKフォルダパス" // optional
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

### 保護されたファイルのパス設定

1.0.1バージョンからvariantsごとに保護されたファイルの保存位置設定が可能です。

**(root, buildTypes, productFlavors Scopeでは設定ができません。)**

outputFilePathが設定されていないvariantsの場合、overrideOutputFileオプションによって、原本ファイルを上書きするか、_protectedがついたファイルとして保存されます。

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

### ProguardとFirebase Crashlyticsを使用する場合の難読化適用

#### 事前準備

1. プロジェクトでAppGuard難読化を使用している必要があります。

2. Androidプロジェクトで[Proguard](https://www.guardsquare.com/manual/home)を使用している必要があります。

3. [FireBase Crashlytics](https://firebase.google.com/docs/crashlytics)アップロード機能を使用している必要があります。使用していなくても難読化は適用できます。

#### 適用方法

アプリレベルのbuild.gradleファイルに次のようにappguardオプションを作成します。

```groovy
appguard {
    // ...
    enabled = true
    obfuscate = true
}
```

### アプリ署名の整合性検証のための証明書指紋設定
1.2.0バージョンから証明書指紋有効化有無と検証に使用される証明書指紋(SHA-256)を追加できます。<br>
**アプリ署名検証のための証明書指紋は有効がデフォルト値で、有効化するには証明書指紋を必ず入力する必要があります。**

#### 適用方法
アプリレベルのbuild.gradleファイルに次のようにappguardオプションを作成します。

- 署名の整合性検証を有効化
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
- アプリ署名の整合性検証を無効化
```groovy
appguard {
    certificateFingerprintEnabled = false
}
```
