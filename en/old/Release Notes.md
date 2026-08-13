<!-- pre-align:aligned sig=d8474a977e05 -->

<a id="security-appguard-release-notes"></a>
## Security > AppGuard > Release Notes { #security-appguard-release-notes }

<a id="security-appguard-release-notes-1"></a>
### 2017.12.21 { #security-appguard-release-notes-1 }

<a id="security-appguard-release-notes-1-function-upgradechange"></a>
#### function upgrade/change
* Enhanced Unity Speed Hack Detection
<a id="security-appguard-release-notes-1-bug-fix"></a>
#### bug fix
* Fixed an error that occurred during the protection operation in the latest version of Unity Personal (2017.x.x version)
* Fixed an apk increase in size unnecessarily when protecting multi-dex (3 or more) apps

<a id="security-appguard-release-notes-2"></a>
### 2017.08.24 { #security-appguard-release-notes-2 }

<a id="security-appguard-release-notes-2-function-upgradechange"></a>
#### function upgrade/change
* Removal of charge/free selection window (Apply September 1)
* Support Android 8.0
<a id="security-appguard-release-notes-2-bug-fix"></a>
#### bug fix
* Modify the module(CLIUpdater.exe) that automatically updates the AppGuard CLI(AppGuard.exe), required update
    * Requires CLI of latest SDK (If you don't want automatic update function, add --noUpdate as CLI option)

<a id="security-appguard-release-notes-3"></a>
### 2017.07.20 { #security-appguard-release-notes-3 }

<a id="security-appguard-release-notes-3-function-upgradechange"></a>
#### function upgrade/change
* Fixed an error that Callback function is not called when detecting on Level 1~3
* Add optimization function option for Level 1~3

<a id="security-appguard-release-notes-4"></a>
### 2017.06.22 { #security-appguard-release-notes-4 }

<a id="security-appguard-release-notes-4-function-upgradechange"></a>
#### function upgrade/change
* App that use jni for x86_64, arm64-v8a will have an AppGuard module for that architecture.
* Divide path to download SDK for Android, iOS(Beta)
* The iOS(Beta) version is free for all users
* Enhancement of the module detection function of the AppGuard itself
* Extend Unity3D DLL File Encrpyt
    * Unitiy Basic DLL files as well as DLL files separately added are also encrypted. (Level 3)

<a id="security-appguard-release-notes-5"></a>
### 2017.05.25 { #security-appguard-release-notes-5 }

<a id="security-appguard-release-notes-5-function-upgradechange"></a>
#### function upgrade/change
* Simplify application Android version
    * before : Protection work after SDK linkage
    * after : You can apply only protection work (If user ID identifier registration is necessary, it is necessary to selectively be linked SDK, but it becomes simpler than before.)
* Restructure App Protection Level
    * Level 1 : Abnormal behavior and pattern based basic security behavior detect about app
    * Level 2 : Level1 + Enhanced security function such as Encrypt source code, Prevent to modify App, etc.
    * Level 3 : Level2 + More Enhanced security function(Because stability check may be required for certain services, it is recommended to use it only if you have received a separate guide)
    * Level ex : Version of must required SDK be linked, Provide security between level1 to level2(it is recommended when conflict other security solution)

<a id="security-appguard-release-notes-6"></a>
### 2017.04.20 { #security-appguard-release-notes-6 }

<a id="security-appguard-release-notes-6-bug-fix"></a>
#### bug fix
* Fix some app intall issues when applying app modification prevent function
* Enhance compatibility with apps that use external resources when applying app modification prevent function
* Fix app guard build error in version 5.6 of Unity3d

<a id="security-appguard-release-notes-7"></a>
### 2017.04.04 { #security-appguard-release-notes-7 }

<a id="security-appguard-release-notes-7-bug-fix"></a>
#### bug fix
* Fix multidex bug of app modification prevent function

<a id="security-appguard-release-notes-8"></a>
### 2017.03.23 { #security-appguard-release-notes-8 }

<a id="security-appguard-release-notes-8-function-upgradechange"></a>
#### function upgrade/change
* [SDK] Add function of supporting Unity3d il2cpp build

<a id="security-appguard-release-notes-8-bug-fix"></a>
#### bug fix
* Fix an issue where blocking logic was not executed normally when policy update was delayed
* Fix an issue where unnecessary exceptions were output to Android logs

<a id="security-appguard-release-notes-9"></a>
### 2017.01.19 { #security-appguard-release-notes-9 }

<a id="security-appguard-release-notes-9-function-upgradechange"></a>
#### function upgrade/change
* [SDK] New AppGuard iOS SDK deploy
* Enhance function of apk modification prevention

<a id="security-appguard-release-notes-9-bug-fix"></a>
#### bug fix
* Fix synchronization error between policy settings and detection logic
* Fix crash issue based on network conditions (Update log transfer library)

<a id="security-appguard-release-notes-10"></a>
### 2016.12.22 { #security-appguard-release-notes-10 }

<a id="security-appguard-release-notes-10-function-upgradechange"></a>
#### function upgrade/change
* Add detection pattern of cheating tool
* [Console] Add information of AppGuard engine version in detection logs

<a id="security-appguard-release-notes-11"></a>
### 2016.12.08 { #security-appguard-release-notes-11 }

<a id="security-appguard-release-notes-11-function-upgradechange"></a>
#### function upgrade/change
* Add detection pattern of rooting
* [SDK] Add multi-lingual setting API at message when blocking in AppGuard

<a id="security-appguard-release-notes-11-bug-fix"></a>
#### bug fix
* [Console] Fix an error that the protection failed but appears to be successful on the web console

<a id="security-appguard-release-notes-12"></a>
### 2016.11.24 { #security-appguard-release-notes-12 }

<a id="security-appguard-release-notes-12-function-upgradechange"></a>
#### function upgrade/change

* [SDK] Update AppGuard SDK(tcag.jar)
* [Console] Add Notice in AppGuard Web Console

<a id="security-appguard-release-notes-13"></a>
### 2016.10.20 { #security-appguard-release-notes-13 }

<a id="security-appguard-release-notes-13-function-upgradechange"></a>
#### function upgrade/change

* [API] Change parameter of AppGuard SDK linkage function
* [SDK] Add auto update function of AppGuard CLI(Command Line Build) tool

<a id="security-appguard-release-notes-14"></a>
### 2016.09.29 { #security-appguard-release-notes-14 }

<a id="security-appguard-release-notes-14-bug-fix"></a>
#### bug fix

* [Console] Fix window of agree terms and link error
* [Console] Fix UI break when protecting app

<a id="security-appguard-release-notes-15"></a>
### 2016.09.08 { #security-appguard-release-notes-15 }

<a id="security-appguard-release-notes-15-bug-fix"></a>
#### bug fix

* Fix false positives of speed hack detection in Android 7.0

<a id="security-appguard-release-notes-16"></a>
### 2016.08.18 { #security-appguard-release-notes-16 }

<a id="security-appguard-release-notes-16-function-upgradechange"></a>
#### function upgrade/change

* Update detection pattern
* Support Android N
* [Console] Add function to searching iOS logs
* [Console] Add function to change the number of logs displayed on a page (fixed 15 -> select 15/30/50)

<a id="security-appguard-release-notes-17"></a>
### 2016.08.04 { #security-appguard-release-notes-17 }

<a id="security-appguard-release-notes-17-function-upgradechange"></a>
#### function upgrade/change

* Enhance detection of speed manipulation

<a id="security-appguard-release-notes-17-bug-fix"></a>
#### bug fix

* Fix some errors due to Timer
