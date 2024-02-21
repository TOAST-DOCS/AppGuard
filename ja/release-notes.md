## Security > NHN AppGuard > リリースノート

### 2024. 02. 23.
* [Android] 1.10.5.5
    * 悪性行為検出ポップアップデザイン改善
    * 보안성 개선
    * TeamViewer Host(Code: 1401)検出を追加
    * AnyDesk(Code: 1403)検出を追加
    * Auto Click - Automatic Clicker(Code: 1708)検出を追加
    * Auto Tapper: Auto Clicker(Code: 1709)検出を追加
    * 암호화 적용 시 용량이 크게 증가하는 이슈 수정
* [Unity] 0.4.3
    * (iOS) 탐지 알림창이 나타나지 않는 이슈 수정
    * (iOS) iOS SDK 1.3.16アップデート
* [iOS] 1.3.16
    * [Unity] iOS 15 환경에서 앱 실행 시 비정상 종료 이슈 수정

### 2024. 02. 16.
* [Unity] 0.4.2
    * (iOS) NHN AppGuard iOSビルドの問題を修正
        * Package Manager使用時、iOSビルドが失敗する問題を修正しました。
    * (iOS) iOS SDK 1.3.15アップデート

### 2024. 02. 15.
* [iOS] 1.3.15
    * iOS最小サポートバージョンのアップ(iOS 11以上)
    * i386, armv7s, armv7アーキテクチャのサポート終了
    * 基本検出通知ウィンドウの改善
    * 個人情報保護マニフェストを追加
    * 署名の追加(NHN Cloud Corp.)

### 2024. 01. 23.
* [Android] 1.10.5.3
    * 難読化機能の改善
        * 関数呼び出し非表示(Hide Call)機能を改善します。

### 2024. 01. 09.
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
    
### 2023. 12. 28.
* [Android] 1.10.5.1
    * StackOverflowErrorの問題を修正

### 2023. 12. 19.
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

### 2023. 12. 06.
* [iOS] 1.3.12
    * エンジンセキュリティの強化
* [Unity] 0.3.1
    * (iOS) iOS SDK 1.3.12アップデート
    
### 2023. 11. 24.
* [Android] 1.10.4.1
    * NHN AppGuardセキュリティ脆弱性の改善

### 2023. 11. 21.
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

### 2023. 10. 24.
* [iOS] 1.3.10
    * 難読化プラグインが適用されたUnityアプリを保護する際に保護に失敗する問題を修正
* [Unity] 0.2.2
    * iOS SDK 1.3.10アップデート

### 2023. 10. 19.
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

### 2023. 09. 26.
* [Android] 1.10.3.2
    * 署名改ざん誤検知を修正
        * アプリ保護時に使用するkeystoreの署名を改ざんと判断する問題を修正しました。
    * 署名の重複を確認
        * `--as` オプションとkeystoreの署名が同じ場合、エラーを返すように修正
* [Unity] 0.2.0
    * Certificate Fingerprints無効化オプションを追加
* [Gradle Plugin] 1.2.0
    * Certificate Fingerprintsオプションを追加

### 2023. 09. 13.
* [Android] 1.10.3.1
    * アプリ署名改ざんの誤検知イシューを修正
* [Unity] 0.1.8
    * iOS SDK 1.3.8アップデート

### 2023. 09. 12.
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

### 2023. 08. 17.
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

### 2023. 07. 21.
* [Android] 1.10.2.1
    * アプリ起動時の異常終了の問題を修正
    * 難読化の改善
        * 難読化対象メソッドが65Kを超えると保護作業に失敗する問題に対応
    * ポリシー改ざん対応改善

### 2023. 07. 11.
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

### 2023. 07. 06.
* [Android] 1.10.1.2
    * ルート化検出機能の強化
    * 安定性改善

### 2023. 06. 16.
* [Unity] 0.1.5
    * iOS SDK 1.3.5アップデート

### 2023. 06. 15.
* [iOS] 1.3.5
    * Info.plist改ざん誤検知の改善
* [iOS] 1.3.4
    * エンジンセキュリティの強化
* [Unity] 0.1.4
    * iOS SDK 1.3.4アップデート

### 2023. 06. 13.
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

### 2023. 05. 30.
* [Android] 1.10.0.5
    * 識別子難読化エラーを修正

* [Gradle Plugin] 1.1.1
    * extraOptionsエラーを修正

### 2023. 05. 11.
* [iOS] 1.3.2
    * エンジンセキュリティの強化(Unity)

* [Unity] 0.1.2
    * Linux OSでCLI保護作業が実行されるように改善
    * iOS SDK 1.3.2アップデート

### 2023. 05. 02.
* [Android] 1.10.0.4
    * 権限改ざん(400_106_0)の誤検知問題を修正

### 2023. 04. 25.
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

### 2023. 04. 14.
* [Android] 1.10.0.2
    * 32bitエミュレータで正常に終了しないエラーを修正
    * 文字列難読化の改善

### 2023. 04. 10.
* [Android] 1.10.0.1
    * 文字列暗号化エラーを修正

### 2023. 03. 28.
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

### 2023. 02. 28.
* [Android] 1.9.13.5
    * アビューズアプリライセンス検出の改善
    * 条件ブロックポリシーが適用されない問題を修正
    * Unityアプリ実行時にクラッシュが発生する問題を修正
    * Unity整合性検証の偽陰性を修正(405_49_0)

* [iOS] 1.2.10
    * エンジンセキュリティの強化
    * iOS 15互換性の改善

### 2023. 02. 08.
* [Android] 1.9.13.1
    * DEX難読化イシューを修正

### 2023. 01. 31.
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

### 2022. 12. 27.
* [Android] 1.9.12.0
    * クライアントポリシーのサポート終了
    * 基本ポリシー機能の追加
    * 警告ウィンドウ未発生の問題
    * DEX暗号化クラッシュ問題の修正
    
* [iOS] 1.2.8
    * エンジンセキュリティの強化
    * iOS 16互換性の改善

### 2022. 12. 13.
* [Android] 1.9.11.2
    * API表示の問題の修正
    * LifecycleCallbackの問題の修正
    * 特定保護機能クラッシュおよび偽陰性問題の修正
    * x86クラッシュ問題の修正

### 2022. 12. 07.
* [Android] 1.9.11.1
    * 改ざん偽陰性問題の修正

### 2022. 11. 29.
* [Android] 1.9.11.0
    * フレームドロップ問題の修正
    * SSLピンニングバイパス未検出問題の修正
    * Google Playゲームズのサポート
    * クラッシュ問題の修正

* [iOS] 1.2.7
    * APIフック検出ロジックの強化
    * ポリシー関連イシューの解決
    * AppGuard CLI機能の改善

### 2022.11.09.

* [Android] 1.9.10.2
    * バックグラウンドクラッシュ問題の修正

### 2022.11.02.

* [Android] 1.9.10.1
    * クラッシュ問題の修正

### 2022. 10. 28.
* [iOS] 1.2.6
    * エンジンセキュリティの強化

### 2022. 10. 25.
* [Android] 1.9.10.0
    * エミュレータ検出機能の強化
    * チートツール検出機能の強化

### 2022. 10. 14.
* [Android] 1.9.9.2
    * LDPlayer4 64bitエミュレータのサポート
    * 韓国語警告ウィンドウの追加
    * 初期化速度改善
    * エミュレータクラッシュ問題の修正
    * エンジンセキュリティの強化

### 2022. 10. 07.
* [Android] 1.9.9.1
    * 当該バージョンの削除

### 2022. 10. 04.
* [Android] 1.9.9.0
    * 当該バージョンの削除

* [iOS] 1.2.5
    * エンジンセキュリティの強化
    * ネットワーク関連バグパッチ
    * リパッケージ関連セキュリティ強化

### 2022. 09.08.
* [Android] 1.9.8.1
    * マニフェスト問題の修正

### 2022. 08. 23.
* [Android] 1.9.8.0
    * クレマ端末mpサポート 
    * BlueStacks、Nox、LDPlayer9 64bitエミュレータのサポート
    * SafetyNetのサポート中止
    * エンジンセキュリティの強化
    * Unity保護作業問題の修正

* [iOS] 1.2.4
    * エンジンセキュリティの強化
    * tweak検出機能の追加

### 2022. 07. 26.
* [Android] 1.9.7.0
    * エンジンセキュリティの強化
    * マニフェストバグの修正
    * 未検出バグの修正

* [iOS] 1.2.3
    * エンジンセキュリティの強化
    * Device ID関連APIの追加

* [Gradle Plugin] 1.0.2
    * CLIコンソールログ出力

### 2022. 07. 06.
* [Android] 1.9.6.1
    * ANR問題の修正
    * エンジンセキュリティの強化

### 2022. 06. 30

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

### 2022. 05. 24.

#### 機能改善/変更
* [Android] 1.9.5.0
    * ブラックリスト遮断機能の改善
    * 一部クラッシュ問題の修正
    * BlueStacks(BlueStacks)エミュレータ検証の強化
    * エンジンセキュリティの強化

* [iOS] 1.2.1
    * NHN AppGuard iOS CLIの追加

* [Console]検知ログ検索可能期間の変更(30日→90日)

### 2022. 05. 10.

#### 機能改善/変更
* [Android] 1.9.4.1
    * ANRおよびクラッシュ問題の改善
    * コールバックデータの改善
    * エミュレータ検知機能の強化
    * エンジンセキュリティの強化

### 2022. 04. 26.

#### 機能改善/変更
* [Android] 1.9.4.0
    * 該当バージョンの削除

* [iOS] 1.2.0
    * Unityフレームワーク関連セキュリティの強化
    * エンジンセキュリティの強化

* [Gradle Plugin] 1.0.0
    * groupId、パッケージ名の変更

### 2022. 03. 29.

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

### 2022. 02. 22.

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

### 2022. 01. 25.

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

### 2021. 12. 28.

#### 機能改善/変更
* [Android] 1.9.0.0
    * AppGuardバージョンを指定して保護作業を行うように修正
    * ハッキングツール検出機能の強化
    * 遠隔制御パッケージ検出機能の改善
    * 特定エミュレータのクラッシュ問題を修正

* [iOS] 1.1.7
    * エンジンのセキュリティを強化

#### バグ修正
* [iOS] 1.1.7
    * プロテクターバグパッチ
    * リサイナーバグパッチ

### 2021. 12. 02.

#### バグ修正
* [Android] 1.8.9.1
    * 警告ウィンドウのクラッシュを修正

### 2021. 11. 23.

#### 機能改善/変更
* [Android] 1.8.9.0
    * エンジンのセキュリティを強化
    * 新しい構造のCLIを配布

#### 機能改善/変更
* [iOS] 1.1.6
    * エンジンのセキュリティを強化
    * プロテクター機能の改善

### 2021. 11. 04.

#### バグ修正
* [iOS] 1.1.5
    * プロテクターアプリネーム抽出関連バグの修正

### 2021. 10. 26.

#### 機能改善/変更
* [Android] 1.8.8.0
    * エンジンのセキュリティを強化
    * 暗号化API機能の改善

### 2021. 10. 8.

#### バグ修正
* [Android] 1.8.7.1
    * Google Play Asset Deliveryサポート機能エラー修正
    
### 2021. 9. 28.

#### 機能改善/変更
* [Android] 1.8.7.0
    * エンジンのセキュリティを強化
    * Google SafetyNet悪性アプリ検知機能を追加

#### 機能改善/変更
* [iOS] 1.1.4
    * エンジンのセキュリティを強化
    * AppGuardプロテクターで保護機能を強化

### 2021. 9. 1.

#### バグ修正
* [Android] 1.8.6.1
    * SQLiteを使用するUnityクラッシュを修正
    * Unrealの一部セキュリティ機能を修正
    
### 2021. 8. 24.

#### 機能改善/変更
* [Android] 1.8.6.0
    * エンジンのセキュリティを強化
    * Unrealのセキュリティ機能を改善
    * 保護作業時間の改善
    * CLI macOS M1をサポート
    
### 2021. 7. 27.

#### 機能改善/変更
* [iOS] 1.1.2
    * エンジンのセキュリティ性を強化
    * プロテクターのアップデート
    
* Webコンソールページを変更
    * アプリ保護作業が非同期に変更されました。

### 2021. 7. 13.

#### 機能改善/変更
* [Android] 1.8.5.1
    * Google Play Asset Delivery適用アプリサポート機能を改善

### 2021. 6. 29.

#### 機能改善/変更
* [Android] 1.8.5.0
    * エンジンのセキュリティを強化
    * Unityのセキュリティ機能を改善
    * CLIエラー処理を改善

* [iOS] 1.1.1
    * エンジンのセキュリティを強化
    * IAPアビューズ検知を追加
    * 内部テストロジックを改善
  
### 2021. 5. 25.

#### 機能改善/変更
* [iOS] 1.1.0
    * エンジンの性能改善
    * エンジンの安定化

### 2021. 5. 24.

#### 機能改善/変更
* [Android] 1.8.4.0
    * エンジンのセキュリティを強化
    * エンジンの安定化
    * Unity 2020の特定バージョンでクラッシュする問題を修正

### 2021. 5. 11.

#### 機能改善/変更
* [Android] 1.8.3.1
	* 遠隔制御検知機能を追加
	
### 2021. 4. 27.

#### 機能改善/変更
* サービス名を変更(AppGuard -> NHN AppGuard)
* [Android] 1.8.3.0
	* NHN AppGuardエンジンのセキュリティを強化
* [iOS] 1.0.18
	* 不正な行為を検知した後のハンドリングロジックを変更
	* NHN AppGuardエンジンのセキュリティを強化
	* NHN AppGuardエンジンの安定化

### 2021. 4. 12.

#### バグ修正
* [iOS] 1.0.17
    * NHN AppGuardフッキング検知ロジックを追加

### 2021. 4. 09.

#### バグ修正
* [Android] 1.8.2.2
	* Cocos2dエンジンエミュレータのクラッシュ問題を改善
	
### 2021. 3. 31.

#### バグ修正
* [Android] 1.8.2.1
	* Facebook SDKの一部機能の競合エラーを修正
	
### 2021. 3. 23.

#### 機能改善/変更
* [Android] 1.8.2.0
    * NHN AppGuardエンジンのセキュリティを強化
* [iOS] 1.0.16
    * NHN AppGuardエンジンのセキュリティを強化

### 2021. 2. 23.

#### 機能改善/変更
* [Android] 1.8.1.0
    * CLI機能の改善
    * NHN AppGuardエンジンの安定化
    * NHN AppGuardエンジンのセキュリティを強化
* [iOS] 1.0.15
    * NHN AppGuardエンジンの安定化

### 2021. 1. 26.

#### 機能改善/変更
* [Android] 1.8.0.1
    * サードパーティストアサポート用オプションを追加
    * ゲームハック検知を高度化

### 2020. 12. 29.

#### バグ修正
* NHN AppGuardエンジンの安定化

### 2020. 08. 25.

#### 機能改善/変更
* [Android]仮想環境検知機能を改善
* [iOS]脱獄検知を高度化
* [iOS]ゲームハック検知を高度化

### 2020. 07. 28.

#### 機能改善/変更
* [Android]仮想環境検知機能を追加
* [iOS]脱獄検知を高度化
* [iOS]強制終了を高度化
* [iOS]ブラックリスト遮断機能を追加

#### バグ修正
* [Android] Unity Monoエミュレータ7バージョンのクラッシュイシューを修正
* [iOS] GAMEPOT(ゲームポット)フレームワーク衝突エラーを修正

### 2020. 06. 23.

#### 機能改善/変更
* NHN AppGuard容量縮小を改善
* NHN AppGuardエンジンのセキュリティを強化

#### バグ修正
* Unrealエンジンの保護バグを修正

### 2020. 05. 26.

#### 機能改善/変更
* 難読化申請機能を追加

#### バグ修正
* NHN AppGuardエンジンの安定化

### 2020. 04. 28.

#### 機能改善/変更
* SSL Pinning攻撃検知機能を追加

### 2020. 03. 24.

#### 機能改善/変更
* Android 7.0バージョンエミュレータをサポート

### 2020. 02. 25.

#### 機能改善/変更
* 改ざんアプリ対応ロジックを追加

### 2020. 01. 21.

#### 機能改善/変更
* NHN AppGuardエンジンの安定化

### 2019. 12. 24.

#### 機能改善/変更
* Cocos2d-xエンジン暗号化モジュールを追加

### 2019. 11. 26.

#### 機能改善/変更
* NHN AppGuardバージョン選択機能を追加

#### バグ修正
* 文字列難読化機能のバグを修正

### 2019. 10. 29.

#### 機能改善/変更
* アンチデバッグ機能を改善
* ゲームハック検知機能を改善
* メモリ検索検知機能を追加

#### バグ修正
* NHN AppGuardエンジンの安定化

### 2019. 09. 24.

#### 機能改善/変更
* NHN AppGuard Android Qの安定性が向上

### 2019. 08. 27.

#### 機能改善/変更
* Android Qをサポート
* Webコンソール条件遮断およびブラックリスト機能を追加
* NHN AppGuard iOSリアルタイムポリシー設定機能を追加
* 機械学習基盤、Unityゲームのマクロ検知機能追加およびWebコンソールをサポート
* NHN AppGuardモジュールの整合性検証を改善
* Webコンソールの監査ログ機能を追加

### 2019. 07. 23.

#### 機能改善/変更
* Android App Bundleをサポート
* Unityライブラリパッキング機能を追加
* Unity MONOマクロ探知機能を追加

#### バグ修正
* dex整合性チェックのバグを修正

### 2019. 06. 25.

#### 機能改善/変更
* アプリガード64bitライブラリ保護機能を強化
* アプリガード制御フロー難読化機能を追加
* クラッシュレポート機能を追加

#### バグ修正
* アプリガードパス権限変更チェックのバグを修正

### 2019. 05. 28.

#### 機能改善/変更
* Googleのガイドに従い、defaultで64bitのライブラリを追加するように変更
	* 従来の方式：ユーザーがABIチェックして32または64bitライブラリを追加
	* 変更方式：32/64bitライブラリの両方を追加
* マクロ探知機能を改善

#### バグ修正
* [Android]エミュレータ未探知バグを修正
* [iOS]整合性チェックのバグを修正

### 2019.04.23

#### function upgrade/change
* Add Unity IL2CPP method encryption function
	* Applied with CLI option "--il2cpp-encryption"
* Add Unity MONO method encryption function
	* Applied to NHN AppGuard level3
* Add Emulator Detection Pattern
	* Memu Player latest version(6.1.1)

#### bug fix
* Fixed a multi-deck duplicate installation error on Android OS 4.X version

### 2019.03.26

#### function upgrade/change
* Apply Unity Library obfuscation
* Add NHN AppGuard API/Method obfuscation function

### 2019.02.26

#### function upgrade/change
* Apply NHN AppGuard self-obfuscation
* Unity latest version(2018) compatibility improvement
	* MONO, IL2CPP build encryption function
* Add Emulator Detection Pattern
	* NOX latest version(6.2.7.0)

### 2019.01.29

#### function upgrade/change
* Unity latest version compatibility improvement

### 2018.12.27

#### function upgrade/change
* Enhanced self-protection
* Add Dex Loader Obfuscation Function
* Add Hooking Detection Pattern
* Add Rooting Detection Pattern
* Add Emulator Detection Pattern
* Enhanced Unity IL2CPP Build Protection Function
	* IL2CPP Dumper Tool Prevention

### 2018.11.27

#### function upgrade/change
* Enhanced encryption function for Unity il2cpp build
* Enhanced Hooking Detection Function

### 2018.10.23

#### function upgrade/change
* Add function to applied NHN AppGuard verification
* Enhanced Rooting Detection
* Enhanced Debugging Detection

### 2018.08.28

#### bug fix
* NHN AppGuard Unity SDK
	* Fixed an error that editor linkage in Unity 5 or earlier

### 2018.07.24

#### function upgrade/change
* Support Unreal Engine 4
    * Support protection for game code of Unreal Engine 4

### 2018.06.26

#### function upgrade/change
* Improved compatibility in Android P(9.0)
* NHN AppGuard Unity SDK
    * Support UNITY 2018

### 2018.05.29

#### function upgrade/change
* Enhanced Memory Manipulation Detection
    * Enhanced detection of memory manipulation using cheating tool
#### bug fix
* Fixed an error that the anti-debugging function applied to Level 3 consumed battery excessively

### 2018.04.24

#### function upgrade/change
* Support game code encryption for Unity il2cpp build
    * Supports il2cpp build by extending game code encryption, which was only supported in Mono builds
* Improved anti-debugging(App analysis prevention technology)
    * Enhanced functionality and stability

### 2018.02.20

#### bug fix
* Fixed an error that the app with NHN AppGuard Level2 app was not running properly in Momo App Player version 1.2.1

### 2018.01.24

#### bug fix
* Fixed an error that would not run on Android 8.x specific devices if Level2 was applied to an app developed with Unity2017 version

### 2017.12.21

#### function upgrade/change
* Enhanced Unity Speed Hack Detection
#### bug fix
* Fixed an error that occurred during the protection operation in the latest version of Unity Personal (2017.x.x version)
* Fixed an apk increase in size unnecessarily when protecting multi-dex (3 or more) apps

### 2017.08.24

#### function upgrade/change
* Removal of charge/free selection window (Apply September 1)
* Support Android 8.0
#### bug fix
* Modify the module(CLIUpdater.exe) that automatically updates the NHN AppGuard CLI(AppGuard.exe), required update
    * Requires CLI of latest SDK (If you don't want automatic update function, add --noUpdate as CLI option)

### 2017.07.20

#### function upgrade/change
* Fixed an error that Callback function is not called when detecting on Level 1~3
* Add optimization function option for Level 1~3

### 2017.06.22

#### function upgrade/change
* App that use jni for x86_64, arm64-v8a will have an NHN AppGuard module for that architecture.
* Divide path to download SDK for Android, iOS(Beta)
* The iOS(Beta) version is free for all users
* Enhancement of the module detection function of the NHN AppGuard itself
* Extend Unity3D DLL File Encrpyt
    * Unitiy Basic DLL files as well as DLL files separately added are also encrypted. (Level 3)

### 2017.05.25

#### function upgrade/change
* Simplify application Android version
    * before : Protection work after SDK linkage
    * after : You can apply only protection work (If user ID identifier registration is necessary, it is necessary to selectively be linked SDK, but it becomes simpler than before.)
* Restructure App Protection Level
    * Level 1 : Abnormal behavior and pattern based basic security behavior detect about app
    * Level 2 : Level1 + Enhanced security function such as Encrypt source code, Prevent to modify App, etc.
    * Level 3 : Level2 + More Enhanced security function(Because stability check may be required for certain services, it is recommended to use it only if you have received a separate guide)
    * Level ex : Version of must required SDK be linked, Provide security between level1 to level2(it is recommended when conflict other security solution)

### 2017.04.20

#### bug fix
* Fix some app intall issues when applying app modification prevent function
* Enhance compatibility with apps that use external resources when applying app modification prevent function
* Fix app guard build error in version 5.6 of Unity3d

### 2017.04.04

#### bug fix
* Fix multidex bug of app modification prevent function

### 2017.03.23

#### function upgrade/change
* [SDK] Add function of supporting Unity3d il2cpp build

#### bug fix
* Fix an issue where blocking logic was not executed normally when policy update was delayed
* Fix an issue where unnecessary exceptions were output to Android logs

### 2017.01.19

#### function upgrade/change
* [SDK] New NHN AppGuard iOS SDK deploy
* Enhance function of apk modification prevention

#### bug fix
* Fix synchronization error between policy settings and detection logic
* Fix crash issue based on network conditions (Update log transfer library)

### 2016.12.22

#### function upgrade/change
* Add detection pattern of cheating tool
* [Console] Add information of NHN AppGuard engine version in detection logs

### 2016.12.08

#### function upgrade/change
* Add detection pattern of rooting
* [SDK] Add multi-lingual setting API at message when blocking in NHN AppGuard

#### bug fix
* [Console] Fix an error that the protection failed but appears to be successful on the web console

### 2016.11.24

#### function upgrade/change

* [SDK] Update NHN AppGuard SDK(tcag.jar)
* [Console] Add Notice in NHN AppGuard Web Console

### 2016.10.20

#### function upgrade/change

* [API] Change parameter of NHN AppGuard SDK linkage function
* [SDK] Add auto update function of NHN AppGuard CLI(Command Line Build) tool

### 2016.09.29

#### bug fix

* [Console] Fix window of agree terms and link error
* [Console] Fix UI break when protecting app

### 2016.09.08

#### bug fix

* Fix false positives of speed hack detection in Android 7.0

### 2016.08.18

#### function upgrade/change

* Update detection pattern
* Support Android N
* [Console] Add function to searching iOS logs
* [Console] Add function to change the number of logs displayed on a page (fixed 15 -> select 15/30/50)

### 2016.08.04

#### function upgrade/change

* Enhance detection of speed manipulation

#### bug fix

* Fix some errors due to Timer
