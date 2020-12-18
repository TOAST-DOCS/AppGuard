## Security > AppGuard > Release Notes

### December 29, 2020

#### 기능 개선/변경
[Android] 서드 파티 스토어 지원용 옵션 추가

#### Bug Fixes
* Stabilized the AppGuard engine

### August 25, 2020

#### Feature Updates
[Android] Updated detection of virtual environment 
[iOS] Upgraded detection of jailbreaking 
[iOS] Upgraded detection of game hacks 

### July 28, 2020

#### Feature Updates
* [Android] Added detection of virtual environment
* [iOS] Sophisticated jailbreaking detection
* [iOS] Sophisticated forced closure
* [iOS] Added the feature of blocking blacklist

#### Bug Fixes
* [Android] Updated crashes in Unity Mono Emulator version 7
* [iOS] Updated clashes in Gamepot framework

### June 23, 2020

#### Feature Updates
* Updated downsizing AppGuard volume
* Fortified AppGuard engine security

#### Bug Fixes
* Fixed bugs in unreal engine protection

### May 26, 2020

#### Feature Updates
* Added the obfuscation application  

#### Bug Fixes
* Stabilized the AppGuard engine

### April 28, 2020

#### Feature Updates
* Added the detection of attacks with SSL pinning  

### March 24, 2020

#### Feature Updates
* Supports the Android 7.0 emulator

### February 25, 2020

#### Feature Updates
* Added the countermeasure logic to forged apps

### January 21, 2020

#### Feature Updates
* Stabilized the AppGuard engine

### December 24, 2019

#### Feature Updates
* Added Cocos2d-x engine encryption module

### November 26, 2019

#### Feature Updates
* Allows to select AppGuard version

#### Bug Fixes
* Fixed string obfuscation bugs

### October 29, 2019

#### Feature Updates
* Updated the anti-debugging feature
* Updated game hack detection
* Added the memory search detection feature

#### Bug Fixes
* Stabilized the AppGuard engine

### September 24, 2019

#### Feature Updates
* Enhanced Stability for AppGuard Android Q

### August 27, 2019

#### Feature Updates
* Supports Android Q Android Q
* Added conditional block on web console and blacklisting  
* Added real-time policy setting for AppGuard iOS
* Added machine learning-based macro detection for Unity games and web console support
* Updated integrity checks for AppGuard modules
* Added web console inspection logs

### July 23, 2019

#### Feature Updates
* Supports Android App Bundle
* Added Unity library packing
* Added macro detection of Unity MONO build

#### Bug Fixes
* Fixed bugs in dex integrity check

### June 25, 2019

#### Feature Updates
* Upgraded Appguard 64-bit library protection
* Added obfuscation in Appguard control flow
* Added crash reporting

#### Bug Fixes
* Fixed bugs in the check of authority change of Appguard path

### May 28, 2019

#### Feature Updates
* Changed to add 64-bit library as default, according to Google guides
	* Before Change: 32 or 64-bit library was added depending on user's ABI
	* Now: Both 32 and 64-bit library are available
* Upgraded macro detection

#### Bug Fixes
* [Android] Fixed undetected emulator bugs
* [iOS] Fixed bugs in integrity check

### April 23, 2019

#### Feature Updates
* Added the Unity IL2CPP method encryption feature
	* Applied with CLI option "--il2cpp-encryption"
* Added the Unity MONO method encryption feature
	* Applied with AppGuard level3
* Added emulator detection pattern
	* The latest Memu Player version(6.1.1)

#### Bug Fixes
* Fixed error in duplicate multi-deck installation on Android OS 4.X version

### March 26, 2019

#### Feature Updates
* Applies Unity Library obfuscation
* Added AppGuard API / Method obfuscation function

### February 26, 2019

#### Feature Updates
* Applies AppGuard self-obfuscation
* Upgraded the compatibility for the latest Unity version(2018)
	* Build encryption for MONO and IL2CPP
* Added emulator detection pattern
	* The latest NOX version(6.2.7.0)

### January 29, 2019

#### Feature Updates
* Upgraded the compabibility for the lastest Unity version

### December 27, 2018

#### Feature Updates
* Enhanced AppGuard self-protection
* Added obfuscation of Dex Loader
* Added hooking detection pattern
* Added rooting detection pattern
* Added emulator detection pattern
* Enhanced the Unity IL2CPP build protection feature
	* IL2CPP Dumper Tool Prevention

### November 27, 2018

#### Feature Updates
* Enhanced encryption for Unity il2cpp build
* Enhanced hooking detection

### October 23, 2018

#### Feature Updates
* Added the feature of confirming AppGuard application
* Enhanced rooting detection
* Enhanced debugging detection

### Aubust 28, 2018

#### Bug Fixes
* AppGuard Unity SDK
	* Fixed integration bugs for Unity 5 or lower versions

### July 24, 2018

#### Feature Updates
* Supports Unreal Engine 4
    * Supports protection of game codes for Unreal Engine 4

### June 26, 2018

#### Feature Updates
* Upgraded compatibility for Android P(9.0)
* AppGuard Unity SDK
    * Supports UNITY 2018

### May 29, 2018

#### Feature Updates
* Enhanced detection of memory manipulation
    * Enhanced the detection feature of memory manipulation based on cheating tools

#### Bug Fixes
* Fixed excessive battery consumption by the anti-debugging feature of Level 3

### April 24, 2018

#### Feature Updates
* Supports game code encryption for Unity il2cpp build
    * Supports il2cpp build by extending game code encryption, which was supported only for Mono builds
* Improved anti-debugging (app analysis prevention technology)
    * Enhanced functionality and stability

### February 20, 2018

#### Bug Fixes
* Fixed errors in which apps with AppGuard Level2 were not running properly on the Momo App Player 1.2.1 version

### January 24, 2018

#### Bug Fixes
* Fixed errors on particular Android 8.x devices, for which Level 2 was not properly executed on apps developed with Unity 2017

### December 21, 2017

#### Feature Updates
* Enhanced speed hack detection on Unity

#### Bug Fixes
* Fixed an error that occurred during the protection operation in the latest version of Unity Personal (2017.x.x version)
* Fixed unnecessary size increase of apk when protecting multi-dex (3 or more) apps

### August 24, 2017

#### Feature Updates
* Removed the Charged/Charge-Free selection window (as of September 1)
* Supports Android 8.0

#### Bug Fixes
* Modified the module (CLIUpdater.exe) that automatically updates the AppGuard CLI(AppGuard.exe), which requires updates
    * Requires CLI of latest SDK (if you don't want automatic updates, add --noUpdate as CLI option)

### July 20, 2017

#### Feature Updates
* Fixed an error in which the callback function was not called when detected, on Level 1~3
* Sets volume optimization as an option for Level 1~3

### June 22, 2017

#### Feature Updates
* Includes Appguard modules for each architecture, when using 64 bit architecture for x86_64 and jni for arm64-v8a.
* Divides SDK download paths for Android from iOS(Beta)
* Free service for iOS (Beta) users  
* Enhanced module detection of the AppGuard itself
* Extended the subject for Unity3D DLL file encryption
    * Encrypted default and additional DLL files of Unity (Level 3)

### May 25, 2017

#### Feature Updates
* Simplified the application method for Android
    * Previously: Protection after SDK integration
    * Now: Application is available only with protection (although SDK integration is required selectively, such as user ID identifier for registration, it is much simpler than before.)
* Restructure App Protection Level
    * Level 1: Basic security detection, like abnormal behavior and pattern-based
    * Level 2: Level1 + Enhanced security, including code encryption and app forgery prevention
    * Level 3: Level2 + More upgraded security features (which is recommended only for the specially guided, since some services may need stability checks)
    * Level ex: Requires SDK integration, providing security between Level 1 to Level 2 (recommended only when there's conflict with other security solutions)

### April 20, 2017

#### Bug Fixes
* Fixed some app intallation issues when app forgery prevention is applied
* Enhanced compatibility with apps that use external resources when app forgery prevention is applied
* Fixed app guard build error in version 5.6 of Unity3d

### April 4, 2017

#### Bug Fixes
* Fixed multidex bugs of app forgery prevention

### March 23, 2017

#### Feature Updates
* [SDK] Added the support of Unity3d il2cpp build

#### Bug Fixes
* Fixed an issue where blocking logic was not executed normally when policy update was delayed
* Fixed an issue where unnecessary exceptions were output to Android logs

### January 19, 2017

#### Feature Updates
* [SDK] Newly deployed AppGuard iOS SDK
* Enhanced the app forgery prevention feature

#### Bug Fixes
* Fixed synchronization error between policy settings and detection logic
* Fixed crash issue based on network conditions (updates on log transfer library)

### December 22, 2016

#### Feature Updates
* Added detection pattern of cheating tool
* [Console] Added information on AppGuard engine version for detection logs

### December 8, 2016

#### Feature Updates
* Added rooting detection pattern
* [SDK] Added multi-lingual setting API at message when blocking in AppGuard

#### Bug Fixes
* [Console] Fixed an error that the protection failed but appears to be successful on the web console

### November 24, 2016

#### Feature Updates

* [SDK] Updated AppGuard SDK(tcag.jar)
* [Console] Added notice on AppGuard Web Console

### October 20, 2016

#### Feature Updates

* [API] Changed parameter for the AppGuard SDK integration feature
* [SDK] Added auto tool updates for AppGuard CLI(Command Line Build)

### September 29, 2016

#### Bug Fixes

* [Console] Fixed the location error of pop-up for the consent of Terms, and linkage error
* [Console] Fixed UI breaks when protecting app

### September 8, 2016

#### Bug Fixes

* Fixed false positives of speed hack detection in Android 7.0

### August 18, 2016

#### Feature Updates

* Updated detection pattern
* Supports Android N
* [Console] Allows the search of iOS logs
* [Console] Allows to change the number of logs displayed on a page (fixed 15 -> select 15/30/50)

### August 4, 2016

#### Feature Updates

* Enhance detection of speed manipulation

#### Bug Fixes

* Fixed some errors due to Timer
