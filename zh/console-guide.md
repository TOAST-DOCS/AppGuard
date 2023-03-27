## Security > NHN AppGuard > Console Guide

NHN AppGuard is provided in two versions: Android and iOS.

For Android users, NHN AppGuard is applied when apk files built on SDK integration (optional) go through application protection process (required) on a web console or command line interface(CLI).
For iOS users, it is applied when the application files are created with SDK integration (required) and no further protection process is required.
Unity 버전은 Android/iOS 앱을 손쉽게 보호할 수 있는 편의 기능을 제공합니다.

Following diagram shows the NHN AppGuard application process.

![[Figure 1] How to apply NHN AppGuard](http://static.toastoven.net/prod_appguard/AppGuard_3_overview01.png)

## Dashboard

When an abusive user is detected, you can check detection status by clicking on the **Dashboard** tab.

![appguard_01_202104](http://image.toast.com/aaaaaha/console-guide/1_1_%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C_en.png)

- **Status of abnormal behavior** can be found among abusive users as detected by NHN AppGuard in the order of trials by **log detection pattern** or **period**.
- Click **Download Reports (Excel)** on top-right of the page to download the detection result of abnormal behavior.
- **Dashboard** tab shows statistical graphs and the list of abusive users detected by NHN AppGuard.
    - For rooting, you may check detection or sanction logs on dashboard, once a day since app is installed.
- You can **Search** by [User ID], [Device ID], [Detection Log Count], [Log Pattern], and [Search Period].
    - Multiple [User ID] and [Device ID] can be added with comma as a delimiter.
- In the statistical detection graph, you can check 'Detection Distribution by Pattern' and 'Change status of detection logs'.
- The detection list shows User ID, Device ID, Host IP, OS, Logs, App Information, and Detection Time.
- You may click **Download Report (Excel)** to download the query result.

## App Protection

### Download and Integrate SDKs

Select **App Protection** and click **Download SDK** to download SDK by OS.

Then, follow the attached manual to work with SDKs.
(In case of iOS, no further steps are required once the application is integrated with the SDK).

### App Protection Menu

Select **App Protection** and click **\+ Protect App**.

![appguard_02_202104](http://image.toast.com/aaaaaha/console-guide/2_1_%EC%95%B1%EB%B3%B4%ED%98%B8_en.png)

* Choose a [Certificate] KeyStore file.
* Enter [Master Password] and Click [Validation] to check validation of the chosen file.
    - This process is required to validate KeyStore and to choose an appropriate Alias.
    - When validation fails, be sure to check the status of the certificate file and the master password.
* Select the name of [Alias].
* Enter [Alias Password].
* Choose an [APK]
* Select the level of protection
    - Level1 : Basic level of pattern-oriented and abnormal acts protection on application
    - Level2 : Level1 + Advanced security functions such as, code encryption and preventing app manipulation (Recommended for general apps)
    - Level3 : Level2 + Fortified security functions (Recommended for game apps)
* Select [Release Versions]
* Click **Ok** to start Protect App
    - When completed, you can download the protected application. Now, you're ready to upload protected apps on each Appstore for deployment.
* Methods of app protection: Console or CLI(Command Line Interface)

## Policy

Blocking policy can be set for tampering trials of code, memory or speed, while NHN AppGuard is running, and blocking conditions can set for 'Block by Condition' based on threshold.

![appguard_03_202104](http://image.toast.com/aaaaaha/console-guide/3_1_%EC%A0%95%EC%B1%85_en.png)

When it is detected by policy set as 'Block All', guide for NHN AppGuard shows and app is closed.
When it is detected by conditions set as 'Block by Condition', guide for NHN AppGuard shows and app is closed.
For further details on the policy, please refer to "NHN AppGuard Developer's Guide" document included in the SDK.

### Change History

History can be managed, regarding by who and when policy was changed and saved.

![appguard_04_202104](http://image.toast.com/aaaaaha/console-guide/3_2_%EC%A0%95%EC%B1%85%20%EB%B3%80%EA%B2%BD%EC%9D%B4%EB%A0%A5_en.png)

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

* Modify **Cause of Registration** and **Blocking Period (day)**.
* Click **Register** to register the updated blacklist.
* Execute the app with re-registered blacklist ID and guide for NHN AppGuard shows during specified blocking period and app is closed.