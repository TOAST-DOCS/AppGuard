## Security > NHN AppGuard > Gradle Plugin Guide

### Overview

NHN AppGuard Gradle Plugin supports build automation so that protection operations can be included in Android Gradle build steps. If you are using ProGuard and Firebase Crashlytics, you can read and apply ProGuard mapping files to use with NHN AppGuard obfuscation.

### Supported Environment

- Android Gradle Plugin (AGP) 3.0.1 or higher

- firebase-crashlytics-gradle 2.2.0~2.8.0

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
        classpath 'com.nhncloud.android:appguard-gradle-plugin:1.0.0'
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

| Option                    | Description                       | Required |
| --------------------- | ------------------------ | ----- |
| enabled               | Whether to apply the AppGuard Gradle plugin       | Y     |
| appBundle             | Whether to apply the app bundle               | Y     |
| obfuscate             | Whether to apply AppGuard obfuscation            | Y     |
| level                 | Obfuscation level                   | Y     |
| appKey                | Appkey that can be found in the console     | Y     |
| version               | AppGuard version                   | Y     |
| appGuardSDKFolderPath | AppGuard SDK folder path            | N     |
| overrideOutputFile    | Whether to overwrite protected files           | N     |
| extraOptions          | Add options used in CLI (contact us if necessary) | N     |

### Setting the NHN AppGuard Gradle Plugin Options

Write appguard options in your app-level build.gradle file.

```groovy
appguard {
    enabled = true
    appBundle = true
    obfuscate = false
    level = 3
    appKey = "Appkey issued from the web console"
    version = "Protector version"

    appGuardSDKFolderPath = "AppGuard SDK folder path" // optional
    overrideOutputFile = false // optional
    extraOptions = "" // optional
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
