## Security > NHN AppGuard > Console Guide

NHN AppGuard supports Android, iOS, and Unity environments.

### Android

* You can apply the AppGuard Android SDK to use even more enhanced features (optional).
* You can protect apk or aab files built in Android Studio, etc. more conveniently through the web console or CLI (required).

### iOS

* You can apply the AppGuard iOS SDK to protect your app (required).
* You can protect your app more conveniently through the web console or CLI from ipa files built in Xcode (optional).
* If you don't protect your app through the web console or CLI, it runs on the Business plan.
* You must perform protection using the web console or CLI to enable features such as integrity verification, signer verification, default policy, obfuscation, and plan selection.
    * This protection does not incur additional cost.

> [Caution]
> If you need to set up a plan other than the Business plan or change plans, you must perform app protection using the web console or CLI. If you do not want to do app protection, request a consultation to proceed.

### Unity

* You can easily protect Android/iOS apps through provided features.
* The Unity SDK includes an Android SDK and an iOS SDK and can be applied through a single interface.

Following diagram shows the NHN AppGuard application process.

![[Figure 1] How to apply NHN AppGuard](http://static.toastoven.net/prod_appguard/AppGuard_3_overview01.png)

## Dashboard

When an abusive user is detected, you can check detection status by clicking on the **Dashboard** tab.

![appguard_01_202104](http://image.toast.com/aaaaaha/console-guide/1_1_%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C_en_240329.png)

- **Status of abnormal behavior** can be found among abusive users as detected by NHN AppGuard in the order of trials by **log detection pattern** or **period**.
- Click **Download Reports (Excel)** on top-right of the page to download the detection result of abnormal behavior.
- **Dashboard** tab shows statistical graphs and the list of abusive users detected by NHN AppGuard.
    - For rooting, you may check detection or sanction logs on dashboard, once a day since app is installed.
- You can **Search** by [User ID], [Device ID], [Detection Log Count], [Log Pattern], and [Search Period].
    - Multiple [User ID] and [Device ID] can be added with comma as a delimiter.
- In the statistical detection graph, you can check **Detection Distribution by Pattern** and **Change status of detection logs**.
- The **Abnormal behavior detection status** can also be retrieved in json format through APIs. For more information, see the [API guide](https://docs.nhncloud.com/en/Security/NHN%20AppGuard/en/api-guide/).

## App Protection

### Download and Integrate SDKs

Select **App Protection** and click **Download SDK** to download SDK by OS.

Then, follow the attached manual to work with SDKs.

### Apply to Enable Obfuscation

You can apply for code obfuscation for Android OS by selecting **App Protection** and **Enable Obfuscation**.
Code obfuscation for Android OS requires an additional fee of KRW 1 million per month.
For iOS, you can choose whether or not to use code obfuscation when protecting your app, and there is no additional charge.

### App Protection Menu

Select **App Protection** and click **+ Protect App**.

![appguard_02_202104](http://image.toast.com/aaaaaha/console-guide/2_1_%EC%95%B1%EB%B3%B4%ED%98%B8_en_240329.png)

* Choose a [Certificate] KeyStore file.
* Enter [Master Password] and Click [Validation] to check validation of the chosen file.
    - This process is required to validate KeyStore and to choose an appropriate Alias.
    - When validation fails, be sure to check the status of the certificate file and the master password.
* Select the name of [Alias].
* Enter [Alias Password].
* Choose an [APK]
* Select [Plan].
    - Business: Basic level of pattern-oriented and abnormal acts protection on application
    - Enterprise: Business + Dynamic analysis defenses, including Zava code (DEX) encryption + memory manipulation detection (recommended for general apps)
    - Game: Enterprise + Game engine library static protection + Enhanced dynamic analysis defense security features, including Unity IL2CPP code analysis defense (recommended for game apps)
    - See the [AppGuard Service Guide](https://www.nhncloud.com/kr/service/security/nhn-appguard) for a complete list of features available with each plan.
* Select [Release Versions]
* Click **Ok** to start Protect App
    - When completed, you can download the protected application. Now, you're ready to upload protected apps on each Appstore for deployment.
* Methods of app protection: Console or CLI(Command Line Interface)

## Policy

Blocking policy can be set for tampering trials of code, memory or speed, while NHN AppGuard is running, and blocking conditions can set for 'Block by Condition' based on threshold.

![appguard_03_202104](http://image.toast.com/aaaaaha/console-guide/3_1_%EC%A0%95%EC%B1%85_en.png)

When it is detected by policy set as **Block All**, guide for NHN AppGuard shows and the app is closed.
When the  conditions  set in **Block by Condition** are met, the user is blacklisted, and if the user launches the app, the NHN AppGuard guide window appears and the app is ended.

For further details on the policy, please refer to "NHN AppGuard Developer's Guide" document included in the SDK.

### Introduction to Block Features
- **NHN AppGuard** > **Policy** > **Block All**
    - If set to **Block All**in the NHN AppGuard Policy screen, the app will be ended as soon as the behavior is detected.
    - Even if the app is shut down due to a policy, you can use the app normally if you relaunch the app without any abnormal behavior.
    - If you change the policy to Block All or Detect, it will be applied to the app that has restarted after about a minute.
- **NHN AppGuard** > **Policies** > **Individual Block**
    - Only emulators and macro tools can be blocked per individual tool, not all types.
    - When set to block in the individual block, the app will be ended upon detection, just like a full block.
    - The policy is applied to apps that restart approximately one minute after saving the policy.
- **NHN AppGuard** > **Policy** > **Block by Condition**
    - If you set it to **Block by Condition**on the NHN AppGuard policy screen, it will blacklist users who meet the condition at 00:00 every day.
    - Whether the conditions are met is determined based on detection logs that occurred between 00:00:00 and 23:59:59 in the last day, and each condition works independently by type.
    - You can check the blacklist registered as conditional blocking on the NHN AppGuard Blacklist tab.
    - Users blocked due to blacklisting registered as conditional blocking are not exposed to the NHN AppGuard dashboard tab.
    - Users blacklisted with conditional blocking will not be able to use the app for the block period you set, even if they launch the app without any abnormal behavior.
    - If you change a setting or condition with conditional blocking, it will take effect for all users after about 10 minutes.
- Block through **NHN AppGuard** > **Blacklist**
    - If you blacklist a user on the NHN AppGuard Blacklist screen and the user launches an app, the app will be ended.
    - It takes effect when the app is re-launched, starting immediately after blacklisting.

### Change History

History can be managed, regarding by who and when policy was changed and saved.

![appguard_04_202104](http://image.toast.com/aaaaaha/console-guide/3_2_%EC%A0%95%EC%B1%85%20%EB%B3%80%EA%B2%BD%EC%9D%B4%EB%A0%A5_en.png)

### Individual Block

Only emulators and macro tools can be blocked per individual tool, not all types.

- You can **disable**, **detect**, and **block** an individual tool.
- **Default Policies**allow you to set policies for unidentified types.

### Add Conditions

Select **Policy** and click **Block by Condition** by each detection type, and the page shows as follows:

![appguard_05_202104](http://image.toast.com/aaaaaha/console-guide/3_3_%EC%A0%95%EC%B1%85%20%EC%A1%B0%EA%B1%B4%EC%B6%94%EA%B0%80_en.png)

* Select **Blocking Criteria**.
* Select **Country Information**.
* Enter **Number of Detections**.
    - For rooting, detection is set one-time.
* Select **Blocking Period (day)**.
* Click **Add** to add more conditions.
* While **Block by Condition** is enabled, click **Save** to apply the conditions.
    - Conditions are applied based on detection logs accumulated on the previous day, and it takes up to 10 minutes to apply initially.
    - Conditions are newly applied upon detection logs accumulated on the previous day, as of 05 of 00 every day.

### Check Conditions

![appguard_06_202104](http://image.toast.com/aaaaaha/console-guide/3_4_%EC%A0%95%EC%B1%85%20%EC%A1%B0%EA%B1%B4%ED%99%95%EC%9D%B8_en.png)

* Click ▼ next to **Block by Condition** and check added conditions.

## Blacklist

By registering user IDs for the integration of device ID and SDK as provided by NHN AppGuard, particular devices and users can be managed under blacklist.

![appguard_07_202104](http://image.toast.com/aaaaaha/console-guide/4_1_%EB%B8%94%EB%9E%99%EB%A6%AC%EC%8A%A4%ED%8A%B8_en.png)

### Blacklist

Select **Blacklist** and click **Register**, and the page shows as follows:

![appguard_08_202104](http://image.toast.com/aaaaaha/console-guide/4_2_%EB%B8%94%EB%9E%99%EB%A6%AC%EC%8A%A4%ED%8A%B8%20%EB%93%B1%EB%A1%9D_en.png)

* Select **Registration ID**.
* Select **ID Type**.
* Enter **Cause of Registration**.
* Select **Blocking Period (day)**.
* Click **Register** to register it on the Blacklist.
* Execute the app with registered blacklist ID and guide for NHN AppGuard shows during specified blocking period and app is closed.

### Un-blacklist

Select **Blacklist** and click **UnBlock** from the registered list, and the page shows as follows:

![appguard_09_202104](http://image.toast.com/aaaaaha/console-guide/4_3_%EB%B8%94%EB%9E%99%EB%A6%AC%EC%8A%A4%ED%8A%B8%20%ED%95%B4%EC%A0%9C_en.png)

* Click **UnBlock** to release from the registered blacklist.
* Execute the app with unblacklisted ID and app is not closed by NHN AppGuard.

### Re-blacklist

Select **Blacklist** and click **Re-blacklist** for a blacklist which has been unblacklisted, and the page shows as follows:

![appguard_10_202104](http://image.toast.com/aaaaaha/console-guide/4_4_%EB%B8%94%EB%9E%99%EB%A6%AC%EC%8A%A4%ED%8A%B8%20%EC%9E%AC%EB%93%B1%EB%A1%9D_en.png)

* Modify **Cause of Registration** and <strong>Blocking Period (day)</strong>.
* Click **Register** to register the updated blacklist.
* Execute the app with re-registered blacklist ID and guide for NHN AppGuard shows during specified blocking period and app is closed.

## Log Search

You can view the details of the detected logs on the **Log Search** tab.
![appguard_11](http://image.toast.com/aaaaaha/console-guide/5_1_%EB%A1%9C%EA%B7%B8%EC%A1%B0%ED%9A%8C_en_240329.png)

- You can search by **User ID**, Device ID, Detection Log Count, Log Pattern, and Search Period.
    - Multiple **User ID** and **Device ID** can be added with comma as a delimiter.
- User ID, Device ID, Host IP, OS, Logs, App Information, and Detection Time appear.
- You can download the search results by clicking <strong>Download Report (Excel</strong>).

## Settings

### Set Alarms

You can receive an alarm on the channel you set when the number of detection/block logs exceed a threshold.

- Set Thresholds
  - Alarms are sent when the number of detections+blocks that occurred today exceeds a **threshold** based on the **median value** of detections+blocks that occurred during the comparison period.
    - The median value is used to reduce the impact of cases where the number of logs increased dramatically due to abnormal behaviors, such as an attack within the comparison period. 
  - **The threshold** can be set from 10 to 10000%.
  - For example, if the number of logs over 7 days is [5,5,5,5,5,7,7,7] and the threshold you set is 100%, alarms are sent if the number of logs today is 5 or more. 
- Set Alarm Receiving Channel
  - You can enter up to five emails to receive alarms.
  - You can enter multiple emails, separated by commas (,).
  - You can only add or delete emails. You can't edit emails.
- Alarms are sent within 10 minutes of the threshold being exceeded.
- If you received an alarm, access the console to view the detection log.

> [Note] <br>
> * Alarms are sent up to once per day.