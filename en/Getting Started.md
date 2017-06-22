## Security > AppGuard > Getting Started

Appguard is available in Android and iOS verions.

The Android version is applied to the apk file built after the SDK connection(optional) by applying the appliction protection operation(mandatory) through Web Console or CLI.
The iOS version is applied through SDK connectionn(mandatory), and there is no additional protection operation.

Apply step for using AppGuard are shown in [Figure 1].

![[Figure 1] How to apply AppGuard](http://static.toastoven.net/prod_appguard/picture1.png)
<center>[Figure 1] How to apply AppGuard</center>

## Activate Service

To protect your app with AppGuard, first activate the service. To activate, select [Security] > [AppGuard] and click the [Use Product] button in the Console as shown in [Figure 2]

![[Figure 2] Activate AppGuard](http://static.toastoven.net/toastcloud/static/common/img/cms_img/werebeta/img_08.jpg)
<center>[Figure 2] Activate AppGuard</center>

When you first access the AppGuard Console page after clicking the [Use Product] button, the selection window of the Terms of Use appears as shown in [Figure 3] below.

Refer to the Terms of Use and select the pricing policy, so AppGuard is available according to the set pricing policy.

please see AppGuard pricing policy ([http://cloud.toast.com/pricing/security](http://cloud.toast.com/pricing/security)) for details.

![[Figure 3] Selection of  AppGuard pricing policy](http://static.toastoven.net/prod_appguard/terms.jpg)
<center>[그림 3] Selection of AppGuard pricing policy</center>

If you activate AppGuard after select Terms of Use, you can download an SDK that can be connected to the app from the [App Protection] menu.

How to use the SDK connection can be checked in the manual included in SDK after download the SDK

## Protect App

### Download SDK and Connection

When you activate AppGuard, you will see the [Dashboard/App Protect] menu. You can download the SDK by selecting [App Protection] menu.

After download SDK, follow the attached manual.

### Select App Protect Menu

After selecting [App Setting/Protect] menu, click [Protect App] button and the screen of [Figure 4] will appear. (For iOS, it works only with SDK connection without protection phase)

![[Figure 4] Input item for app protection setting](http://static.toastoven.net/prod_appguard/picture4.png)
<center>[Figure 4] Input item for app protection setting</center>

* Select [Certificate file]. It is KeyStore file on Android.
* Enter [Master Password] and Click [Validation] Button to validate the certificate file.
	* This check is to validate KeyStore and to select proper alias before protecting the app.
	* If the validation fails, check whether the certificate file is OK and the master password.
* Select [Alias].
* Enter the [Alias Password].
* Select the [App to protect]
* Select protection level
	- Level1 : Abnormal behavior and Pattern based basic security behavior detect function about app
	- Level2 : Level1 + Improved security function (Encrypt code, Prevent to modify App, etc)
	- Level3 : Level2 + More improve security function (Because stability check may be required for certain services, it is recommended to use it only if you have received a separate guide)
	- Level ex : Must required SDK connection and Provide security between level1 to level2(It is recommended when conflict other security solution)

* Click [Protect App] button to protect app
	\- Once the app is protected, you can download the protected app by selecting the [App Setting / Protect] tap in [Figure 5]. Now you can deploy protected app to upload each app store.

![[그림 5] App Setting/Protect window](http://static.toastoven.net/prod_appguard/picture5.png)
<center>[그림 5] App Setting/Protect window</center>

* App Protect Operation Method: Console, CLI(Command Line Interface)

## Dashboard

1. App is deployed to the App Store after the app has been protected, and if Abusing user is detected, you can check status on the [Dashboard] tab in [Figure 6].
2. [Dashboard] allows you to search statistic graphs and lists of detected user by AppGuard.
3. You can search by [User ID], [Device ID], [Detection Log Count], [Detection Log Pattern], [Search Period]
	* You can add multiple [User ID] and [Device ID] by separating with comma.
4. The detection statistics graph can check 'distribution byyy detection pattern' and 'detection pattern coutn' by period
5. The detection list show [User ID], [Device ID], [Detection Log Pattern Information], [Detection Log Count], [App version] and [Detection Time]
6. The search results can be downloaded by clicking [Download Report(CSV)].

![[Figure 6] Dashboard Windows of Abusing User Detection](http://static.toastoven.net/prod_appguard/dashboard.jpg)
<center>[Figure 6] Dashboard Windows of Abusing User Detection</center>
