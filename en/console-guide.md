## Security > AppGuard > Console Guide

AppGuard is provided in two versions: Android and iOS(Beta).

For Android users, AppGuard is applied when apk files built on SDK integration (optional) go through application protection process (required) on a web console or command line interface(CLI).
For iOS users, it is applied when the application files are created with SDK integration (required) and no further protection process is required.

Following diagram shows the AppGuard application process.

![[Figure 1] How to apply AppGuard](http://static.toastoven.net/prod_appguard/figure1.png)

## Dashboard
When an abusive user is detected, you can check detection status by clicking on the **Dashboard** tab.

![appguard_01_201812_en](https://static.toastoven.net/prod_appguard/appguard_01_201812_en.png)

- **Dashboard** tab shows statistical graphs and the list of abusive users detected by AppGuard.
- You can **Search** by [User ID], [Device ID], [Detection Log Count], [Log Pattern], and [Search Period].
	- Multiple [User ID] and [Device ID] can be added with comma as a delimiter.
- In the statistical detection graph, you can check 'Detection Distribution by Pattern' and 'Detection Pattern Volume by Period'.
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
	- Level2 : Level1 + Advanced security functions such as, code encryption and preventing app manipulation
	- Level3 : Level2 + Fortified security functions (recommended only when additional deployment guide is given, because some services might require verification process on stability)
	- Level ex : This level requires SDK integration, which provides security between Level 1 and Level 2 (recommended only when there's a conflict with other security solutions
- Click **Ok** to start Protect App
    - When completed, you can download the protected application. Now, you're ready to upload protected apps on each Appstore for deployment.
- Methods of app protection: Console or CLI(Command Line Interface)

## Policy Setting

When AppGuard detects manipulation or malicious hacks, it can set block policies.

![appguard_03_201812_en](https://static.toastoven.net/prod_appguard/appguard_03_201812_en.png)

When a user is detected by the block policy, an AppGuard message box pops up and the app is force-closed.
For further details on the policy, please refer to "AppGuard Developer's Guide" document included in the SDK.