## Security > AppGuard > Console Guide

AppGuard is provided in two versions: Android and iOS(Beta).

For Android users, AppGuard is applied when apk files built on SDK integration (optional) go through application protection process (required) on a web console or command line interface(CLI).
For iOS users, it is applied when the application files are created with SDK integration (required) and no further protection process is required.

Following diagram shows the AppGuard application process.

![[Figure 1] How to apply AppGuard](http://static.toastoven.net/prod_appguard/figure1.png)

## Dashboard
When an abusive user is detected, you can check detection status by clicking on the **Dashboard** tab.

![appguard_01_201812_en](https://static.toastoven.net/prod_appguard/appguard_01_201812_en.png)

- **Status of abnormal behavior** can be found among abusive users as detected by AppGuard in the order of trials by **log detection pattern** or **period**.
- Click **Download Reports (CSV)** on top-right of the page to download the detection result of abnormal behavior.  
- **Dashboard** tab shows statistical graphs and the list of abusive users detected by AppGuard.
	- For rooting, you may check detection or sanction logs on dashboard, once a day since app is installed.
- You can **Search** by [User ID], [Device ID], [Detection Log Count], [Log Pattern], and [Search Period].
	- Multiple [User ID] and [Device ID] can be added with comma as a delimiter.
- In the statistical detection graph, you can check 'Detection Distribution by Pattern' and 'Change status of detection logs'.
- The detection list shows User ID, Device ID, Host IP, OS, Logs, App Information, and Detection Time.
- You may click **Download Report (CSV)** to download the query result.

## App Protection

### Download and Integrate SDKs

Select **App Protection** and click **Download SDK** to download SDK by OS.

Then, follow the attached manual to work with SDKs.
(In case of iOS, no further steps are required once the applicaiton is integrated with the SDK).

### App Protection Menu

Select **App Protection** and click **+ Protect App**.

![appguard_02_201812_en](https://static.toastoven.net/prod_appguard/appguard_02_201812_en.png)

- Choose a [Certificate] KeyStore file.
- Enter [Master Password] and Click [Validation] to check validation of the chosen file.
	- This process is required to validate KeyStore and to choose an appropriate Alias.
	- When validation fails, be sure to check the status of the certificate file and the master password.
- Select the name of [Alias].
- Enter [Alias Password].
- Choose an [APK]
- Select the level of protection
	- Level1 : Basic level of pattern-oriented and abnormal acts protection on application
	- Level2 : Level1 + Advanced security functions such as, code encryption and preventing app manipulation (Recommended for general apps)
	- Level3 : Level2 + Fortified security functions (Recommended for game apps)
	- Level ex : This level requires SDK integration, which provides security between Level 1 and Level 2 (recommended only when there's a conflict with other security solutions)
- Click **Ok** to start Protect App
    - When completed, you can download the protected application. Now, you're ready to upload protected apps on each Appstore for deployment.
- Methods of app protection: Console or CLI(Command Line Interface)

## Policy

Blocking policy can be set for tampering trials of code, memory or speed, while AppGuard is running, and blocking conditions can set for 'Block by Condition' based on threshold.

![appguard_03_201908](https://static.toastoven.net/prod_appguard/appguard_03_201908.png)

When it is detected by policy set as 'Block All', guide for AppGuard shows and app is closed.
When it is detected by conditions set as 'Block by Condition', guide for AppGuard shows and app is closed.
For further details on the policy, please refer to "AppGuard Developer's Guide" document included in the SDK.

### Change History

History can be managed, regarding by who and when policy was changed and saved.

![appguard_04_201908](https://static.toastoven.net/prod_appguard/appguard_04_201908.png)

### Add Conditions

Select **Policy** and click **Block by Condition** by each detection type, and the page shows as follows:

![appguard_05_201908](https://static.toastoven.net/prod_appguard/appguard_05_201908.png)
* Select **Blocking Criteria**.
* Select **Country Information**.
* Enter **Number of Detections**.
    - For rooting, detection is set one-time.
* Select a **Blocking Period (day)**.
* Click **Add** to add more conditions.
* While **Block by Condition** is enabled, click **Save** to apply the conditions.
    - Conditions are applied based on detection logs accumulated on the previous day, and it takes up to 10 minutes to apply initially.
    - Conditions are newly applied upon detection logs accumulated on the previous day, as of 05 of 00 every day.

### Check Conditions

![appguard_06_201908](https://static.toastoven.net/prod_appguard/appguard_06_201908.png)

* Click ▼ next to **Block by Condition** and check added conditions.

## Blacklist

By registering user IDs for the integration of device ID and SDK as provided by AppGuard, particular devices and users can be managed under blacklist.

![appguard_07_201908](https://static.toastoven.net/prod_appguard/appguard_07_201908.png)

### Blacklist

Select **Blacklist** and click **Register**, and the page shows as follows:

![appguard_08_201908](https://static.toastoven.net/prod_appguard/appguard_08_201908.png)

* Select **Registration ID**.
* Select **ID Type**.
* Enter **Cause of Registration**.
* Select **Blocking Period (day)**.
* Click **Register** to register it on the Blacklist.
* Execute the app with registered blacklist ID and guide for AppGuard shows during specified blocking period and app is closed.  

### Un-blacklist

Select **Blacklist** and click **Un-blacklist** from the registered list, and the page shows as follows:

![appguard_09_201908](https://static.toastoven.net/prod_appguard/appguard_09_201908.png)

* Click **Un-blacklist** to release from the registered blacklist.
* Execute the app with **un-blacklisted** ID and app is not closed by AppGuard.

### Re-blacklist

Select **Blacklist** and click **Re-blacklist** for a blacklist which has been unblacklisted, and the page shows as follows:

![appguard_10_201908](https://static.toastoven.net/prod_appguard/appguard_10_201908.png)

* Modify **Cause of Registration** and **Blocking Period (day)**.
* Click **Register** to register the upadated blacklist.
* Execute the app with re-registered blacklist ID and guide for AppGuard shows during specified blocking period and app is closed.

## Setting

You may also leave change history by setting, from the web console policy menu of AppGuard.

![appguard_11_201908](https://static.toastoven.net/prod_appguard/appguard_11_201908.png)
