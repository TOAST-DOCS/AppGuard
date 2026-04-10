## Security > NHN AppGuard > APIガイド

## NHN AppGuard Public API
NHN AppGuard Public APIを使用するには、[お問い合わせ](https://www.nhncloud.com/jp/support/inquiry?alias=tab3_08)から権限をリクエストする必要があります。

[APIドメイン]

| リージョン | ドメイン |
| --- | --- |
| すべてのリージョン | [https://appguard.api.nhncloudservice.com](https://appguard.api.nhncloudservice.com) |

### 認証及び権限

NHN AppGuard Public APIを使用するにはUser Access Keyが必要です。User Access Keyは、NHN CloudアカウントまたはIAMアカウントを基に発行される認証キーであり、Secret Access Keyと一緒に使用して、APIリクエストに対する認証手段として活用されます。
User Access KeyとSecret Access Keyは、コンソールの**APIセキュリティ設定**で発行できます。User Access Keyの発行及び使用に関する詳細は、[User Access Key](/nhncloud/ja/public-api/user-access-key/)をご参照ください。

!!! danger "注意"
API呼び出しに連携されたUser Access Key ID/Secret Access Keyを持つメンバーが退会すると、サービス障害が発生する可能性があります。退会する前に、有効なメンバーのキーに交換する必要があります。

## ダッシュボード

#### 異常行為の検知状況照会

ユーザー/デバイス別の異常行為検出状況を照会します。
当日のデータは照会できません。

##### リクエスト

このAPIはリクエスト本文を要求しません。

[URI]

| メソッド | URI |
| --- | --- |
| GET | /v1.0/appkeys/{appkey}/dashboard/abnormal-status |

[ヘッダ]

| 名前 | タイプ | 必須かどうか | 説明                               |
| --- | --- | ----- |------------------------------------|
| X-TC-AUTHENTICATION-ID | String | 必須 | NHN Cloudコンソールで発行したUser Access Key |
| X-TC-AUTHENTICATION-SECRET | String | 必須 | NHN Cloudコンソールで発行したSecret Access Key |

[パラメータ]

| 名前 | タイプ | 必須かどうか | デフォルト値 | 有効範囲            | 説明                           |
| --- | --- | ----- |--------|--------------------|--------------------------------|
| targetType | Integer | 任意 | 0      | 0, 1               | 出力するIDタイプ(0=デバイスID, 1=ユーザーID) |
| targetDate | Date | 必須 | -      | (N-90)日～(N-1)日 | 対象日時(format=`YYYY-MM-DD`)    |
| os | Integer | 必須 | -      | 1, 2               | 照会対象OS(1=Android, 2=iOS)    |

<details><summary>リクエスト例</summary>

<p>

```
curl -X GET "https://appguard.api.nhncloudservice.com/v1.0/appkeys/{appkey}/dashboard/abnormal-status?targetType=0&targetDate=2024-01-01&os=1" \
 -H "Content-Type: application/json" \
 -H "X-TC-AUTHENTICATION-ID: {user_access_key}" \
 -H "X-TC-AUTHENTICATION-SECRET: {secret_access_key}"
```

</p>
</details>

##### レスポンス

[フィールド]

| フィールド                     | タイプ | 説明                                                       |
|---------------------------| --- |------------------------------------------------------------|
| header                    | Object | ヘッダ領域                                                    |
| header.isSuccessful       | Boolean | 成否                                                    |
| header.resultCode         | Integer | 結果コード                                                    |
| header.resultMessage      | String | 結果メッセージ                                                   |
| data                      | List | ユーザー別異常行為検出現況リスト                                        |
| data[0].abnormalId        | String | ユーザーIDまたはデバイスID(path parameter `targetType`値に基づく)        |
| data[0].total             | Integer | 異常行為検出の合計                                                |
| data[0].cheatCount        | Integer | チートツール検出回数                                                |
| data[0].emulatorCount     | Integer | エミュレータ検出回数                                              |
| data[0].modificationCount | Integer | 改ざん検出回数                                                 |
| data[0].debuggerCount     | Integer | デバッガ検出回数                                                |
| data[0].rootingCount      | Integer | ルート化検出回数(path parameter `os`値に基づく、 Android Only)          |
| data[0].speedHackCount    | Integer | スピード操作検出回数(path parameter `os`値に基づく、 Android Only)      |
| data[0].networkCount      | Integer | SSL Pinning検出回数(path parameter `os`値に基づく、 Android Only) |
| data[0].virtualCount      | Integer | 仮想環境検出回数(path parameter `os`値に基づく、 Android Only)       |
| data[0].remoteCount       | Integer | 遠隔制御検出回数(path parameter `os`値に基づく、 Android Only)       |
| data[0].macroCount        | Integer | マクロツール検出回数(path parameter `os`値に基づく、 Android Only)        |
| data[0].blackCount        | Integer | ブラックリスト検出回数(path parameter `os`値に基づく、 Android Only)       |
| data[0].macroSuspectCount | Integer | マクロ疑惑ユーザー検出回数(path parameter `os`値に基づく、 Android Only) |
| data[0].jailbreakCount    | Integer | 脱獄検出回数(path parameter `os`値に基づく、 iOS Only)             |
| data[0].hookCount         | Integer | フックの検出回数(path parameter `os`値に基づく、 iOS Only)             |

[レスポンス本文]
os=1(Android)レスポンス例

<details><summary>レスポンス例 - Android(os=1)</summary>

<p>

```json
{
    "header": {
        "resultCode": 1,
        "resultMessage": "Request success",
        "isSuccessful": true
    },
    "data": [
        {
            "abnormalId": "id123",
            "total": 12,
            "cheatCount": 1,
            "emulatorCount": 1,
            "modificationCount": 1,
            "debuggerCount": 1,
            "rootingCount": 1,
            "speedHackCount": 1,
            "networkCount": 1,
            "virtualCount": 1,
            "remoteCount": 1,
            "macroCount": 1,
            "blackCount": 1,
            "macroSuspectCount": 1
        }
    ]
}
```

</p>
</details>

<details><summary>レスポンス例 - iOS(os=2)</summary>

<p>

```json
{
    "header": {
        "resultCode": 1,
        "resultMessage": "Request success",
        "isSuccessful": true
    },
    "data": [
        {
            "abnormalId": "device123",
            "total": 6,
            "cheatCount": 1,
            "emulatorCount": 1,
            "modificationCount": 1,
            "debuggerCount": 1,
            "jailbreakCount": 1,
            "hookCount": 1
        }
    ]
}
```

</p>
</details>


#### エラーコード

下記に明示されてないコードは[API GatewayのGatewayエラーコード](https://docs.nhncloud.com/ko/Application%20Service/API%20Gateway/ko/error-code/)とHTTP Response Status Code (RFC9110)に従います。

| code | message | 説明 | 備考 |
| ---- | ------- | --- | --- |
| 4000001 | INVALID PARAMETER | 無効な引数 |  |
| 4010001 | INVALID APPKEY | 無効なappkey | 認証に使用したユーザーがappkeyに含まれるユーザーであることを確認 |
| 4010007 | Invalid user access key. | 無効なuser access key |  |
| 4010008 | Invalid user access key or secret access key. | 無効なuser access keyまたはsecret access key |  |

## 整合性検証APIガイド

整合性検証APIを使用するには、[お問い合わせ](https://www.nhncloud.com/jp/support/inquiry?alias=tab3_08)から権限をリクエストする必要があります。

[APIドメイン]

| リージョン | ドメイン |
| --- | --- |
| 全てのリージョン | [https://api-integrityguard.nhncloudservice.com](https://api-integrityguard.nhncloudservice.com) |

### トークン情報照会
トークンを照会します。一度照会したトークンは削除されます。

#### リクエスト


[URL]

| メソッド | URI |
| --- | --- |
| GET | /integrity-api/v1.0/client/apps/{appId}/token-info |

[ヘッダ]

| 名前 | タイプ | 必須 | 説明 |
| --- | --- | --- | --- |
| Authorization | String | 必須 | Bearerトークン |


<details><summary>リクエスト例</summary>

<p>

```bash
curl -X GET 'https://api-integrityguard.nhncloudservice.com/integrity-api/v1.0/client/apps/{appId}/token-info' \
  -H 'Authorization: Bearer {token}'
```

</p>
</details>

#### レスポンス

[フィールド]

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header | Object | ヘッダ領域 |
| header.isSuccessful | Boolean | 成否 |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| body | Object | トークン情報 |
| body.appId | String | アプリID |
| body.expireAt | Long | 有効期限(timestamp) |
| body.integrityInfo | Object | アプリの整合性情報 |
| body.integrityInfo.codeHash | String | バイナリハッシュ |
| body.integrityInfo.signature | String | 署名 |
| body.integrityResult | Object | 整合性検証結果 |
| body.integrityResult.codeHashMatch | Boolean | コードハッシュの一致の有無 |
| body.integrityResult.signatureMatch | Boolean | 署名の一致の有無 |
| body.integrityResult.integrityChecked | Object | 整合性検査情報 |
| body.integrityResult.integrityChecked.rootingDetected | Boolean | root化検知の有無（nullable） |
| body.integrityResult.integrityChecked.emulatorDetected | Boolean | エミュレータ検知の有無(nullable) |
| body.integrityResult.integrityChecked.debugDetected | Boolean | デバッグ検知の有無(nullable) |
| body.integrityResult.integrityChecked.hookingDetected | Boolean | フッキング検知の有無(nullable) |
| body.integrityResult.integrityChecked.untrustedEnv | Boolean | 信頼できない環境かどうか(nullable) |


<details><summary>レスポンス例</summary>

<p>

```json
{
  "header": {
    "isSuccessful": true,
    "resultCode": 0,
    "resultMessage": "SUCCESS"
  },
  "body": {
    "appId": "619ce8dc-69c7-4efd-ac37-c0439c928d23",
    "expireAt": 1763097379336,
    "integrityInfo": {
      "codeHash": "codeHash....",
      "signature": "signature...."
    },
    "integrityResult": {
      "codeHashMatch": true,
      "signatureMatch": true,
      "integrityChecked": {
        "rootingDetected": true,
        "emulatorDetected": true,
        "debugDetected": true,
        "hookingDetected": false,
        "untrustedEnv": true
      }
    }
  }
}
```

</p>
</details>
