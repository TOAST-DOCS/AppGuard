## Security > NHN AppGuard > Release Notes

### February 16, 2024
* [Android] 1.10.5.4
    * Improved the malicious behavior detection pop-up design
    * Added NHN AppGuard Application bypass detection feature
    * Added detection of TeamViewer Host (Code: 1401)
    * Added detection of AnyDesk (Code: 1403)
    * Added detection of Auto Click - Automatic Clicker (Code: 1708)
    * Added detection of Auto Tapper: Auto Clicker (Code: 1709)
* [Unity] 0.4.2
    * (iOS) Fixed NHN AppGuard iOS build issues
        * Fixed an issue where, when using Package Manager, iOS build fail
    * (iOS) iOS SDK 1.3.15 update

### February 15, 2024
* [iOS] 1.3.15
    * Raised the minimum supported iOS version (iOS 11 or later)
    * Ended support for i386, armv7s, and armv7 architectures
    * Improved the default detection notification screen
    * Added privacy manifest
    * Added signature (NHN Cloud Corp.)

### January 23, 2024
* [Android] 1.10.5.3
    * Improved obfuscation
        * Improved the feature to hide function calls (Hide Call).

### January 9, 2024
* [Android] 1.10.5.2
    * Improved DEX encryption and decryption
    * Improved MEmu emulator detection
        * Detection available in Memu 9.0.9.
    * Improved LDPlayer9 emulator detection
        * Detection available in LDPlayer9 9.0.63.
    * Added the option to support Google Automatic Integrity Protection
        * When using Google Automatic Integrity Protection, must use the "--google-pairip" option.
* [iOS] 1.3.14
    * Improved engine stability
* [Unity] 0.4.1
    * (iOS) iOS SDK 1.3.14 update

### December 28, 2023
* [Android] 1.10.5.1
    * Fixed StackOverflowError issues

### December 19, 2023
* [Android] 1.10.5.0
    * Fixed Android 14-related issues
        * Fixed an issue that could cause abnormal termination when NHN AppGuard is applied to apps targeting Android 14 (API 34) or later.
    * Fixed Multiprocess-related issues
        * Fixed an issue that could cause an intermittent abnormal termination when an application component has the android:process attribute.
    * armeabi architecture errors
        * Fixed an abnormal termination error in apps using only the armeabi architecture.
* [iOS] 1.3.13
    * Enhanced engine security
    * Fixed an issue with missing logs when detecting before setting AppKey
        * Fixed an issue with missing logs when detecting malicious behavior in the Private API before setting AppKey.
        * Applied when setting protection.
    * Improved protection operation fails when obfuscating some class symbols
    * Improved CLI argument
        * The `--latestVersion` argument is now applied by default.
* [Unity] 0.4.0
    * [iOS] Improved NHN AppGuard iOS initialization
        * The Diresu.D function is no longer available (deprecated).
    * (iOS) iOS SDK 1.3.13 update
* [Gradle Plugin] 1.2.1
    * Fixed errors setting signing key password
        * Fixed an error where signing fails if the store password and key password do not match.

### December 06, 2023.
* [iOS] 1.3.12
    * Enhanced security of NHN AppGuard engine
* [Unity] 0.3.1
    * (iOS) iOS SDK 1.3.12 update

### November 24, 2023
* [Android] 1.10.4.1
    * Fixed NHN AppGuard security vulnerabilites

### November 21, 2023.
* [Android] 1.10.4.0
    * Enabled Amazon Appstore signature verification
        * App signature verification is enabled when protecting apps with the "--amazon" option.
        * In Amazon Appstore, you must use the "--as" option to set the SHA-256 Hexadecimal information for the Appstore signature.
        * The Appstore signature can be found in Amazon Developer > My apps > Appstore Certificate Hashes.
    * Added detection of SecureValue tampering (Code: 409)
    * Improved the way DEX loads
    * Enhanced NHN AppGuard security
* [iOS] 1.3.11
    * Enhanced jailbreaking environment detection
    * Added a static library distribution for Unreal Engine
    * Improved support for Unreal Engine
    * Enhanced the security of the engine
* [Unity] 0.3.0
    * (Android) Added detection of SecureValue tampering (Code: 409)
    * (iOS) iOS SDK 1.3.11 update

### October 24, 2023
* [iOS] 1.3.10
    * Fixed an issue where, when protecting Unity apps with obfuscation plugins applied, protection fails
* [Unity] 0.2.2
    * Updated to iOS SDK 1.3.10

### October 19, 2023
* [Android] 1.10.3.3
    * Enhanced security of NHN AppGuard engine
    * Added MEmu emulator detection
    * Improved safety for low-spec devices
    * Fixed an error where protection fails if the file name contains certain strings
* [iOS] 1.3.9
    * Enhanced Unity app protection
    * Improved to resend detection logs when User ID changes
    * Improved output messages when running re-signatures from the CLI
    * Improved stability
* [Unity] 0.2.1
    * Updated to iOS SDK 1.3.9

### September 26, 2023
* [Android] 1.10.3.2
    * Fixed false positives related to signature tampering
        * Fixed an issue where the signature of the keystore used for app protection was determined as tampering
    * Check for duplicate signatures
        * Modified to return an error when **the --as option** and the signature of the keystore are the same
* [Unity] 0.2.0
    * Added an option to disable Certificate Fingerprints
* [Gradle Plugin] 1.2.0
    * Added Certificate Fingerprints option

### September 13, 2023
* [Android] 1.10.3.1
    * Fixed false positives related to tampering of app signature
* [Unity] 0.1.8
    * Updated to iOS SDK 1.3.8

### September 12, 2023
* [Android] 1.10.3.0
    * [CLI] Changed an aditional option of app signature to a required item
        * When using signature methods of stores including Google Play and ONE store, the `--as` option is required
        * When signatures other than the signed information on apk or aab are not allowed, the `--no-as` option is required
    * Displayed a message when the app cannot run due to low device capacity
    * Added support for Google Automatic Integrity Protection
    * Improved Knox emulator detection
    * Enhanced security of NHN AppGuard engine
    * Improved identifier obfuscation
    * Improved hooking detection
    * Add Auto Click Assistant(Code: 1707) detection
    * Improved safety for low-spec tablets
* [iOS] 1.3.8
    * Enhanced engine security
    * Enhanced app decryption prevention

### August 17, 2023
* [Android] 1.10.2.2
    * Enhanced hooking detection
    * Improved engine stability
    * [Unity] Fixed abnormal shutdown issues on Android 4.4(API 19)
* [iOS] 1.3.7
    * Enhanced engine security
    * Enhanced app decryption prevention
    * Added the resigning feautre to CLI
        * The existing re-sign script is no longer available.
* [Unity] 0.1.7
    * Updated to iOS SDK 1.3.7

### July 21, 2023
* [Android] 1.10.2.1
    * Fixed abnormal termination error on app launch
    * Improved obfuscation
        * Fixed an issue where protection fails when the method for obfuscation exceeds 65K
    * Improved response against policy tempering

### July 11, 2023
* [Android] 1.10.2.0
    * Enhanced abusing app detection
    * Improved NHN AppGuard default policy
    * Fixed blacklist bug
* [Gradle Plugin] 1.1.2
    * Fixed an issue where the mapping.txt file is not uploaded in Firebase Crashlytics Gradle 2.8.1 or higher
* [iOS] 1.3.6
    * Enhanced engine security
    * Enhanced detection of Info.plist tampering
    * Added app decryption prevention
    * Improved default policy feature
    * Deprecated f function
* [Unity] 0.1.6
    * Improved stability
    * Updated to iOS SDK 1.3.6

### July 6, 2023
* [Android] 1.10.1.2
    * Enhanced rooting detection
    * Improved stability

### June 16, 2023
* [Unity] 0.1.5
    * Updated to iOS SDK 1.3.5

### June 15, 2023
* [iOS] 1.3.5
    * Info.plist 변조 오탐 수정
* [iOS] 1.3.4
    * Enhanced engine security
* [Unity] 0.1.4
    * Updated to iOS SDK 1.3.4

### June 13, 2023
* [Android] 1.10.1.0
    * Improved detection performance of the macro tool
    * Added support for Amazon Appstore

* [iOS] 1.3.3
    * Added resource tampering detection feature (Info.plist tempering response)
    * Improved detection callback data format (Refer to the user guide)
    * Improved detection code format (Refer to the user guide)
    * Fixed a bug where, when running the re-signing script, re-signing fails if the path contains spaces
    * Improved engine security
    * Excluded the AdSupport.framework
    
* [Unity] 0.1.3
    * Removed Xcode library dependencies
    * Excluded the AdSupport.framework
    * Updated to iOS SDK 1.3.3

### May 30, 2023
* [Android] 1.10.0.5
    * Fixed identifier obfuscation errors

* [Gradle Plugin] 1.1.1
    * Fixed extraOptions errors

### May 11, 2023
* [iOS] 1.3.2
    * Enhanced engine security (Unity)

* [Unity] 0.1.2
    * Improved so that the CLI protection can run on the Linux operating system
    * Updated to iOS SDK 1.3.2

### May 2, 2023
* [Android] 1.10.0.4
    * Fixed false positives in permission tampering (400_106_0)

### April 25, 2023
* [Android] 1.10.0.3
    * Added detection of tampering with the android:debuggable property in AndroidManifest.xml
    * Fixed library packing errors
    * Improved application shutdown logic when abnormal behaviors are blocked
    * [CLI] Improved handling of protection task failures
    * [CLI] Improved protected app downloads
    * [Unity] Improved il2cpp encryption
    * [Unity] Improved integrity checks for game memory
    * [Cocos2d] Fixed an issue where symbol analysis is not performed in Crashlyitcs

* [iOS] 1.3.1
    * Enhanced engine security
    * Integrated with conditional block policy
    * Removed info.plist of framework

* [Unity] 0.1.1
    * Updated to iOS SDK 1.3.1

### April 14, 2023
* [Android] 1.10.0.2
    * Fixed abnormal shutdown issues on 32 bit emulators
    * Fixed string obfuscation issues

### April 10, 2023
* [Android] 1.10.0.1
    * Fixed string encryption errors

### March 28, 2023
* [Android] 1.10.0.0
    * Improved application shutdown logic when external attacks are detected
    * Changed pricing plans (Business, Enterprise, Game)

* [iOS] 1.3.0
    * Enhanced engine security
    * Changed pricing plans (Business, Enterprise, Game)

* [Unity] 0.1.0
    * Released NHN AppGuard Unity SDK 

* [Gradle Plugin] 1.1.0
    * Changed pricing plan options (Business, Enterprise, Game)
    
### February 28, 2023
* [Android] 1.9.13.5
    * Improved detection of abusing app licenses
    * Fixed an issue where conditional block policy is not applied
    * Fixed crash issues when launching a Unity app
    * Fixed false positives in Unity integrity checks (405_49_0)
    
* [iOS] 1.2.10
    * Enhanced the security of the engine
    * Improved the compatibility for iOS 15
    
### February 8, 2023    
* [Android] 1.9.13.1
    * Fixed DEX obfuscation issues

### January 31, 2023
* [Android] 1.9.13.0
    * Changed encryption API header
    * Fixed app bundle issue
    * Enhanced security function
    * Fixed x86 and x86_64 issues

* [iOS] 1.2.9
    * Added default policy features
    * Enhanced the security of the engine
    * Fix simulator false positive issues
    * Supported xcframework
    * Improved AppGuard CLI feature

### December 27, 2022
* [Android] 1.9.12.0
    * Ended support for client policies
    * Added default policy features
    * Fixed an issue where the warning screen id not displayed 

* [iOS] 1.2.8
    * Enhanced the security of the engine
    * Improved the compatibility for iOS 16

### December 13, 2022
* [Android] 1.9.11.2
    * Fixed API exposure issues
    * Fixed LifecycleCallback issues
    * Fixed crash issues and false positives in specific protection feature
    * Fixed x86 crash issues

### December 7, 2022
* [Android] 1.9.11.1
    * Fixed false positives related to tampering

### November 29, 2022
* [Android] 1.9.11.0
    * Fixed frame drop issues
    * Fixed an issue of not detecting SSL pinning bypass
    * Added support for Google Play Games
    * Fixed crash issues

* [iOS] 1.2.7
    * Enhanced API hooking detection logics
    * Fixed issues related to policies
    * Improved AppGuard CLI feature

### November 9, 2022
* [Android] 1.9.10.2
    * Fixed background crash issues

### November 2, 2022
* [Android] 1.9.10.1
    * Fixed crash issues

### October 28, 2022
* [iOS] 1.2.6
    * Enhanced the security of the engine

### October 25, 2022
* [Android] 1.9.10.0
    * Enhanced the emulator detection function
    * Enhanced detection of hacking tools

### October 14, 2022
* [Android] 1.9.9.2
    * Added support for LDPlayer4 64bit emulator
    * Added a Korean warning screen
    * Improved the speed of initialization
    * Fixed a crash issue with emulators
    * Enhanced the security of the engine

### October 7, 2022
* [Android] 1.9.9.1
    * Removed the version

### October 4, 2022
* [Android] 1.9.9.0
    * Removed the version

* [iOS] 1.2.5
    * Enhanced the security of the engine
    * Fixed network-related bugs
    * Enhanced the security related to repackaging

### September 8, 2022
* [Android] 1.9.8.1
    * Fixed manifest issue

### August 23, 2022
* [Android] 1.9.8.0
    * Added support for Crema device 
    * Added support for BluesStacks, Nox, LDPlayer9 64-bit emulators
    * Stopped support for SafetyNet
    * Enhanced the security of the engine
    * Fixed Unity protection operation issues

* [iOS] 1.2.4
    * Enhanced the security of the engine
    * Added tweak detection feature

### July 26, 2022
* [Android] 1.9.7.0
    * Enhanced the security of the engine
    * Fixed manifest bug
    * Fixed undetected bug

* [iOS] 1.2.3
    * Enhanced the security of the engine
    * Added API related Device ID

* [Gradle Plugin] 1.0.2
    * Print out CLI console logs

### July 6, 2022
* [Android] 1.9.6.1
    * Fixed ANR issue
    * Enhanced the security of the engine

### June 30, 2022

#### Feature Updates
* [Android] 1.9.6.0
    * Fixed some ANR issues
    * Enhanced the security of the engine

* [iOS] 1.2.2
    * Enhanced detection of tampering
    * Added a Unity-specific security API
    * Enhanced the security of the engine

* [Gradle Plugin] 1.0.1
    * Added an option to set the storage path for the protected file by variants
    * Made improvements so that whitespaces are allowed in the signing key password and alias

### May 24, 2022

#### Feature Updates
* [Android] 1.9.5.0
    * Improved the blacklist blocking function
    * Fixed some crash issues
    * Enhanced validation for the BlueStacks emulator
    * Enhanced the security of the engine

* [iOS] 1.2.1
    * Added the NHN AppGuard iOS CLI

* [Console] Changed the allowed search period of the detection log (30 days -> 90 days)

### May 10, 2022

#### Feature Updates
* [Android] 1.9.4.1
    * Improved ANR and crash issues
    * Improved callback data
    * Enhanced the emulator detection function
    * Enhanced the security of the engine

### April 26, 2022

#### Feature Updates
* [Android] 1.9.4.0
    * Removed the version

* [iOS] 1.2.0
    * Enhanced the security related to Unity framework
    * Enhanced the security of the engine

* [Gradle Plugin] 1.0.0
    * Changed the groupId and package name

### March 29, 2022

#### Feature Updates
* [Android] 1.9.3.0
    * Improved DEX encryption
    * Separated the macro tool policy from the cheating tool policy
    * Added a verification function for multiple signatures
    * Improved detection of Mod apps
    * Improved the Unreal SDK

* [iOS] 1.1.10
    * Applied a bug patch for protection operations
    * Improved the re-signing script function
    * Improved a feature related to version checking
    * Modified the guide document

* [Gradle Plugin] 0.2.1
    * Improved APK file search logic
    * Improved the Protector version regular expression

### February 22, 2022

#### Feature Updates
* [Android] 1.9.2.0
    * Enhanced detection of abusing apps
    * Improved protection of large apps
    * Exposed macro tool details
    * Fixed a bug in CLI
    * Fixed a bug in real-time policy detection
    * Fixed an issue where the protection operation fails

* [iOS] 1.1.9
    * Improved a feature related to version checking
    * Modified the guide document

* [Gradle Plugin] 0.2.0
    * Added support for options by Gradle buildTypes, productFlavors, and variants
    * Added the overrideOutputFile option

### January 25, 2022

#### Feature Updates
* [Android] 1.9.1.0
    * Improved handling of isolated processes
    * Enhanced detection of Hacking tools
    * Enhanced detection of tampering

* [iOS] 1.1.8
    * Added a new class obfuscation function
    * Improved the blacklist feature

* [Gradle Plugin] 0.1.0
    * Newly released NHN AppGuard Gradle Plugin

### December 28, 2021

#### Feature Updates
* [Android] 1.9.0.0
    * Modified so that the protection operation is performed by specifying the AppGuard version
    * Enhanced detection of Hacking tools
    * Improved detection of remote control packages
    * Fixed a crash issue with certain emulators

* [iOS] 1.1.7
    * Enhanced the security of the engine

#### Bug Fixes
* [iOS] 1.1.7
    * Applied a bug patch for protector
    * Applied a bug patch for re-signer

### 2021. 12. 02.

#### Bug Fixes
* [Android] 1.8.9.1
    * Fixed a crash issue with the alert window

### November 23, 2021

#### Feature Updates
* [Android] 1.8.9.0
    * Enhanced the security of the engine
    * Deployed the CLI with a new structure

#### Feature Updates
* [iOS] 1.1.6
    * Enhanced the security of the engine
    * Improved the protector feature

### November 4, 2021

#### Bug Fixes
* [iOS] 1.1.5
    * Fixed a bug related to protector app name extraction

### October 26, 2021

#### Feature Updates
* [Android] 1.8.8.0
    * Enhanced the security of the engine
    * Improved the encryption API functionality

### October 8, 2021

#### Bug Fixes
* [Android] 1.8.7.1
    * Fixed an error in the Google Play Asset Delivery support function

### September 28, 2021

#### Feature Updates
* [Android] 1.8.7.0
    * Enhanced the security of the engine
    * Added Google SafetyNet malicious app detection

#### Feature Updates
* [iOS] 1.1.4
    * Enhanced the security of the engine
    * Reinforced protection feature through AppGuard protector

### September 1, 2021

#### Bug Fixes
* [Android] 1.8.6.1
    * Fixed the crash on Unity using SQLite
    * Modified security features of Unreal

### August 24, 2021

#### Feature Updates
* [Android] 1.8.6.0
    * Enhanced the security of the engine
    * Improved security features of Unreal
    * Improved the speed of protection tasks
    * Supports CLI macOS M1
    
### July 27, 2021

#### Feature Updates
* [iOS] 1.1.2
    * Enhanced the security of the engine
    * Project update
    
* Change web console page
    * The app protection operation has been changed to asynchronous.

### July 13, 2021

#### Feature Updates
* [Android] 1.8.5.1
    * Improve the feature for app support that applies Google Play Asset Delivery

### June 29, 2021

#### Feature Updates
* [Android] 1.8.5.0
    * Enhanced the security of the engine
    * Improved the security features of Unity
    * Improved CLI error handling
  
* [iOS] 1.1.1
    * Enhanced the security of the engine
    * Added IAP abusing detection
    * Improved internal test logic
  
### May 25, 2021

#### Feature Updates
* [iOS] 1.1.0
    * Improved the engine performance
    * Improved the stability of the engine

### May 24, 2021

#### Feature Updates
* [Android] 1.8.4.0
    * Enhanced the security of the engine
    * Improved the stability of the engine
    * Improved the crash issue with certain versions of Unity 2020
     
### May 11, 2021

#### Feature Updates
* [Android] 1.8.3.1
	* Added the remote control detecting function
	
### April 27, 2021

#### Feature Updates
* Changed service name (AppGuard -> NHN AppGuard)
* [Android] 1.8.3.0
	* Enhanced the security of NHN AppGuard Engine
* [iOS] 1.0.18
	* Changed handling logic after detecting malicious behaviors
	* Enhanced the security of NHN AppGuard Engine
	* Improved the stability of NHN AppGuard Engine
 
### April 12, 2021

#### Bug Fixes
* [iOS] 1.0.17
    * Added the NHN AppGuard hooking detection logic

### April 9, 2021

#### Bug Fixes
* [Android] 1.8.2.2
	* Fixed the crashing issues in the Cocos2d engine emulator
	
### March 31, 2021

#### Bug Fixes
* [Android] 1.8.2.1
	* Fixed the crashing issues in the Facebook SDK
	
### March 23, 2021

#### Feature Updates
* [Android] 1.8.2.0
	* Enhanced the security of NHN AppGuard Engine
* [iOS] 1.0.16
	* Enhanced the security of NHN AppGuard Engine

### February 23, 2021

#### Feature Updates
* [Android] 1.8.1.0
	* CLI feature improved
	* Improved the stability of NHN AppGuard Engine
	* Enhanced the security of NHN AppGuard Engine
	* Added a virtual environment pattern (F1VM)
* [iOS] 1.0.15
	* Improved the stability of NHN AppGuard Engine

### January 26, 2021

#### Feature Updates
* [Android] 1.8.0.1
	* Third party store support
	* Upgraded detection of game hacks

### December 29, 2020

#### Bug Fixes
* Improved the stability of NHN AppGuard Engine

### August 25, 2020

#### Feature Updates
* [Android] Updated detection of virtual environment
* [iOS] Upgraded detection of jailbreaking
* [iOS] Upgraded detection of game hacks

### July 28, 2020

#### Feature Updates
* [Android] Added detection of virtual environment
* [iOS] Upgraded detection of jailbreaking
* [iOS] Sophisticated forced closure
* [iOS] Added the feature of blocking blacklist

#### Bug Fixes
* [Android] Updated crashes in Unity Mono Emulator version 7
* [iOS] Updated clashes in Gamepot framework

### June 23, 2020

#### Feature Updates
* Updated downsizing NHN AppGuard volume
* Enhanced the security of NHN AppGuard Engine

#### Bug Fixes
* Fixed bugs in unreal engine protection

### May 26, 2020

#### Feature Updates
* Added the obfuscation application

#### Bug Fixes
* Improved the stability of NHN AppGuard Engine

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
* Improved the stability of NHN AppGuard Engine

### December 24, 2019

#### Feature Updates
* Added the Cocos2d-x engine encryption module

### November 26, 2019

#### Feature Updates
* Allows to select NHN AppGuard version

#### Bug Fixes
* Fixed string obfuscation bugs

### October 29, 2019

#### Feature Updates
* Updated the anti-debugging feature
* Updated game hack detection
* Added the memory search detection feature

#### Bug Fixes
* Improved the stability of NHN AppGuard Engine

### September 24, 2019

#### Feature Updates
* Enhanced Stability for NHN AppGuard Android Q

### August 27, 2019

#### Feature Updates
* Supports Android Q
* Added conditional block on web console and blacklisting
* Added real-time policy setting for NHN AppGuard iOS
* Added machine learning-based macro detection for Unity games and web console support
* Updated integrity checks for NHN AppGuard modules
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
* Upgraded NHN AppGuard 64-bit library protection
* Added obfuscation in NHN AppGuard control flow
* Added crash reporting

#### Bug Fixes
* Fixed bugs in the check of authority change of NHN AppGuard path

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
	* Applied with NHN AppGuard level3
* Added emulator detection pattern
	* The latest Memu Player version(6.1.1)

#### Bug Fixes
* Fixed error in duplicate multi-dex installation on Android OS 4.X version

### March 26, 2019

#### Feature Updates
* Applies Unity Library obfuscation
* Added NHN AppGuard API / Method obfuscation function

### February 26, 2019

#### Feature Updates
* Applies NHN AppGuard self-obfuscation
* Upgraded the compatibility for the latest Unity version(2018)
	* Build encryption for MONO and IL2CPP
* Added emulator detection pattern
	* The latest NOX version(6.2.7.0)

### January 29, 2019

#### Feature Updates
* Improved the compatibility for the latest Unity version

### December 27, 2018

#### Feature Updates
* Enhanced NHN AppGuard self-protection
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
* Added the feature of confirming NHN AppGuard application
* Enhanced rooting detection
* Enhanced debugging detection

### August 28, 2018

#### Bug Fixes
* NHN AppGuard Unity SDK
	* Fixed integration bugs for Unity 5 or lower versions

### July 24, 2018

#### Feature Updates
* Supports Unreal Engine 4
	* Supports protection of game codes for Unreal Engine 4

### June 26, 2018

#### Feature Updates
* Upgraded compatibility for Android P(9.0)
* NHN AppGuard Unity SDK
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
* Fixed errors in which apps with NHN AppGuard Level2 were not running properly on the Momo App Player 1.2.1 version

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
* Modified the module (CLIUpdater.exe) that automatically updates the NHN AppGuard CLI(AppGuard.exe), which requires updates
* Requires CLI of latest SDK (if you don't want automatic updates, add --noUpdate as CLI option)

### July 20, 2017

#### Feature Updates
* Fixed an error in which the callback function was not called when detected, on Level 1~3
* Sets volume optimization as an option for Level 1~3

### June 22, 2017

#### Feature Updates
* Includes NHN AppGuard modules for each architecture, when using 64 bit architecture for x86_64 and jni for arm64-v8a.
* Divides SDK download paths for Android from iOS(Beta)
* Free service for iOS (Beta) users
* Enhanced module detection of the NHN AppGuard itself
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
* Fixed some app installation issues when app forgery prevention is applied
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
* [SDK] Newly deployed NHN AppGuard iOS SDK
* Enhanced the app forgery prevention feature

#### Bug Fixes
* Fixed synchronization error between policy settings and detection logic
* Fixed crash issue based on network conditions (updates on log transfer library)

### December 22, 2016

#### Feature Updates
* Added detection pattern of cheating tool
* [Console] Added the NHN AppGuard Engine version information to detection logs

### December 8, 2016

#### Feature Updates
* Added rooting detection pattern
* [SDK] Added multi-lingual setting API at message when blocking in NHN AppGuard

#### Bug Fixes
* [Console] Fixed an error that the protection failed but appears to be successful on the web console

### November 24, 2016

#### Feature Updates

* [SDK] Updated NHN AppGuard SDK(tcag.jar)
* [Console] Added notice on NHN AppGuard Web Console

### October 20, 2016

#### Feature Updates

* [API] Changed parameter for the NHN AppGuard SDK integration feature
* [SDK] Added auto tool updates for NHN AppGuard CLI(Command Line Build)

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
