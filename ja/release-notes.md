<!-- pre-align:aligned sig=877ccc77b25f -->

<a id="security-nhn-appguard-release-notes"></a>
## Security > NHN AppGuard > リリースノート { #security-nhn-appguard-release-notes }

| Platform | Version  | Release Date | Status |
| -------- | -------- | -----------  | ------ |
| Android  | 1.13.3.1 | 2026. 07. 14.  | latest |
| Android  | 1.12.4.18 | 2026. 03. 10.  | stable |
| iOS      | 1.5.5    | 2026. 07. 14.  | latest |

<a id="july-28-2026"></a>
### 2026. 07. 28. { #july-28-2026 }
* [Gradle Plugin] 1.3.0
    * Android Gradle Plugin(AGP) 9.xをサポート

<a id="july-14-2026"></a>
### 2026. 07. 14. { #july-14-2026 }
* [Android] 1.13.3.1
    * 断続的に発生するクラッシュ問題を修正
* [iOS] 1.5.5
    * Unityアプリ証明をサポート
* [Unity] 0.5.0
    * アプリ証明機能を追加
    * iOS SDK 1.5.5アップデート
* [Unreal] 0.2.9
    * iOS SDK 1.5.5アップデート

<a id="june-23-2026"></a>
### 2026. 06. 23. { #june-23-2026 }
* 共通
    * 「整合性認証」機能の名称を「アプリ証明」に変更
        * SDKインターフェースがアプリ証明(App Attestation)の名称に合わせて変更されました。
        * CLIオプションが`--integrity`から`--app-attestation`に変更されました。
* [Android] 1.13.3.0
    * ネイティブライブラリ(.so)の整合性検証を有効化
        * Google Playの自動整合性保護の適用時に誤検知が発生する問題を修正しました。
    * アプリ証明の改善
        * ネイティブライブラリ(.so)の検証機能を追加しました。
        * アプリ証明機能の最小サポートバージョンがAndroid 1.13.3.0、SDK 0.5.0に変更されました。
    * Java難読化の改善
        * エスケープ文字列の処理時に発生していた難読化エラーを修正しました。
        * ランタイム環境で特定のクラスに対してVerifyErrorが発生する問題を修正しました。
        * 保護処理の実行時に難読化検証ステップを追加しました。
            * CLIで`--verify-obfuscated-dex`オプションを追加すると検証が有効になります。
    * 不具合の修正
        * Android 5.1(32bit)エミュレータでクラッシュが発生する問題を修正しました。
* [iOS] 1.5.4
    * アプリ証明の名称変更事項を適用
    * セキュリティ強化
    * ライブラリ改ざん検知の改善
        * 一部の旧バージョンのiOSでライブラリの改ざんが検知されない問題を修正しました。
    * 保護処理のパフォーマンス改善
* [Unity] 0.4.30
    * iOS SDK 1.5.4アップデート
* [Unreal] 0.2.8
    * iOS SDK 1.5.4アップデート
* [Console]
    * 用語変更: 整合性検証 → アプリ証明
    * アプリ証明機能の追加
        * ABI別のハッシュ管理機能を追加
        * 検証モード自動切り替え機能を追加
    * ブラックリストのブロック理由が誤って表示されるバグを修正
* [Native Code Obfuscator] 1.1.0
    * 機能改善
        * 文字列エンコーディングの設定方法を簡素化しました。
        * NDKツールチェーンのインストール方法を変更しました。

<a id="june-11-2026"></a>
### 2026. 06. 11. { #june-11-2026 }
* [iOS] 1.5.3
    * AppGuard SDK v1.5.2保護後、ストア配布時の改ざん誤検知を修正
* [Unity] 0.4.29
    * iOS SDK 1.5.3 アップデート
* [Unreal] 0.2.7
    * iOS SDK 1.5.3 アップデート

<a id="may-19-2026"></a>
### 2026. 05. 19. { #may-19-2026 }
* [Android] 1.13.2.1
    * 本バージョンには、使用中止となった1.13.0.0、1.13.1.0、1.13.2.0バージョンの変更事項が含まれています。
    * 特定の環境でNHN AppGuardエンジンのロード失敗によりクラッシュが発生する問題を修正
    * ネイティブライブラリ(.so)の整合性検証を無効化
	
<a id="may-12-2026"></a>
### 2026. 05. 12. { #may-12-2026 }
* [Android] 1.13.2.0 **(使用中止を推奨)**
    * 整合性認証の改善
        * 署名検証の対象をライブラリSplit APKまで拡張しました。
    * ネイティブライブラリの改ざん検知機能を追加
        * ネイティブライブラリ(.so)の整合性を検証し、改ざんされた場合にこれを検知する機能を追加しました。
    * KernelSU root化検知機能を追加
        * KernelSUベースのroot化デバイスを検知できるように機能を追加しました。
    * 遠隔操作検知の改善
        * 遠隔操作の検知方式を、従来のアプリインストールの有無を基準とする方式から、実際の実行の有無を基準とする方式に改善しました。
    * 一部のエミュレータで発生する改ざんの誤検知問題を修正
    * Android 6(API 23)デバイスでアプリが異常終了する問題を修正
    * Androidの最小サポートバージョンの引き上げ
        * Androidの最小サポートバージョンをAndroid 5.0(API Level 21)からAndroid 5.1(API Level 22)へ引き上げました。
* [iOS] 1.5.2
    * デバッグ環境検知の改善
        * frida attachの検知を改善しました。
    * 改ざん検知の改善
        * アプリバンドル内の動的ライブラリ(framework、dylib)の改ざん検知機能を追加しました。
            * Enterpriseプラン以上から適用可能です。
* [Unity] 0.4.28
    * (iOS) iOS SDK 1.5.2アップデート
* [Unreal] 0.2.6
    * (iOS) iOS SDK 1.5.2アップデート
* [Console]
    * 整合性認証の有効化リクエストモーダルを追加

<a id="april-22-2026"></a>
### 2026. 04. 22. { #april-22-2026 }
* [Android] 1.13.1.0 **(使用中止を推奨)**
    * 信頼できない環境の検知機能を追加
        * デバイスのセキュリティ状態を確認し、信頼できない環境を検知します。
    * Java難読化バグ修正
        * バージョン1.13.0.0で難読化が一部しか適用されない問題を修正しました。
* [iOS] 1.5.1
    * 整合性認証のバグ修正
        * 特定の状況で検証に失敗する問題を修正しました。
* [Unity] 0.4.27
	* (iOS) iOS SDK 1.5.1アップデート
* [Unreal] 0.2.5
	* (iOS) iOS SDK 1.5.1アップデート
* [Console]
    * ダッシュボードの異常な振る舞い検知状況に、信頼できない環境(Android)を追加
* [Native Code Obfuscator] 1.0.0
    * ネイティブコード難読化機能をリリース
        * Android NDK(C/C++)及びiOS Xcode Toolchain(C/C++、Swift、Objective-C)ベースのネイティブコードに対する難読化機能を提供します。
        * コンパイル段階でネイティブコードの構造を変形させ、コアアルゴリズム及びビジネスロジックをリバースエンジニアリングから保護します。
        * 制御フロー平坦化、算術命令の置換、文字列エンコーディング機能をサポートします。
        * 機能を有効にするには、[NHN Cloudコンソール](https://console.nhncloud.com/)にアクセスし、Security > NHN AppGuard > アプリ保護メニューで難読化の有効化ボタンをクリックしてリクエストしてください。

<a id="april-16-2026"></a>
### 2026. 04. 16. { #april-16-2026 }
* [Android] 1.13.0.0 **(使用中止を推奨)**
    * 整合性認証の新機能を追加
        * アプリの改ざんの有無と実行環境の安全性をNHN AppGuardサーバーで検証し、検証に成功したアプリのみサービスにアクセスできるように制御する機能です。
	    * アプリが認証をリクエストすると、NHN AppGuardサーバーが整合性を検証した後にJWTトークンを発行し、発行されたトークンはお客様のサーバーで検証されます。
	* 本機能により、異常な環境で実行されるアプリのサービスへのアクセスを効果的にブロックできます。
	* 機能を有効にするには、NHN Cloud Webサイトの[カスタマーサポート > お問い合わせ](https://www.nhncloud.com/kr/support/inquiry)をご利用ください。
    * リソース文字列難読化の新機能を追加
        * strings.xmlに含まれる文字列をビルド時に難読化し、アプリケーション内部の機密情報を保護する機能です。
        * 難読化された文字列は、該当リソースを参照するメソッドの呼び出し時に自動で復号されるため、別途ソースコードを修正することなく既存のロジックをそのまま維持して適用できます。
        * AppGuard CLIで--resource-obfuscateオプションを使用して機能を有効にします。
    * Rosettaが有効化されていないApple Silicon環境でもCLIが正常に動作するように改善
    * 制御フロー難読化の適用時にInterfaceのDefault Methodで発生していたクラッシュを修正
    * 保護作業の実行時にassetsパスのdexファイルが削除されるバグを修正
* [iOS] 1.5.0
    * 整合性認証の新機能を追加 (--integrity)
        * アプリの改ざんの有無と実行環境の安全性をNHN AppGuardサーバーで検証し、検証に成功したアプリのみサービスにアクセスできるように制御する機能です。
	    * アプリが認証をリクエストすると、NHN AppGuardサーバーが整合性を検証した後にJWTトークンを発行し、発行されたトークンはお客様のサーバーで検証されます。
	* 本機能により、異常な環境で実行されるアプリのサービスへのアクセスを効果的にブロックできます。
	* 機能を有効にするには、NHN Cloud Webサイトの[カスタマーサポート > お問い合わせ](https://www.nhncloud.com/kr/support/inquiry)をご利用ください。
    * Info.plist難読化の新機能を追加
        * Info.plistに含まれる特定のキーの文字列をアプリ保護のタイミングで暗号化し、アプリ内部の機密情報を保護する機能です。
        * Info.plistの特定のキーの文字列値をアプリ保護のタイミングで暗号化し、アプリ実行時に復号することで、アプリのコードを修正せずに適用可能
        * 難読化対象のキーはJSON設定ファイルで指定し、AppGuard CLIで--resource-obfuscateオプションを使用して適用します。
        * Info.plist難読化機能を有効にするには、難読化の申請が必要です。
    * Rosettaが有効化されていないApple Silicon環境でもCLIが正常に動作するように改善
    * セキュリティの改善
* [Unity] 0.4.26
	* (iOS) iOS SDK 1.5.0 アップデート
* [Unreal] 0.2.4
	* (iOS) iOS SDK 1.5.0 アップデート
* [Console]
    * 整合性認証の新機能を追加
        * 商品タブで整合性検証ポリシー、Android署名情報などを確認できます。
        * アプリタブでアプリごとのアプリ署名、ハッシュ、キー値を確認でき、ハッシュ収集モードを変更できます。
        * 検証ログタブで整合性検証ログを確認できます。
        * 機能を有効にするには、NHN Cloud Webサイトの[カスタマーサポート > お問い合わせ](https://www.nhncloud.com/kr/support/inquiry)から有効化をリクエストしてください。
    * 難読化リクエストモーダルの改善
        * リソース難読化機能の追加に伴い、難読化リクエストモーダルにリソース難読化オプションが追加されました。
        * ネイティブコード難読化ライセンスリクエストオプションが追加されました。
    * コンソールでの保護作業時にリソース難読化ルールファイルを添付できるよう、添付機能を追加

<a id="march-10-2026"></a>
### 2026. 03. 10. { #march-10-2026 }
* [Android] 1.12.4.18
    * APKパッケージングツールをアップデートし、16KBのページサイズをサポートするように改善
* [iOS] 1.4.16
	* rootless脱獄環境のセキュリティを向上
* [Unity] 0.4.25
	* (iOS) iOS SDK 1.4.16アップデート
* [Unreal] 0.2.3
	* (iOS) iOS SDK 1.4.16アップデート

<a id="february-10-2026"></a>
### 2026. 02. 10. { #february-10-2026 }
* [Android] 1.12.4.17
    * Unity、Unrealの単一アーキテクチャApp Bundleが終了する問題を修正

<a id="january-27-2026"></a>
### 2026. 01. 27. { #january-27-2026 }
* [Android] 1.12.4.16
	* React Native 0.79.0以上アプリの互換性を改善
* [iOS] 1.4.15
	* コンソールアップロード保護時の署名改ざん検知を改善
      * CLIを利用した保護だけでなく、コンソールアップロード保護時にも署名改ざん検知が可能です。
* [Unity] 0.4.24
    * (iOS) iOS SDK 1.4.15アップデート
* [Unreal] 0.2.2
    * (iOS) iOS SDK 1.4.15アップデート
* [Console]
    * ダッシュボードの異常な振る舞い検知推移に、OS条件が適用されないバグを修正
    * ダッシュボードの異常な振る舞い検知状況にマクロツール(iOS)、VPN(Android, iOS)、仕事用プロファイル(Android)を追加
    * ダッシュボード照会時、チャートごとにローディングを表示
  
<a id="december-16-2025"></a>
### 2025. 12. 16. { #december-16-2025 }
* [Android] 1.12.4.15
    * DEX暗号化の改善
      
<a id="december-9-2025"></a>
### 2025. 12. 09. { #december-9-2025 }
* [iOS] 1.4.14
    * 暗号化APIのサポートを追加
    * PDFユーザーガイドをHTMLに変更
* [Unity] 0.4.23
    * (iOS) iOS SDK 1.4.14 アップデート
* [Unreal] 0.2.1
    * (iOS) iOS SDK 1.4.14 アップデート
* [Console]
    * 基本ポリシーに誤ったポリシーが表示される現象を修正

<a id="november-14-2025"></a>
### 2025. 11. 14. { #november-14-2025 }
* [Android] 1.12.4.14
    * Dex Reference Countが上限を超えたことにより、アプリを保護する際に難読化が失敗していた問題を修正

<a id="november-11-2025"></a>
### 2025. 11. 11. { #november-11-2025 }
* [Android] 1.12.4.13
    * 仮想環境(クローンアプリ)の検知対象アプリを追加
        * Virtual Master(Code: 1300)
    * エンジンの安定性が向上

<a id="october-23-2025"></a>
### 2025. 10. 23. { #october-23-2025 }
* [Android] 1.12.4.12
    * Google Automatic Integrity Protectionを使用するとUnreal Engine 4が異常終了する問題を修正
    * マクロツールの検知を改善
    *  エンジンのセキュリティを強化

<a id="september-09-2025"></a>
### 2025. 09. 09. { #september-09-2025 }
* [Android] 1.12.4.11
    * アプリケーション初期化時の例外処理を改善
    * シングルアーキテクチャのApp Bundleにおける終了問題を修正
    * セキュリティの改善
* [Unreal] 0.2.0
    * Secure Valueをサポート
* [iOS] 1.4.13
    * Unreal SDKでSecure Valueをサポート
    * エンジンのセキュリティを強化
* [Unity] 0.4.22
    * (iOS) iOS SDK 1.4.13へアップデート

<a id="august-12-2025"></a>
### 2025. 08. 12. { #august-12-2025 }
* [Android] 1.12.4.10
  * Unreal Engine 4エミュレーターで異常終了する不具合を修正
  * アプリ保護作業性能の改善
* [Unity] 0.4.21
    * (Android) Android SDK 0.3.0アップデート

<a id="july-29-2025"></a>
### 2025. 07. 29. { #july-29-2025 }
* [Android] 1.12.4.9
    * 16KBメモリページサイズサポート
    * Businessプラン適用時、 Application.onCreate()でユーザーIDが正常に登録されない問題を修正
    * Fly GPSとMock Locationsの検出コールバックコードが正常に呼び出されない問題を修正
    * Galaxy S6デバイスで異常終了する問題を修正
* [iOS] 1.4.12
    * Rootless脱獄環境の検出を改善
* [Unity] 0.4.20
    * (iOS) iOS SDK 1.4.12アップデート
* [Console]
    * 個別ブロックモーダルの改善
        * 基本ポリシーを直感的に理解できるようにUIを改善
        * 個別ブロック項目が重複して表示されるバグを修正

<a id="june-24-2025"></a>
### 2025. 06. 24. { #june-24-2025 }
* [Android] 1.12.4.8
    * 最小サポートバージョンの引き上げ(API 19 -> API 21)
    * synchronizedキーワードを含むメソッドの制御フロー難読化時に発生する問題を修正
    * React Native 0.76.0以上のバージョンをサポート
* [iOS] 1.4.11
    * React Native Expo互換性改善
        * 初回インストール時にExpoアプリが終了する問題を修正しました。
* [Console]
    * SDKダウンロードモーダルを改善
        * Unreal Engine SDKダウンロードを追加
        * 列ベースのグリッドビューからリストビューへUI改善
* [Unity] 0.4.19
    * (iOS) iOS SDK 1.4.11アップデート
* [Unreal] 0.1.0
    * NHN AppGuard Unreal SDKをリリース
    
<a id="may-27-2025"></a>
### 2025. 05. 27. { #may-27-2025 }
* [Android] 1.12.4.7
    * 仮想環境(クローンアプリ)検出機能を追加
        * 次のようなクローンアプリ環境を検出できるように機能を拡張しました：
            * Multi App(Code: 1306)
            * Parallel Space(Code: 1307)
            * DualSpace(Code: 1308)
            * Clone App(Code: 1309)
            * 2 Account(Code: 1310)
            * Dual App(Code: 1311)
            * DualSpace Lite(Code: 1312)
            * DualSpace Pro(Code: 1313)
    * 職場プロフィール検出機能追加(Code: 2301)
        * コンソール > NHN AppGuard > ポリシー > Android > 職場プロファイルポリシーの設定で該当機能を有効にすることができます。
    * 検出コード設定エラー修正
        * 条件ベースの検出時、検出コードが誤って「00」に設定されていた問題を修正しました。
    * 検出コールバックロジックを改善
        * 同じ検出イベントに対してコールバックが重複して呼び出されないように処理ロジックを改善しました。
        * Businessプラン適用時、 Application.onCreate()でコールバックが正常に登録されない問題を解決しました。
    * User ID定時に再検出されない問題を修正
        * User ID設定時、一部の検出ロジックで再検出が正常に行われない問題を修正しました。
    * マクロツール検出機能の改善

<a id="may-15-2025"></a>
### 2025. 05. 15. { #may-15-2025 }
* [iOS] 1.4.10
    * フッキング検出の誤検出を修正
        * デバッグビルドで`ENABLE_DEBUG_DYLIB`の設定有無によってフッキング検出が誤検出される問題を修正しました。
* [Unity] 0.4.18
    * (iOS) iOS SDK 1.4.10アップデート

<a id="april-29-2025"></a>
### 2025. 04. 29. { #april-29-2025 }
* [Android] 1.12.4.6
    * (React Native) Expo Updatesを適用した際にアプリが異常終了する問題を修正
    * 複数のアプリを並列で保護する場合に、まれに文字列難読化テーブルが破損する問題を修正
    * 文字列難読化テーブルが重複して生成される問題を修正
    * User IDをnullに設定した場合にアプリが異常終了する問題を修正
    * Callbackメソッドをnullに設定した場合にアプリが異常終了する問題を修正

<a id="april-21-2025"></a>
### 2025. 04. 21. { #april-21-2025 }
* [iOS] 1.4.9
    * エンジンセキュリティの強化
        * エンジン保護機能を強化しました。
* [Unity] 0.4.17
    * (iOS) iOS SDK 1.4.9アップデート

<a id="march-25-2025"></a>
### 2025. 03. 25. { #march-25-2025 }
* [Android] 1.12.4.5
    * Google自動保護(Google Automatic Protection)適用時にclasses.dexが誤検知される問題を修正
    * レガシーテーマ(@android:style/Theme.Holo.Lightなど)使用時に終了ポップアップの上部が空白になる問題を修正

<a id="march-11-2025"></a>
### 2025. 03. 11. { #march-11-2025 }
* [Android] 1.12.4.4
    * 異常終了するエラーを修正
  
<a id="march-7-2025"></a>
### 2025. 03. 07. { #march-7-2025 }
* [Android] 1.12.4.3
    * シンプルポップアップの適用時に保護作業に失敗するエラーを修正

<a id="march-4-2025"></a>
### 2025. 03. 04. { #march-4-2025 }
* [Android] 1.12.4.2
    * Unity最新バージョン(6000.0.38f1)で保護作業に失敗する問題を修正
* [iOS] 1.4.8
    * 安定性の改善
* [Unity] 0.4.16
    * (iOS) NHN AppGuard iOS初期化安定性の改善
* [Gradle Plugin] 1.2.5
    * 保護作業中のエラー処理の改善
    
<a id="february-12-2025"></a>
### 2025. 02. 12. { #february-12-2025 }
* [iOS] 1.4.7
    * エンジン安定性向上
* [Unity] 0.4.15
    * ネイティブポップアップを有効にするかどうかのオプションを追加
    * (iOS)コールバック安定性改善
    * (iOS) iOS SDK 1.4.7アップデート

<a id="fabruary-11-2026"></a>
### 2025. 02. 11. { #fabruary-11-2026 }
* [Android] 1.12.4.1
    * Dex暗号化バグ修正

<a id="february-6-2025"></a>
### 2025. 02. 06. { #february-6-2025 }
* [iOS] 1.4.6
    * 特定の状況でCPU使用率が高くなる問題を修正
* [Unity] 0.4.14
    * (iOS) iOS SDK 1.4.6アップデート

<a id="february-3-2025"></a>
### 2025. 02. 03. { #february-3-2025 }
* [Gradle Plugin] 1.2.4
    * Gradleビルド時にログレベルを`QUIET(-q | --quiet)`に設定すると、NHN AppGuard のログが出力されないように修正。

<a id="january-21-2025"></a>
### 2025. 01. 21. { #january-21-2025 }
* [Android] 1.12.4.0
    * VPN検出機能追加
        * コンソール > NHN AppGuard > ポリシー > Android > VPNポリシー設定で適用が可能です。
    * NHN AppGuard起動メッセージを追加
        * アプリ実行時にNHN AppGuardの有効化有無を知らせるメッセージが表示されます。
        * CLIで`--show-startup-message`を追加して有効にできます。
    * '--google-pairip'オプションの使用中止
        * '--google-pairip'オプションが不要になり、その機能はオプションがなくても自動的に有効になります。
* [iOS] 1.4.5
    * VPN検出機能追加
        * コンソール > NHN AppGuard > ポリシー > iOS > VPNポリシー設定から適用が可能です。
    * NHN AppGuard起動メッセージを追加
        * CLIで`--show-startup-message`を追加して有効にできます。
* [Unity] 0.4.13
    * (iOS) AppGuard iOS Settings > ExtraOptions追加
    * (iOS) iOS SDK 1.4.5アップデート
* [Console]
    * ブラックリストの検索条件を追加(開始日、有効期限、ブロック理由)
    * ブラックリスト照会ページサイズ調整機能を追加
    * 照会したブラックリストに対してExcelダウンロード機能を追加
    * 照会したブラックリストに対して一括再登録、一括解除機能を追加
    * ブラックリスト一括登録機能を追加

<a id="january-16-2025"></a>
### 2025. 01. 16. { #january-16-2025 }
* [Gradle Plugin] 1.2.3
    * overrideOutputFileオプションが正常に動作しない問題を修正

<a id="january-06-2025"></a>
### 2025. 01. 06. { #january-06-2025 }
* [Android] 1.12.3.2
    * 難読化例外処理方法の改善

<a id="december-24-2024"></a>
### 2024. 12. 24. { #december-24-2024 }
* [Android] 1.12.3.1
    * 難読化例外処理方法の改善

<a id="december-3-2024"></a>
### 2024. 12. 03. { #december-3-2024 }
* [Android] 1.12.3.0
    * マクロツール検出改善
        * マクロツール(Code: 1700)検出改善
    * Dex暗号化改善
* [Android] 1.12.2.12
    * 難読化問題の修正
* [iOS] 1.4.4
  * マクロツール検出機能を追加
    * iOSのスイッチ制御機能を通じたマクロ行為を検出/遮断します。
* [Unity] 0.4.12
    * (iOS) iOS SDK 1.4.4アップデート  

<a id="november-28-2024"></a>
### 2024. 11. 28. { #november-28-2024 }
* [Android] 1.12.2.11
    * 難読化問題を修正

<a id="november-8-2024"></a>
### 2024. 11. 08. { #november-8-2024 }
* [Android] 1.12.2.10
    * 難読化の過程で発生したエラーにより、保護作業に失敗する問題を修正しました。

<a id="november-5-2024"></a>
### 2024. 11. 05. { #november-5-2024 }
* [Android] 1.12.2.9
    * 安定性の改善
* [iOS] 1.4.3
    * 画面キャプチャ、画面録画検出機能を追加
    * 画面保護機能のためのAPIを追加
        * SDK APIを通じてバックグラウンドスナップショット、画面キャプチャ、画面録画の画面保護機能を有効にできます。
* [Unity] 0.4.11
    * (iOS) iOS SDK 1.4.3アップデート
    
<a id="october-30-2024"></a>
### 2024. 10. 30. { #october-30-2024 }
* [Android] 1.12.2.8
    * デバッグモードのアプリが異常終了する問題を修正

<a id="october-25-2024"></a>
### 2024. 10. 25. { #october-25-2024 }
* [Android] 1.12.2.7
    * 一部の低スペックデバイスで異常終了する問題を修正

<a id="october-15-2024"></a>
### 2024. 10. 15. { #october-15-2024 }
* [Android] 1.12.2.6
    * 仮想環境検出パターンを追加
        * Black Box(Code: 1304)検出を追加
        * KGO(Code: 1305)検出を追加
    * エミュレータ検出パターンを追加
        * UgPhone(Code: 212)検出を追加
    * マクロツール検出パターンを追加
        * Auto Clicker - Automatic tap(Code: 1710)
* [Gradle Plugin] 1.2.2
    * Android Gradle Plugin 8.1.0以上のバージョンのサポート
* [Console]
    * ダッシュボードの異常行為検出状況テーブルに位置操作カラムを追加
    * (iOS)ダッシュボードの異常行為検出状況テーブルにブラックリストカラムを追加
    * ログ照会でOS検索条件をiOSに選択した場合、ブラックリスト条件が表示されるように追加
    * iOS保護履歴のAppGuardバージョンをSDKバージョンのみ表示するように修正
    * ログ照会でGamebaseのdevice_keyとして活用可能なANDROID IDカラム照会を追加
    
<a id="september-27-2024"></a>
### 2024. 09. 27. { #september-27-2024 }
* [Android] 1.12.2.5
    * Google自動整合性保護(Google Automatic Integrity Protection)使用時のUnity改ざん(Code: 405)誤検知問題を修正
    * アビューズアプリ検出(Code: 1600)誤検知問題を修正
    
<a id="september-10-2024"></a>
### 2024. 09. 10. { #september-10-2024 }
* [Android] 1.12.2.4
    * アプリローディング速度改善
    * android:extractNativeLibraries="false"設定時、SDK APIが正常に動作しない問題を修正
    * NoxPlayer Android 5バージョンでアプリが異常終了する問題を修正
    * UnityまたはUnrealのデバッグモードアプリで異常終了する問題を修正

<a id="august-27-2024"></a>
### 2024. 08. 27. { #august-27-2024 }
* [Console]
    * ログ照会結果にデバイスモデル情報を追加

<a id="august-26-2024"></a>
### 2024. 08. 26. { #august-26-2024 }
* [Android] 1.12.2.3
    * アプリ更新時にアプリが異常終了する問題を修正

<a id="august-20-2024"></a>
### 2024. 08. 20. { #august-20-2024 }
* [Android] 1.12.2.2
    * Android 14(API 34)ターゲットアプリが一部の低スペックデバイスで異常終了する問題を修正

<a id="august-13-2024"></a>
### 2024. 08. 13. { #august-13-2024 }
* [Android] 1.12.2.1
    * アプリローディング速度を改善
    * Android 14(API 34)エミュレータ検出を追加
    * Google自動整合性保護(Google Automatic Integrity Protection)オプション互換性を改善
    * アプリ署名オプション("--as")を改善
        *  2つ以上の署名情報を入力した時、KeyStoreの署名値が含まれていてもエラーが発生しないように改善しました。

<a id="july-23-2024"></a>
### 2024. 07. 23. { #july-23-2024 }
* [Android] 1.12.2.0
    * ルート化検出機能強化
* [Console]
    * アラーム設定失敗文言の細分化
    * ブラックリストブロック基準を変更して再登録する機能を追加しました。

<a id="july-9-2024"></a>
### 2024. 07. 09. { #july-9-2024 }
* [Android] 1.12.1.1 
    * Google自動整合性保護(Google Automatic Integrity Protection)オプション使用時、NHN AppGuard改ざん誤検知イシューを修正
        * Google自動整合性保護オプション: "--google-pairip"
* [Android] 1.12.1.0
    * Android 5.1以下のバージョンでクラッシュが発生する問題を修正
    * 一部の検出ロジックが正常に動作しない問題を修正
    * Google PADとNHN AppGuard Unity SDKの互換性のバグを修正
* [iOS] 1.4.2 
	* (React Native) Codepushを適用する時、ロールバックされる問題を修正
    * エンジンの安定性向上
* [Unity] 0.4.10
    * (SecureValue)パフォーマンスとセキュリティの脆弱性を改善
    * (SecureValue)シリアル化および逆シリアル化機能を追加しました。
        * Newtonsoft及びPhoton RPCをサポートします。

<a id="june-7-2024"></a>
### 2024. 06. 07. { #june-7-2024 }
* [iOS] 1.4.1
    * エンジンの安定性改善
        * 特定の状況で仮想メモリの使用が増加する問題を改善しました。
* [Unity] 0.4.9
    * (iOS) iOS SDK 1.4.1アップデート

<a id="june-5-2024"></a>
### 2024. 06. 05. { #june-5-2024 }
* [Android] 1.12.0.1
    * NHN AppGuardのセキュリティ強化

<a id="may-31-2024"></a>
### 2024. 05. 31. { #may-31-2024 }
* [Android] 1.12.0.0
    * 位置操作検出機能を追加
        * コンソール > NHN AppGuard > ポリシー > Android > 位置操作ポリシー設定で適用が可能です。
    * Google PADとNHN AppGuard Unity SDK間の互換性問題を修正
* [Android] 1.11.1.1
    * アプリ実行時、断続的な異常終了イシューを修正
* [iOS] 1.4.0
    * 位置操作検出機能を追加
        * コンソール > NHN AppGuard > ポリシー > iOS > 位置操作ポリシー設定から適用が可能です。
        * iOS 15以上で検出可能です。
* [Unity] 0.4.8
    * (iOS) iOS SDK 1.4.0アップデート

<a id="may-14-2024"></a>
### 2024. 05. 14. { #may-14-2024 }
* [Console]
    * 設定タブの追加
    * 検出/遮断アラーム設定機能の追加

<a id="april-18-2024"></a>
### 2024. 04. 18. { #april-18-2024 }
* [iOS] 1.3.20
    * 初期化呼び出しのタイミングによって発生する可能性のあるエンジン誤動作の問題を修正
* [Unity] 0.4.7
    * (iOS) iOS SDK 1.3.20アップデート
<a id="april-16-2024"></a>
### 2024. 04. 16. { #april-16-2024 }
* [Android] 1.11.1.0
    * Flutterアプリ保護をサポート
        * CLIで保護作業時、`--flutter`オプションを追加する必要があります。
    * LDPlayer検出の改善
    * NHN AppGuardのセキュリティ強化
* [iOS] 1.3.19
    * Flutterアプリの保護をサポート
        * CLIで保護作業時、`--flutter`オプションを追加する必要があります。
* [Unity] 0.4.6
    * Device ID取得APIを追加
    * (iOS) iOS SDK 1.3.19アップデート
* [Flutter] 0.1.0
    * NHN AppGuard Flutter SDKをリリース
* [Console] 
  * ポリシータブの個別ブロック機能を追加
  * 保護タブのSDKダウンロード内のFlutter SDKダウンロードを追加


<a id="april-3-2024"></a>
### 2024. 04. 03. { #april-3-2024 }
* [Android] 1.11.0.1
    * Android 10デバイスで異常終了する問題を修正

<a id="april-2-2024"></a>
### 2024. 04. 02. { #april-2-2024 }
* [Andorid] 1.11.0.0
    * React Nativeアプリ保護機能を追加
        * CLIで保護作業をする時、`--react-native` オプションを追加する必要があります。
    * アンチデバッグ機能強化
* [iOS] 1.3.18
    * React Nativeアプリ保護をサポート
* [Unity] 0.4.5
    * (iOS) NHN AppGuard iOSライブラリをxcodeプロジェクトに追加する際、相対パスに追加できるように改善
    * (iOS) iOS SDK 1.3.18アップデート
* [React Native] 0.1.0
    * NHN AppGuard React Native SDKリリース

<a id="march-12-2024"></a>
### 2024. 03. 12. { #march-12-2024 }
* [Android] 1.10.6.0
    * 重要ライブラリ(.so)保護機能追加
        * Unity、Unrealなどのゲームエンジン以外の重要なライブラリ(.so)を保護する機能が追加されました。
    * HUAWEI AppGalleryをサポート
        * CLI保護作業時、"-huawei"オプションを使用する必要があります。
    * NHN Android AppGuard SDK連動後、保護作業なしで正常に実行されるように改善
    * 検出ポップアップ画面の異常を修正
    * カスタムポップアップ設定後、検出ポップアップが表示される問題を修正
    * Device ID取得APIを追加
        * コンソール > NHN AppGuard Android SDKダウンロード画面で.aarファイルをアップデートする必要があります。
* [iOS] 1.3.17
    * 検出時間の短縮
    * Modulemapの追加
* [Unity] 0.4.4
    * (iOS) iOS SDK 1.3.17アップデート

<a id="february-23-2024"></a>
### 2024. 02. 23. { #february-23-2024 }
* [Android] 1.10.5.5
    * 悪性行為検出ポップアップデザイン改善
    * セキュリティの改善
    * マクロツール検出パターンを追加
        * Auto Click - Automatic Clicker(Code: 1708)検出を追加
        * Auto Tapper: Auto Clicker(Code: 1709)検出を追加
    * 遠隔制御検出パターンヲ追加
        * TeamViewer Host(Code: 1401)検出を追加
        * AnyDesk(Code: 1403)検出を追加
    * DEX暗号化適用時、容量が大きく増加する問題を修正
* [iOS] 1.3.16
    * [Unity] iOS 15環境でアプリ実行時に異常終了する問題を修正
* [Unity] 0.4.3
    * (iOS) 検出通知ウィンドウが表示されない問題を修正
    * (iOS) iOS SDK 1.3.16アップデート

<a id="february-16-2024"></a>
### 2024. 02. 16. { #february-16-2024 }
* [Unity] 0.4.2
    * (iOS) NHN AppGuard iOSビルドの問題を修正
        * Package Manager使用時、iOSビルドが失敗する問題を修正しました。
    * (iOS) iOS SDK 1.3.15アップデート

<a id="february-15-2024"></a>
### 2024. 02. 15. { #february-15-2024 }
* [iOS] 1.3.15
    * iOS最小サポートバージョンのアップ(iOS 11以上)
    * i386, armv7s, armv7アーキテクチャのサポート終了
    * 基本検出通知ウィンドウの改善
    * 個人情報保護マニフェストを追加
    * 署名の追加(NHN Cloud Corp.)

<a id="january-23-2024"></a>
### 2024. 01. 23. { #january-23-2024 }
* [Android] 1.10.5.3
    * 難読化機能の改善
        * 関数呼び出し非表示(Hide Call)機能を改善します。

<a id="january-9-2024"></a>
### 2024. 01. 09. { #january-9-2024 }
* [Android] 1.10.5.2
    * DEX暗号化・復号の改善
    * MEmuエミュレータ検出の改善
        * MEmu 9.0.9バージョンでも検出できるように改善しました。
    * LDPlayer9エミュレータ検出改善
        * LDPlayer9 9.0.63バージョンでも検出できるように改善しました。
    * Google自動整合性保護(Google Automatic Integrity Protection)サポートオプション追加
        * Google自動整合性保護を使用する場合、"--google-pairip"オプションを使用する必要があります。
* [iOS] 1.3.14
    * エンジンの安定性の改善
* [Unity] 0.4.1
    * (iOS) iOS SDK 1.3.14アップデート
    
<a id="december-28-2023"></a>
### 2023. 12. 28. { #december-28-2023 }
* [Android] 1.10.5.1
    * StackOverflowErrorの問題を修正

<a id="december-19-2023"></a>
### 2023. 12. 19. { #december-19-2023 }
* [Android] 1.10.5.0
    * Android 14対応
        * Android 14(API 34)以上をターゲットとするアプリで、NHN AppGuard適用時に異常終了する問題を修正しました。
    * マルチプロセス対応
        * アプリケーションコンポーネントにandroid:processプロパティがある場合、断続的に異常終了するエラーを修正しました。
    * armeabiアーキテクチャのエラーを修正
        * armeabiアーキテクチャのみを使用するアプリで発生する異常終了エラーを修正しました。
* [iOS] 1.3.13
    * エンジンセキュリティの強化
    * AppKey設定前の検出時にログが抜け落ちる問題を修正
        * AppKey設定前のPrivate APIで悪質行為検出時にログが抜け落ちる問題を修正しました。
        * 保護作業設定時に適用されます。
    * 一部のクラスシンボルの難読化時に保護作業に失敗する問題を修正
    * CLI 引数の改善
        * `--latestVersion` 引数がデフォルトで適用されます。
* [Unity] 0.4.0
    * [iOS] NHN AppGuard iOS初期化作業を改善
        * Diresu.D関数は使用されなくなりました(deprecated)。
    * (iOS) iOS SDK 1.3.13アップデート
* [Gradle Plugin] 1.2.1
    * 署名鍵のパスワード設定エラーを修正
        * ストアパスワードとキーパスワードが異なる場合、署名に失敗するエラーを修正しました。

<a id="december-06-2023"></a>
### 2023. 12. 06. { #december-06-2023 }
* [iOS] 1.3.12
    * エンジンセキュリティの強化
* [Unity] 0.3.1
    * (iOS) iOS SDK 1.3.12アップデート
    
<a id="november-24-2023"></a>
### 2023. 11. 24. { #november-24-2023 }
* [Android] 1.10.4.1
    * NHN AppGuardセキュリティ脆弱性の改善

<a id="november-21-2023"></a>
### 2023. 11. 21. { #november-21-2023 }
* [Android] 1.10.4.0
    * Amazon Appstore署名検証の有効化[Gradle Plugin]
        * "--amazon"オプションを使用してアプリ保護時にアプリ署名検証が有効になります。
        * Amazon Appstoreは"--as"オプションを使用してAppstore署名のSHA-256 Hexadecimal情報を設定する必要があります。
        * Appstore署名はAmazon Developer > My apps > Appstore Certificate Hashesで確認できます。
    * SecureValue改ざん(Code: 409)検出機能を追加
    * DEXローディング方式の改善
    * NHN AppGuardのセキュリティ強化
* [iOS] 1.3.11
    * 脱獄環境の検出を強化
    * Unreal Engine用静的ライブラリの配布を追加
    * Unreal Engineサポート改善
    * エンジンセキュリティの強化
* [Unity] 0.3.0
    * (Android) SecureValue改ざん(Code: 409)検出機能追加
    * (iOS) iOS SDK 1.3.11アップデート

<a id="october-24-2023"></a>
### 2023. 10. 24. { #october-24-2023 }
* [iOS] 1.3.10
    * 難読化プラグインが適用されたUnityアプリを保護する際に保護に失敗する問題を修正
* [Unity] 0.2.2
    * iOS SDK 1.3.10アップデート

<a id="october-19-2023"></a>
### 2023. 10. 19. { #october-19-2023 }
* [Android] 1.10.3.3
    * NHN AppGuardエンジンセキュリティの強化
    * MEmuエミュレータ検出機能を追加
    * 低スペックデバイスの安全性改善
    * ファイル名に特定文字列が含まれる場合に保護作業が失敗するエラーを修正
* [iOS] 1.3.9
    * Unityアプリ保護強化
    * User ID変更時に検出ログを再送信するように改善
    * CLIで再署名実行時の出力メッセージを改善
    * 安定性改善
* [Unity] 0.2.1
    * iOS SDK 1.3.9アップデート

<a id="september-26-2023"></a>
### 2023. 09. 26. { #september-26-2023 }
* [Android] 1.10.3.2
    * 署名改ざん誤検知を修正
        * アプリ保護時に使用するkeystoreの署名を改ざんと判断する問題を修正しました。
    * 署名の重複を確認
        * `--as` オプションとkeystoreの署名が同じ場合、エラーを返すように修正
* [Unity] 0.2.0
    * Certificate Fingerprints無効化オプションを追加
* [Gradle Plugin] 1.2.0
    * Certificate Fingerprintsオプションを追加

<a id="september-13-2023"></a>
### 2023. 09. 13. { #september-13-2023 }
* [Android] 1.10.3.1
    * アプリ署名改ざんの誤検知イシューを修正
* [Unity] 0.1.8
    * iOS SDK 1.3.8アップデート

<a id="september-12-2023"></a>
### 2023. 09. 12. { #september-12-2023 }
* [Android] 1.10.3.0
    * [CLI]アプリ署名(SHA-256)追加オプションを必須項目に変更
        * Google Play、OneStoreなどのストア署名方式を使用する場合 `--as` オプション必須
        * apkまたはaabに署名された情報以外の署名を許可しない場合、`--no-as`オプション必須
    * デバイス容量不足でアプリが実行できない場合、メッセージ表示
    * Google自動整合性保護(Google Automatic Integrity Protection)をサポート
    * Noxエミュレータ検出の改善
    * NHN AppGuardエンジンセキュリティの強化
    * 識別子難読化の改善
    * フッキング検出機能の改善
    * Auto Click Assistant(Code: 1707)検出を追加
    * 低仕様タブレットの安全性向上
* [iOS] 1.3.8
    * エンジンセキュリティの強化
    * アプリ復号防止機能を強化

<a id="august-17-2023"></a>
### 2023. 08. 17. { #august-17-2023 }
* [Android] 1.10.2.2
    * フック検出機能の強化
    * エンジンの安定性改善
    * [Unity] Android 4.4(API 19)で異常終了するエラーを修正
* [iOS] 1.3.7
    * エンジンセキュリティの強化
    * アプリ復号防止機能を強化
    * CLIに再署名機能を追加
        * これまで提供していた再署名スクリプトの提供は終了しました。
* [Unity] 0.1.7
    * iOS SDK 1.3.7アップデート

<a id="july-21-2023"></a>
### 2023. 07. 21. { #july-21-2023 }
* [Android] 1.10.2.1
    * アプリ起動時の異常終了の問題を修正
    * 難読化の改善
        * 難読化対象メソッドが65Kを超えると保護作業に失敗する問題に対応
    * ポリシー改ざん対応改善

<a id="july-11-2023"></a>
### 2023. 07. 11. { #july-11-2023 }
* [Android] 1.10.2.0
    * アビューズアプリ検出機能の強化
    * NHN AppGuard基本ポリシーの改善
    * ブラックリストバグの修正
* [Gradle Plugin] 1.1.2
    * Firebase Crashlytics Gradle 2.8.1以上でmapping.txtファイルがアップロードされないイシューを修正
* [iOS] 1.3.6
    * エンジンセキュリティの強化
    * Info.plist改ざん検出の改善
    * アプリ復号防止機能の追加
    * 基本ポリシー機能の改善
    * f関数Deprecated
* [Unity] 0.1.6
    * 安定性の改善
    * iOS SDK 1.3.6アップデート

<a id="july-6-2023"></a>
### 2023. 07. 06. { #july-6-2023 }
* [Android] 1.10.1.2
    * ルート化検出機能の強化
    * 安定性改善

<a id="june-16-2023"></a>
### 2023. 06. 16. { #june-16-2023 }
* [Unity] 0.1.5
    * iOS SDK 1.3.5アップデート

<a id="june-15-2023"></a>
### 2023. 06. 15. { #june-15-2023 }
* [iOS] 1.3.5
    * Info.plist改ざん誤検知の改善
* [iOS] 1.3.4
    * エンジンセキュリティの強化
* [Unity] 0.1.4
    * iOS SDK 1.3.4アップデート

<a id="june-13-2023"></a>
### 2023. 06. 13. { #june-13-2023 }
* [Android] 1.10.1.0
    * マクロツール検出の改善
    * Amazon AppStoreのサポート
* [iOS] 1.3.3
    * リソース改ざん検出機能の追加(Info.plist改ざん対応)
    * 検出コールバックデータ形式の改善(ユーザーガイド参照)
    * 検出コード形式改善(ユーザーガイド参照)
    * 再署名スクリプト実行時、パスに空白が含まれている場合、再署名に失敗するバグを修正
    * エンジンセキュリティの改善
    * AdSupport.framework必須フレームワーク除外
* [Unity] 0.1.3
    * Xcodeライブラリ依存性の削除
    * AdSupport.framework必須フレームワークの除外反映
    * iOS SDK 1.3.3アップデート

<a id="may-30-2023"></a>
### 2023. 05. 30. { #may-30-2023 }
* [Android] 1.10.0.5
    * 識別子難読化エラーを修正

* [Gradle Plugin] 1.1.1
    * extraOptionsエラーを修正

<a id="may-11-2023"></a>
### 2023. 05. 11. { #may-11-2023 }
* [iOS] 1.3.2
    * エンジンセキュリティの強化(Unity)

* [Unity] 0.1.2
    * Linux OSでCLI保護作業が実行されるように改善
    * iOS SDK 1.3.2アップデート

<a id="may-2-2023"></a>
### 2023. 05. 02. { #may-2-2023 }
* [Android] 1.10.0.4
    * 権限改ざん(400_106_0)の誤検知問題を修正

<a id="april-25-2023"></a>
### 2023. 04. 25. { #april-25-2023 }
* [Android] 1.10.0.3
    * AndroidManifest.xmlのandroid:debuggableプロパティ改ざん検出を追加
    * ライブラリパッキングエラーを修正
    * 異常行為ブロック時のアプリ終了ロジックを改善
    * [CLI]保護作業失敗処理の改善
    * [CLI]保護されたアプリのダウンロードを改善
    * [Unity] il2cpp暗号化の改善
    * [Unity]ゲームメモリ整合性検証を改善
    * [Cocos2d] Crashlyitcsでシンボル分析ができない問題を修正

* [iOS] 1.3.1
    * エンジンセキュリティの強化
    * 条件ブロックポリシーの連動
    * frameworkのinfo.plistの除去

* [Unity] 0.1.1
    * iOS SDK 1.3.1アップデート

<a id="april-14-2023"></a>
### 2023. 04. 14. { #april-14-2023 }
* [Android] 1.10.0.2
    * 32bitエミュレータで正常に終了しないエラーを修正
    * 文字列難読化の改善

<a id="april-10-2023"></a>
### 2023. 04. 10. { #april-10-2023 }
* [Android] 1.10.0.1
    * 文字列暗号化エラーを修正

<a id="march-28-2023"></a>
### 2023. 03. 28. { #march-28-2023 }
* [Android] 1.10.0.0
    * 外部攻撃検出時のアプリ終了ロジックを改善
    * 料金プラン変更(Business、Enterprise、Game)

* [iOS] 1.3.0
    * エンジンセキュリティの強化
    * 料金プラン変更(Business, Enterprise, Game)

* [Unity] 0.1.0
    * NHN AppGuard Unity SDKリリース

* [Gradle Plugin] 1.1.0
    * 料金プランオプション変更(Business, Enterprise, Game)

<a id="february-28-2023"></a>
### 2023. 02. 28. { #february-28-2023 }
* [Android] 1.9.13.5
    * アビューズアプリライセンス検出の改善
    * 条件ブロックポリシーが適用されない問題を修正
    * Unityアプリ実行時にクラッシュが発生する問題を修正
    * Unity整合性検証の偽陰性を修正(405_49_0)

* [iOS] 1.2.10
    * エンジンセキュリティの強化
    * iOS 15互換性の改善

<a id="february-8-2023"></a>
### 2023. 02. 08. { #february-8-2023 }
* [Android] 1.9.13.1
    * DEX難読化イシューを修正

<a id="january-31-2023"></a>
### 2023. 01. 31. { #january-31-2023 }
* [Android] 1.9.13.0
    * 暗号化APIヘッダを変更
    * アプリバンドルイシューを修正
    * セキュリティ機能を強化
    * x86, x86_64イシューを修正
    
* [iOS] 1.2.9
    * 基本ポリシー機能を追加
    * エンジンセキュリティの強化
    * シミュレータ偽陰性の改善
    * xcframeworkサポート
    * AppGuard CLI機能の改善

<a id="december-27-2022"></a>
### 2022. 12. 27. { #december-27-2022 }
* [Android] 1.9.12.0
    * クライアントポリシーのサポート終了
    * 基本ポリシー機能の追加
    * 警告ウィンドウ未発生の問題
    * DEX暗号化クラッシュ問題の修正
    
* [iOS] 1.2.8
    * エンジンセキュリティの強化
    * iOS 16互換性の改善

<a id="december-13-2022"></a>
### 2022. 12. 13. { #december-13-2022 }
* [Android] 1.9.11.2
    * API表示の問題の修正
    * LifecycleCallbackの問題の修正
    * 特定保護機能クラッシュおよび偽陰性問題の修正
    * x86クラッシュ問題の修正

<a id="december-7-2022"></a>
### 2022. 12. 07. { #december-7-2022 }
* [Android] 1.9.11.1
    * 改ざん偽陰性問題の修正

<a id="november-29-2022"></a>
### 2022. 11. 29. { #november-29-2022 }
* [Android] 1.9.11.0
    * フレームドロップ問題の修正
    * SSLピンニングバイパス未検出問題の修正
    * Google Playゲームズのサポート
    * クラッシュ問題の修正

* [iOS] 1.2.7
    * APIフック検出ロジックの強化
    * ポリシー関連イシューの解決
    * AppGuard CLI機能の改善

<a id="november-9-2022"></a>
### 2022.11.09. { #november-9-2022 }

* [Android] 1.9.10.2
    * バックグラウンドクラッシュ問題の修正

<a id="november-2-2022"></a>
### 2022.11.02. { #november-2-2022 }

* [Android] 1.9.10.1
    * クラッシュ問題の修正

<a id="october-28-2022"></a>
### 2022. 10. 28. { #october-28-2022 }
* [iOS] 1.2.6
    * エンジンセキュリティの強化

<a id="october-25-2022"></a>
### 2022. 10. 25. { #october-25-2022 }
* [Android] 1.9.10.0
    * エミュレータ検出機能の強化
    * チートツール検出機能の強化

<a id="october-14-2022"></a>
### 2022. 10. 14. { #october-14-2022 }
* [Android] 1.9.9.2
    * LDPlayer4 64bitエミュレータのサポート
    * 韓国語警告ウィンドウの追加
    * 初期化速度改善
    * エミュレータクラッシュ問題の修正
    * エンジンセキュリティの強化

<a id="october-7-2022"></a>
### 2022. 10. 07. { #october-7-2022 }
* [Android] 1.9.9.1
    * 当該バージョンの削除

<a id="october-4-2022"></a>
### 2022. 10. 04. { #october-4-2022 }
* [Android] 1.9.9.0
    * 当該バージョンの削除

* [iOS] 1.2.5
    * エンジンセキュリティの強化
    * ネットワーク関連バグパッチ
    * リパッケージ関連セキュリティ強化

<a id="september-8-2022"></a>
### 2022. 09.08. { #september-8-2022 }
* [Android] 1.9.8.1
    * マニフェスト問題の修正

<a id="august-23-2022"></a>
### 2022. 08. 23. { #august-23-2022 }
* [Android] 1.9.8.0
    * クレマ端末mpサポート 
    * BlueStacks、Nox、LDPlayer9 64bitエミュレータのサポート
    * SafetyNetのサポート中止
    * エンジンセキュリティの強化
    * Unity保護作業問題の修正

* [iOS] 1.2.4
    * エンジンセキュリティの強化
    * tweak検出機能の追加

<a id="july-26-2022"></a>
### 2022. 07. 26. { #july-26-2022 }
* [Android] 1.9.7.0
    * エンジンセキュリティの強化
    * マニフェストバグの修正
    * 未検出バグの修正

* [iOS] 1.2.3
    * エンジンセキュリティの強化
    * Device ID関連APIの追加

* [Gradle Plugin] 1.0.2
    * CLIコンソールログ出力

<a id="july-6-2022"></a>
### 2022. 07. 06. { #july-6-2022 }
* [Android] 1.9.6.1
    * ANR問題の修正
    * エンジンセキュリティの強化

<a id="june-30-2022"></a>
### 2022. 06. 30 { #june-30-2022 }

<a id="june-30-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.6.0
    * 一部ANRイシュー修正
    * エンジンセキュリティの強化

* [iOS] 1.2.2
    * 改ざん検知機能の強化
    * Unity専用セキュリティAPIの追加
    * エンジンセキュリティの強化

* [Gradle Plugin] 1.0.1
    * varianatsごとに保護されたファイルパス保存オプションを追加
    * 署名キーパスワード、エイリアス(alias)に空白を含めることができるように改善

<a id="may-24-2022"></a>
### 2022. 05. 24. { #may-24-2022 }

<a id="may-24-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.5.0
    * ブラックリスト遮断機能の改善
    * 一部クラッシュ問題の修正
    * BlueStacks(BlueStacks)エミュレータ検証の強化
    * エンジンセキュリティの強化

* [iOS] 1.2.1
    * NHN AppGuard iOS CLIの追加

* [Console]検知ログ検索可能期間の変更(30日→90日)

<a id="may-10-2022"></a>
### 2022. 05. 10. { #may-10-2022 }

<a id="may-10-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.4.1
    * ANRおよびクラッシュ問題の改善
    * コールバックデータの改善
    * エミュレータ検知機能の強化
    * エンジンセキュリティの強化

<a id="april-26-2022"></a>
### 2022. 04. 26. { #april-26-2022 }

<a id="april-26-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.4.0
    * 該当バージョンの削除

* [iOS] 1.2.0
    * Unityフレームワーク関連セキュリティの強化
    * エンジンセキュリティの強化

* [Gradle Plugin] 1.0.0
    * groupId、パッケージ名の変更

<a id="march-29-2022"></a>
### 2022. 03. 29. { #march-29-2022 }

<a id="march-29-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.3.0
    * デックス暗号化の改善
    * チートツールポリシーのマクロツールポリシー分離
    * 複数の署名に対する検証機能の追加
    * モードアプリ検出の改善
    * Unreal SDKの改善

* [iOS] 1.1.10
    * 保護作業のバグパッチ
    * 再署名スクリプト機能の改善
    * バージョン確認関連機能の改善
    * ガイド文書の修正

* [Gradle Plugin] 0.2.1
    * apkファイル探索ロジックの改善
    * プロテクターバージョン正規表現の改善

<a id="february-22-2022"></a>
### 2022. 02. 22. { #february-22-2022 }

<a id="february-22-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.2.0
    * アビューズアプリ検出機能の強化
    * 大容量アプリ保護作業の改善
    * マクロツール詳細情報の表示
    * CLIバグの修正
    * リアルタイムポリシー検出バグの修正
    * 保護作業失敗イシューの修正

* [iOS] 1.1.9
    * バージョン確認関連機能の改善
    * ガイド文書の修正

* [Gradle Plugin] 0.2.0
    * Gradle buildTypes、productFlavors、variants別オプションをサポート
    * overrideOutputFileオプションの追加

<a id="january-25-2022"></a>
### 2022. 01. 25. { #january-25-2022 }

<a id="january-25-2022-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.1.0
    * isolatedプロセス処理の改善
    * ハッキングツール検出機能の強化
    * 改ざん検出機能の強化

* [iOS] 1.1.8
    * クラス難読化新規機能の追加
    * ブラックリスト機能の改善

* [Gradle Plugin] 0.1.0
    * NHN AppGuard Gradle Plugin新規リリース

<a id="december-28-2021"></a>
### 2021. 12. 28. { #december-28-2021 }

<a id="december-28-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.9.0.0
    * AppGuardバージョンを指定して保護作業を行うように修正
    * ハッキングツール検出機能の強化
    * 遠隔制御パッケージ検出機能の改善
    * 特定エミュレータのクラッシュ問題を修正

* [iOS] 1.1.7
    * エンジンのセキュリティを強化

<a id="december-28-2021-bug-fixes"></a>
#### バグ修正
* [iOS] 1.1.7
    * プロテクターバグパッチ
    * リサイナーバグパッチ

<a id="2021-12-02"></a>
### 2021. 12. 02. { #2021-12-02 }

<a id="2021-12-02-bug-fixes"></a>
#### バグ修正
* [Android] 1.8.9.1
    * 警告ウィンドウのクラッシュを修正

<a id="november-23-2021"></a>
### 2021. 11. 23. { #november-23-2021 }

<a id="november-23-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.9.0
    * エンジンのセキュリティを強化
    * 新しい構造のCLIを配布

<a id="november-23-2021-november-23-2021-feature-updates"></a>
#### 機能改善/変更
* [iOS] 1.1.6
    * エンジンのセキュリティを強化
    * プロテクター機能の改善

<a id="november-4-2021"></a>
### 2021. 11. 04. { #november-4-2021 }

<a id="november-4-2021-bug-fixes"></a>
#### バグ修正
* [iOS] 1.1.5
    * プロテクターアプリネーム抽出関連バグの修正

<a id="october-26-2021"></a>
### 2021. 10. 26. { #october-26-2021 }

<a id="october-26-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.8.0
    * エンジンのセキュリティを強化
    * 暗号化API機能の改善

<a id="october-8-2021"></a>
### 2021. 10. 8. { #october-8-2021 }

<a id="october-8-2021-bug-fixes"></a>
#### バグ修正
* [Android] 1.8.7.1
    * Google Play Asset Deliveryサポート機能エラー修正
    
<a id="september-28-2021"></a>
### 2021. 9. 28. { #september-28-2021 }

<a id="september-28-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.7.0
    * エンジンのセキュリティを強化
    * Google SafetyNet悪性アプリ検知機能を追加

<a id="september-28-2021-september-28-2021-feature-updates"></a>
#### 機能改善/変更
* [iOS] 1.1.4
    * エンジンのセキュリティを強化
    * AppGuardプロテクターで保護機能を強化

<a id="september-1-2021"></a>
### 2021. 9. 1. { #september-1-2021 }

<a id="september-1-2021-bug-fixes"></a>
#### バグ修正
* [Android] 1.8.6.1
    * SQLiteを使用するUnityクラッシュを修正
    * Unrealの一部セキュリティ機能を修正
    
<a id="august-24-2021"></a>
### 2021. 8. 24. { #august-24-2021 }

<a id="august-24-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.6.0
    * エンジンのセキュリティを強化
    * Unrealのセキュリティ機能を改善
    * 保護作業時間の改善
    * CLI macOS M1をサポート
    
<a id="july-27-2021"></a>
### 2021. 7. 27. { #july-27-2021 }

<a id="july-27-2021-feature-updates"></a>
#### 機能改善/変更
* [iOS] 1.1.2
    * エンジンのセキュリティ性を強化
    * プロテクターのアップデート
    
* Webコンソールページを変更
    * アプリ保護作業が非同期に変更されました。

<a id="july-13-2021"></a>
### 2021. 7. 13. { #july-13-2021 }

<a id="july-13-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.5.1
    * Google Play Asset Delivery適用アプリサポート機能を改善

<a id="june-29-2021"></a>
### 2021. 6. 29. { #june-29-2021 }

<a id="june-29-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.5.0
    * エンジンのセキュリティを強化
    * Unityのセキュリティ機能を改善
    * CLIエラー処理を改善

* [iOS] 1.1.1
    * エンジンのセキュリティを強化
    * IAPアビューズ検知を追加
    * 内部テストロジックを改善
  
<a id="may-25-2021"></a>
### 2021. 5. 25. { #may-25-2021 }

<a id="may-25-2021-feature-updates"></a>
#### 機能改善/変更
* [iOS] 1.1.0
    * エンジンの性能改善
    * エンジンの安定化

<a id="may-24-2021"></a>
### 2021. 5. 24. { #may-24-2021 }

<a id="may-24-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.4.0
    * エンジンのセキュリティを強化
    * エンジンの安定化
    * Unity 2020の特定バージョンでクラッシュする問題を修正

<a id="may-11-2021"></a>
### 2021. 5. 11. { #may-11-2021 }

<a id="may-11-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.3.1
	* 遠隔制御検知機能を追加
	
<a id="april-27-2021"></a>
### 2021. 4. 27. { #april-27-2021 }

<a id="april-27-2021-feature-updates"></a>
#### 機能改善/変更
* サービス名を変更(AppGuard -> NHN AppGuard)
* [Android] 1.8.3.0
	* NHN AppGuardエンジンのセキュリティを強化
* [iOS] 1.0.18
	* 不正な行為を検知した後のハンドリングロジックを変更
	* NHN AppGuardエンジンのセキュリティを強化
	* NHN AppGuardエンジンの安定化

<a id="april-12-2021"></a>
### 2021. 4. 12. { #april-12-2021 }

<a id="april-12-2021-bug-fixes"></a>
#### バグ修正
* [iOS] 1.0.17
    * NHN AppGuardフッキング検知ロジックを追加

<a id="april-9-2021"></a>
### 2021. 4. 09. { #april-9-2021 }

<a id="april-9-2021-bug-fixes"></a>
#### バグ修正
* [Android] 1.8.2.2
	* Cocos2dエンジンエミュレータのクラッシュ問題を改善
	
<a id="march-31-2021"></a>
### 2021. 3. 31. { #march-31-2021 }

<a id="march-31-2021-bug-fixes"></a>
#### バグ修正
* [Android] 1.8.2.1
	* Facebook SDKの一部機能の競合エラーを修正
	
<a id="march-23-2021"></a>
### 2021. 3. 23. { #march-23-2021 }

<a id="march-23-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.2.0
    * NHN AppGuardエンジンのセキュリティを強化
* [iOS] 1.0.16
    * NHN AppGuardエンジンのセキュリティを強化

<a id="february-23-2021"></a>
### 2021. 2. 23. { #february-23-2021 }

<a id="february-23-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.1.0
    * CLI機能の改善
    * NHN AppGuardエンジンの安定化
    * NHN AppGuardエンジンのセキュリティを強化
* [iOS] 1.0.15
    * NHN AppGuardエンジンの安定化

<a id="january-26-2021"></a>
### 2021. 1. 26. { #january-26-2021 }

<a id="january-26-2021-feature-updates"></a>
#### 機能改善/変更
* [Android] 1.8.0.1
    * サードパーティストアサポート用オプションを追加
    * ゲームハック検知を高度化

<a id="december-29-2020"></a>
### 2020. 12. 29. { #december-29-2020 }

<a id="december-29-2020-bug-fixes"></a>
#### バグ修正
* NHN AppGuardエンジンの安定化

<a id="august-25-2020"></a>
### 2020. 08. 25. { #august-25-2020 }

<a id="august-25-2020-feature-updates"></a>
#### 機能改善/変更
* [Android]仮想環境検知機能を改善
* [iOS]脱獄検知を高度化
* [iOS]ゲームハック検知を高度化

<a id="july-28-2020"></a>
### 2020. 07. 28. { #july-28-2020 }

<a id="july-28-2020-feature-updates"></a>
#### 機能改善/変更
* [Android]仮想環境検知機能を追加
* [iOS]脱獄検知を高度化
* [iOS]強制終了を高度化
* [iOS]ブラックリスト遮断機能を追加

<a id="july-28-2020-bug-fixes"></a>
#### バグ修正
* [Android] Unity Monoエミュレータ7バージョンのクラッシュイシューを修正
* [iOS] GAMEPOT(ゲームポット)フレームワーク衝突エラーを修正

<a id="june-23-2020"></a>
### 2020. 06. 23. { #june-23-2020 }

<a id="june-23-2020-feature-updates"></a>
#### 機能改善/変更
* NHN AppGuard容量縮小を改善
* NHN AppGuardエンジンのセキュリティを強化

<a id="june-23-2020-bug-fixes"></a>
#### バグ修正
* Unrealエンジンの保護バグを修正

<a id="may-26-2020"></a>
### 2020. 05. 26. { #may-26-2020 }

<a id="may-26-2020-feature-updates"></a>
#### 機能改善/変更
* 難読化申請機能を追加

<a id="may-26-2020-bug-fixes"></a>
#### バグ修正
* NHN AppGuardエンジンの安定化

<a id="april-28-2020"></a>
### 2020. 04. 28. { #april-28-2020 }

<a id="april-28-2020-feature-updates"></a>
#### 機能改善/変更
* SSL Pinning攻撃検知機能を追加

<a id="march-24-2020"></a>
### 2020. 03. 24. { #march-24-2020 }

<a id="march-24-2020-feature-updates"></a>
#### 機能改善/変更
* Android 7.0バージョンエミュレータをサポート

<a id="february-25-2020"></a>
### 2020. 02. 25. { #february-25-2020 }

<a id="february-25-2020-feature-updates"></a>
#### 機能改善/変更
* 改ざんアプリ対応ロジックを追加

<a id="january-21-2020"></a>
### 2020. 01. 21. { #january-21-2020 }

<a id="january-21-2020-feature-updates"></a>
#### 機能改善/変更
* NHN AppGuardエンジンの安定化

<a id="december-24-2019"></a>
### 2019. 12. 24. { #december-24-2019 }

<a id="december-24-2019-feature-updates"></a>
#### 機能改善/変更
* Cocos2d-xエンジン暗号化モジュールを追加

<a id="november-26-2019"></a>
### 2019. 11. 26. { #november-26-2019 }

<a id="november-26-2019-feature-updates"></a>
#### 機能改善/変更
* NHN AppGuardバージョン選択機能を追加

<a id="november-26-2019-bug-fixes"></a>
#### バグ修正
* 文字列難読化機能のバグを修正

<a id="october-29-2019"></a>
### 2019. 10. 29. { #october-29-2019 }

<a id="october-29-2019-feature-updates"></a>
#### 機能改善/変更
* アンチデバッグ機能を改善
* ゲームハック検知機能を改善
* メモリ検索検知機能を追加

<a id="october-29-2019-bug-fixes"></a>
#### バグ修正
* NHN AppGuardエンジンの安定化

<a id="september-24-2019"></a>
### 2019. 09. 24. { #september-24-2019 }

<a id="september-24-2019-feature-updates"></a>
#### 機能改善/変更
* NHN AppGuard Android Qの安定性が向上

<a id="august-27-2019"></a>
### 2019. 08. 27. { #august-27-2019 }

<a id="august-27-2019-feature-updates"></a>
#### 機能改善/変更
* Android Qをサポート
* Webコンソール条件遮断およびブラックリスト機能を追加
* NHN AppGuard iOSリアルタイムポリシー設定機能を追加
* 機械学習基盤、Unityゲームのマクロ検知機能追加およびWebコンソールをサポート
* NHN AppGuardモジュールの整合性検証を改善
* Webコンソールの監査ログ機能を追加

<a id="july-23-2019"></a>
### 2019. 07. 23. { #july-23-2019 }

<a id="july-23-2019-feature-updates"></a>
#### 機能改善/変更
* Android App Bundleをサポート
* Unityライブラリパッキング機能を追加
* Unity MONOマクロ探知機能を追加

<a id="july-23-2019-bug-fixes"></a>
#### バグ修正
* dex整合性チェックのバグを修正

<a id="june-25-2019"></a>
### 2019. 06. 25. { #june-25-2019 }

<a id="june-25-2019-feature-updates"></a>
#### 機能改善/変更
* アプリガード64bitライブラリ保護機能を強化
* アプリガード制御フロー難読化機能を追加
* クラッシュレポート機能を追加

<a id="june-25-2019-bug-fixes"></a>
#### バグ修正
* アプリガードパス権限変更チェックのバグを修正

<a id="may-28-2019"></a>
### 2019. 05. 28. { #may-28-2019 }

<a id="may-28-2019-feature-updates"></a>
#### 機能改善/変更
* Googleのガイドに従い、defaultで64bitのライブラリを追加するように変更
	* 従来の方式：ユーザーがABIチェックして32または64bitライブラリを追加
	* 変更方式：32/64bitライブラリの両方を追加
* マクロ探知機能を改善

<a id="may-28-2019-bug-fixes"></a>
#### バグ修正
* [Android]エミュレータ未探知バグを修正
* [iOS]整合性チェックのバグを修正

<a id="april-23-2019"></a>
### 2019.04.23 { #april-23-2019 }

<a id="april-23-2019-feature-updates"></a>
#### function upgrade/change
* Add Unity IL2CPP method encryption function
	* Applied with CLI option "--il2cpp-encryption"
* Add Unity MONO method encryption function
	* Applied to NHN AppGuard level3
* Add Emulator Detection Pattern
	* Memu Player latest version(6.1.1)

<a id="april-23-2019-bug-fixes"></a>
#### bug fix
* Fixed a multi-deck duplicate installation error on Android OS 4.X version

<a id="march-26-2019"></a>
### 2019.03.26 { #march-26-2019 }

<a id="march-26-2019-feature-updates"></a>
#### function upgrade/change
* Apply Unity Library obfuscation
* Add NHN AppGuard API/Method obfuscation function

<a id="february-26-2019"></a>
### 2019.02.26 { #february-26-2019 }

<a id="february-26-2019-feature-updates"></a>
#### function upgrade/change
* Apply NHN AppGuard self-obfuscation
* Unity latest version(2018) compatibility improvement
	* MONO, IL2CPP build encryption function
* Add Emulator Detection Pattern
	* NOX latest version(6.2.7.0)

<a id="january-29-2019"></a>
### 2019.01.29 { #january-29-2019 }

<a id="january-29-2019-feature-updates"></a>
#### function upgrade/change
* Unity latest version compatibility improvement

<a id="december-27-2018"></a>
### 2018.12.27 { #december-27-2018 }

<a id="december-27-2018-feature-updates"></a>
#### function upgrade/change
* Enhanced self-protection
* Add Dex Loader Obfuscation Function
* Add Hooking Detection Pattern
* Add Rooting Detection Pattern
* Add Emulator Detection Pattern
* Enhanced Unity IL2CPP Build Protection Function
	* IL2CPP Dumper Tool Prevention

<a id="november-27-2018"></a>
### 2018.11.27 { #november-27-2018 }

<a id="november-27-2018-feature-updates"></a>
#### function upgrade/change
* Enhanced encryption function for Unity il2cpp build
* Enhanced Hooking Detection Function

<a id="october-23-2018"></a>
### 2018.10.23 { #october-23-2018 }

<a id="october-23-2018-feature-updates"></a>
#### function upgrade/change
* Add function to applied NHN AppGuard verification
* Enhanced Rooting Detection
* Enhanced Debugging Detection

<a id="august-28-2018"></a>
### 2018.08.28 { #august-28-2018 }

<a id="august-28-2018-bug-fixes"></a>
#### bug fix
* NHN AppGuard Unity SDK
	* Fixed an error that editor linkage in Unity 5 or earlier

<a id="july-24-2018"></a>
### 2018.07.24 { #july-24-2018 }

<a id="july-24-2018-feature-updates"></a>
#### function upgrade/change
* Support Unreal Engine 4
    * Support protection for game code of Unreal Engine 4

<a id="june-26-2018"></a>
### 2018.06.26 { #june-26-2018 }

<a id="june-26-2018-feature-updates"></a>
#### function upgrade/change
* Improved compatibility in Android P(9.0)
* NHN AppGuard Unity SDK
    * Support UNITY 2018

<a id="may-29-2018"></a>
### 2018.05.29 { #may-29-2018 }

<a id="may-29-2018-feature-updates"></a>
#### function upgrade/change
* Enhanced Memory Manipulation Detection
    * Enhanced detection of memory manipulation using cheating tool
<a id="may-29-2018-bug-fixes"></a>
#### bug fix
* Fixed an error that the anti-debugging function applied to Level 3 consumed battery excessively

<a id="april-24-2018"></a>
### 2018.04.24 { #april-24-2018 }

<a id="april-24-2018-feature-updates"></a>
#### function upgrade/change
* Support game code encryption for Unity il2cpp build
    * Supports il2cpp build by extending game code encryption, which was only supported in Mono builds
* Improved anti-debugging(App analysis prevention technology)
    * Enhanced functionality and stability

<a id="february-20-2018"></a>
### 2018.02.20 { #february-20-2018 }

<a id="february-20-2018-bug-fixes"></a>
#### bug fix
* Fixed an error that the app with NHN AppGuard Level2 app was not running properly in Momo App Player version 1.2.1

<a id="january-24-2018"></a>
### 2018.01.24 { #january-24-2018 }

<a id="january-24-2018-bug-fixes"></a>
#### bug fix
* Fixed an error that would not run on Android 8.x specific devices if Level2 was applied to an app developed with Unity2017 version

<a id="december-21-2017"></a>
### 2017.12.21 { #december-21-2017 }

<a id="december-21-2017-feature-updates"></a>
#### function upgrade/change
* Enhanced Unity Speed Hack Detection
<a id="december-21-2017-bug-fixes"></a>
#### bug fix
* Fixed an error that occurred during the protection operation in the latest version of Unity Personal (2017.x.x version)
* Fixed an apk increase in size unnecessarily when protecting multi-dex (3 or more) apps

<a id="august-24-2017"></a>
### 2017.08.24 { #august-24-2017 }

<a id="august-24-2017-feature-updates"></a>
#### function upgrade/change
* Removal of charge/free selection window (Apply September 1)
* Support Android 8.0
<a id="august-24-2017-bug-fixes"></a>
#### bug fix
* Modify the module(CLIUpdater.exe) that automatically updates the NHN AppGuard CLI(AppGuard.exe), required update
    * Requires CLI of latest SDK (If you don't want automatic update function, add --noUpdate as CLI option)

<a id="july-20-2017"></a>
### 2017.07.20 { #july-20-2017 }

<a id="july-20-2017-feature-updates"></a>
#### function upgrade/change
* Fixed an error that Callback function is not called when detecting on Level 1~3
* Add optimization function option for Level 1~3

<a id="june-22-2017"></a>
### 2017.06.22 { #june-22-2017 }

<a id="june-22-2017-feature-updates"></a>
#### function upgrade/change
* App that use jni for x86_64, arm64-v8a will have an NHN AppGuard module for that architecture.
* Divide path to download SDK for Android, iOS(Beta)
* The iOS(Beta) version is free for all users
* Enhancement of the module detection function of the NHN AppGuard itself
* Extend Unity3D DLL File Encrpyt
    * Unitiy Basic DLL files as well as DLL files separately added are also encrypted. (Level 3)

<a id="may-25-2017"></a>
### 2017.05.25 { #may-25-2017 }

<a id="may-25-2017-feature-updates"></a>
#### function upgrade/change
* Simplify application Android version
    * before : Protection work after SDK linkage
    * after : You can apply only protection work (If user ID identifier registration is necessary, it is necessary to selectively be linked SDK, but it becomes simpler than before.)
* Restructure App Protection Level
    * Level 1 : Abnormal behavior and pattern based basic security behavior detect about app
    * Level 2 : Level1 + Enhanced security function such as Encrypt source code, Prevent to modify App, etc.
    * Level 3 : Level2 + More Enhanced security function(Because stability check may be required for certain services, it is recommended to use it only if you have received a separate guide)
    * Level ex : Version of must required SDK be linked, Provide security between level1 to level2(it is recommended when conflict other security solution)

<a id="april-20-2017"></a>
### 2017.04.20 { #april-20-2017 }

<a id="april-20-2017-bug-fixes"></a>
#### bug fix
* Fix some app intall issues when applying app modification prevent function
* Enhance compatibility with apps that use external resources when applying app modification prevent function
* Fix app guard build error in version 5.6 of Unity3d

<a id="april-4-2017"></a>
### 2017.04.04 { #april-4-2017 }

<a id="april-4-2017-bug-fixes"></a>
#### bug fix
* Fix multidex bug of app modification prevent function

<a id="march-23-2017"></a>
### 2017.03.23 { #march-23-2017 }

<a id="march-23-2017-feature-updates"></a>
#### function upgrade/change
* [SDK] Add function of supporting Unity3d il2cpp build

<a id="march-23-2017-bug-fixes"></a>
#### bug fix
* Fix an issue where blocking logic was not executed normally when policy update was delayed
* Fix an issue where unnecessary exceptions were output to Android logs

<a id="january-19-2017"></a>
### 2017.01.19 { #january-19-2017 }

<a id="january-19-2017-feature-updates"></a>
#### function upgrade/change
* [SDK] New NHN AppGuard iOS SDK deploy
* Enhance function of apk modification prevention

<a id="january-19-2017-bug-fixes"></a>
#### bug fix
* Fix synchronization error between policy settings and detection logic
* Fix crash issue based on network conditions (Update log transfer library)

<a id="december-22-2016"></a>
### 2016.12.22 { #december-22-2016 }

<a id="december-22-2016-feature-updates"></a>
#### function upgrade/change
* Add detection pattern of cheating tool
* [Console] Add information of NHN AppGuard engine version in detection logs

<a id="december-8-2016"></a>
### 2016.12.08 { #december-8-2016 }

<a id="december-8-2016-feature-updates"></a>
#### function upgrade/change
* Add detection pattern of rooting
* [SDK] Add multi-lingual setting API at message when blocking in NHN AppGuard

<a id="december-8-2016-bug-fixes"></a>
#### bug fix
* [Console] Fix an error that the protection failed but appears to be successful on the web console

<a id="november-24-2016"></a>
### 2016.11.24 { #november-24-2016 }

<a id="november-24-2016-feature-updates"></a>
#### function upgrade/change

* [SDK] Update NHN AppGuard SDK(tcag.jar)
* [Console] Add Notice in NHN AppGuard Web Console

<a id="october-20-2016"></a>
### 2016.10.20 { #october-20-2016 }

<a id="october-20-2016-feature-updates"></a>
#### function upgrade/change

* [API] Change parameter of NHN AppGuard SDK linkage function
* [SDK] Add auto update function of NHN AppGuard CLI(Command Line Build) tool

<a id="september-29-2016"></a>
### 2016.09.29 { #september-29-2016 }

<a id="september-29-2016-bug-fixes"></a>
#### bug fix

* [Console] Fix window of agree terms and link error
* [Console] Fix UI break when protecting app

<a id="september-8-2016"></a>
### 2016.09.08 { #september-8-2016 }

<a id="september-8-2016-bug-fixes"></a>
#### bug fix

* Fix false positives of speed hack detection in Android 7.0

<a id="august-18-2016"></a>
### 2016.08.18 { #august-18-2016 }

<a id="august-18-2016-feature-updates"></a>
#### function upgrade/change

* Update detection pattern
* Support Android N
* [Console] Add function to searching iOS logs
* [Console] Add function to change the number of logs displayed on a page (fixed 15 -> select 15/30/50)

<a id="august-4-2016"></a>
### 2016.08.04 { #august-4-2016 }

<a id="august-4-2016-feature-updates"></a>
#### function upgrade/change

* Enhance detection of speed manipulation

<a id="august-4-2016-bug-fixes"></a>
#### bug fix

* Fix some errors due to Timer
