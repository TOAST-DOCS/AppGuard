## Security > NHN AppGuard > APIガイド

APIを使用するには[1:1お問い合わせ](https://www.toast.com/kr/support/inquiry?alias=tab3_08)を通じて権限をリクエストする必要があります。

[APIドメイン]

| リージョン | ドメイン |
| --- | --- |
| すべてのリージョン | [https://api-appguard.capi.nhncloudservice.com](https://api-appguard.capi.nhncloudservice.com) |

### 認証及び権限

APIを使用するには、認証のためにUser Access Key IDとSecret Access Keyが必要です。**会員情報 > APIセキュリティ設定**で作成できます。
作成されたKeyはリクエストHeaderに含める必要があります。

> [注意]
> User Access Key ID/Secret Access Keyを持つメンバーが退会する場合、顧客のサービスに障害が発生する可能性があるため、退会前に有効なメンバーのキーに交換する必要があります。

## ダッシュボード

### 異常行為検出状況照会

ユーザー/デバイス別の異常行為検出状況を照会します。
当日のデータは照会できません。

#### リクエスト

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
| --- | --- | ----- | --- |--------------------|--------------------------------|
| targetType | Integer | 必須 | - | 0, 1               | 出力するIDタイプ(0=デバイスID, 1=ユーザーID) |
| targetDate | Date | 必須 | - | (N-90)日～(N-1)日 | 対象日時(format=`YYYY-MM-DD`)    |
| os | Integer | 必須 | - | 1, 2               | 照会対象OS(1=Android, 2=iOS)    |

<details><summary>リクエスト例</summary>

<p>

```
curl -X GET "https://api-appguard.capi.nhncloudservice.com/v1.0/appkeys/{appkey}/dashboard/abnormal-status?targetType=0&targetDate=2024-01-01&os=1" \ 
 -H "Content-Type: application/json" 
 -H "X-TC-AUTHENTICATION-ID: {user_access_jey}" 
 -H "X-TC-AUTHENTICATION-SECRET: {secret_access_key}"
```

</p>
</details>

#### レスポンス

[フィールド]

| フィールド | タイプ | 説明                                                       |
| --- | --- |------------------------------------------------------------|
| header | Object | ヘッダ領域                                                    |
| header.isSuccessful | Boolean | 成否                                                    |
| header.resultCode | Integer | 結果コード                                                    |
| header.resultMessage | String | 結果メッセージ                                                   |
| results | List | ユーザー別異常行為検出現況リスト                                        |
| results[0].id | String | ユーザーIDまたはデバイスID(path parameter `targetType`値に基づく)        |
| results[0].total | Integer | 異常行為検出の合計                                                |
| results[0].cheatCount | Integer | チートツール検出回数                                                |
| results[0].emulatorCount | Integer | エミュレータ検出回数                                              |
| results[0].modificationCount | Integer | 改ざん検出回数                                                 |
| results[0].debuggerCount | Integer | デバッガ検出回数                                                |
| results[0].rootingCount | Integer | ルート化検出回数(path parameter `os`値に基づく、 Android Only)          |
| results[0].speedHackCount | Integer | スピード操作検出回数(path parameter `os`値に基づく、 Android Only)      |
| results[0].networkCount | Integer | SSL Pinning検出回数(path parameter `os`値に基づく、 Android Only) |
| results[0].virtualCount | Integer | 仮想環境検出回数(path parameter `os`値に基づく、 Android Only)       |
| results[0].remoteCount | Integer | 遠隔制御検出回数(path parameter `os`値に基づく、 Android Only)       |
| results[0].macroCount | Integer | マクロツール検出回数(path parameter `os`値に基づく、 Android Only)        |
| results[0].blackCount | Integer | ブラックリスト検出回数(path parameter `os`値に基づく、 Android Only)       |
| results[0].macroSuspect\_count | Integer | マクロ疑惑ユーザー検出回数(path parameter `os`値に基づく、 Android Only) |
| results[0].jailbreakCount | Integer | 脱獄検出回数(path parameter `os`値に基づく、 iOS Only)             |
| results[0].hookCount | Integer | フックの検出回数(path parameter `os`値に基づく、 iOS Only)             |

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
    "results": [
        { 
            "id": "id123", 
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
            "macroSuspect_count": 1
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
    "results": [
        { 
            "id": "device123", 
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

---
