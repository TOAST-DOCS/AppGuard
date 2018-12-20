## Security > AppGuard > Console Guide

AppGuard有 Android版本和iOS版本(Beta)。

Android版本关联SDK(选项)后所构建的apk文件，通过Web Console或CLI来进行App保护 工作(必选项)。<br>
iOS版本的话，通过关联SDK(必选项)来进行应用，没有额外的保护工作。

AppGuard的使用应用阶段如下。

![[图 1] AppGuard 应用方法](http://static.toastoven.net/prod_appguard/figure1.png)

## 控制面板

App保护工作已完结的App在App Store发布后，若被Abusing用户探知的话，可在 **Dashboard**标签上确认现状。

![appguard_01_201812_zh](https://static.toastoven.net/prod_appguard/[appguard_01_201812_zh.png)

- **Dashboard**可搜索AppGuard探知的Abusing用户的统计图表和清单。
- 可用 [User ID]、 [Device ID]、 [Detection Log Count]、 [Detection Log Pattern]、[Search Period]进行搜索。
    - [User ID]和[Device ID]用逗号来区分，可添加多个条件。
- 检测统计图表可确认“按检测模式分布”和按时间“检测模式量”。
- 检测目录会显示User ID和Device ID、Host IP、 OS、 Logs、App Information、Detection Time。
- 搜索结果，点击**Download Report(CSV)** ， 即可进行下载。

## App保护

### SDK下载及关联

若是激活AppGuard的话，就会看见 **App保护** 菜单。若是选择 **App保护** 菜单的话，就可下载SDK。

下载SDK后，按照附加的说明书中进行关联。
(iOS的话，没有保护阶段，只能关联SDK。)

### App保护菜单

选择 **App保护** 后，点击 **+ Protect App** 按钮的话，就会出现以下页面。

![appguard_02_201812_zh](https://static.toastoven.net/prod_appguard/[appguard_02_201812_zh.png)

- 选择[Certificate](KeyStore文件）。 
- 输入[Master Password]，点击[Validation]按钮，可检查证书文件的有效性。
    - 此检查操作是为了在App保护工作前选择KeyStore的有效性和适当的Alias。
    - 有效性检查失败时，需确认证书文件是否正常和管理员密码。
- 选择[Alias]名。
- 输入[Alias Password]。
- 选择要保护的App。
- 选择保护等级。
    - Level1 : 有关App的非正常行为及模式基础的基本安全检测功能
    - Level2 : Level1 + 代码加密、App防伪等增强的安全功能
    - Level3 : Level2 + 强化的安全功能(在特定服务中，可能会需要检测安全性，只有收到额外的应用指南才建议使用。)
    - Level ex : 关联SDK作为必须需要的版本，提供Level1和2之间的安全性(只有和其它安全解决方案相冲突时，才建议使用。)
- 点击**OK**按钮，保护App。
    - 若保护App结束的话，即可下载被保护的App。现在，将被保护的发布文件上传至各App Store进行发布即可。
- App保护工作手段 Console, CLI(Command Line Interface)

## 策略设置

AppGuard发现恶意破解或者编码造假的时，可以设置阻止政策。

![appguard_03_201812_zh](https://static.toastoven.net/prod_appguard/[appguard_03_201812_zh.png)

用户用Block设置政策来检测的话，AppGuard弹出消息框后停止运行。
有关阻止政策的更多详细信息，请参阅SDK中包含的“AppGuard Devloper's Guide”文档。