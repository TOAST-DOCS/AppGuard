## Security > AppGuard > Console Guide

AppGuard is provided in two versions: Android and iOS(Beta).

For Android users, AppGuard is applied when apk files built on SDK integration (optional) go through application protection process (required) on a web console or command line interface(CLI).
For iOS users, it is applied when apk files are created with SDK integration (required) and no further protection process is needed.

Apply step for using AppGuard are shown in [Figure 1].

![[Figure 1] How to apply AppGuard](http://static.toastoven.net/prod_appguard/figure1.png)
<center>[Figure 1] How to apply AppGuard</center>

## Enable Service

To enable AppGuard products, select [Security] > [AppGuard] on the Toast Cloud [Console] page, as Figure 2 shows, and click on [Product Using].

![[Figure 2] How to Enable AppGuard](http://static.toastoven.net/prod_appguard/figure2_new.png)
<center>[Figure 2] How to Enable AppGuard</center>

Then, the enabled AppGuard product is made available with the reference guide on [Product Using] in the upper side of the web console.

AppGuard collects and stores device IDs and IPs, etc. to provide log data on abuses.

For more information about AppGuard, see 'Guide on Personal Information Protection' released on [Product Using].

Visit AppGuard Pricing ([http://cloud.toast.com/pricing/security](http://cloud.toast.com/pricing/security)) to learn more about pricing.

## Protect App

### Download and Integrate SDKs

When AppGuard is enabled, the [Dashboard] and [App Setting/Protection] menus are made available. Select [App Setting/Protection] and click on [Download SDK] to download SDKs for each OS. Then, follow the attached manual to work with SDKs.

### Select App Protect Menu

Select [App Setting/Protection] and click on the [Protect App] button, and [Figure 3] will pop up (in the case of iOS, it works only by SDK integration, without any protection process required).

![[Figure 3] Input item for app protection setting](http://static.toastoven.net/prod_appguard/figure4.png)
<center>[Figure 3] Input item for app protection setting</center>

* Choose a [Certificate] file. For Android, use a Keystore file.
* Enter [Master Password] and Click [Validation] to check validation of the chosen file.
	* This process is required to validate KeyStore and to choose an appropriate Alias.
	* When validation fails, be sure to check the status of the certificate file and the master password.
* Choose a name of [Alias].
* Enter [Alias Password].
* Choose an [APK]
* Select the level of protection
	- Level1 : Basic level of pattern-oriented and abnormal acts protection on application
	- Level2 : Level1 + Advanced security functions such as, code encryption and preventing app manipulation
	- Level3 : Level2 + Fortified security functions (recommended only when additional deployment guide is given, because some services might require verification process on the stability)
	- Level ex : This level requires SDK integration, which provides security between Level 1 and Level 2 (recommended only when there's a conflict with other security solutions)

* Click [Ok] to start Protect App
	\- when completed, select [App Setting/Protection] tab on [Figure 4] to download the protected application. Now, you're ready to upload the protected files to each Appstore for deployment.

![[Figure 4] App Setting/Protect window](http://static.toastoven.net/prod_appguard/figure5.png)
<center>[Figure 4] App Setting/Protect window</center>

*	Methods of app protection: Console or CLI(Command Line Interface)

## Dashboard

1. When an abusive user is detected, you can check the status by clicking on the [Dashboard] tab, as [Figure 6] shows.
2. [Dashboard] shows statistical graphs and the list of abusive users detected by AppGuard.
3. You can [Search] by [User ID], [Device ID], [Detection Log Count], [Log Pattern], and [Search Period].
	* For [User ID] and [Device ID], many conditions can be added, by comma.
4. In the statistical detection graph, you can check 'Detection Distribution by Pattern' and 'Detection Pattern Volume by Period'.
5. The detection list shows [User ID], [Device ID], [Detection Log Pattern Information], [Detection Log Count], [App version] and [Detection Time]
6. You may click on the [Download Report (CSV)] to see the results.

![[Figure 5] Dashboard Screen](http://static.toastoven.net/prod_appguard/figure6.png)
<center>[Figure 5] Dashboard Screen</center>
