## Security > NHN AppGuard > API Guide

## NHN AppGuard Public API
To use the NHN AppGuard Public API, you must request permission through [Contact us] (https://www.nhncloud.com/kr/support/inquiry?alias=tab3_08).

[API Domain]

| Region | Domain |
| --- | --- |
| All regions | [https://appguard.api.nhncloudservice.com](https://appguard.api.nhncloudservice.com) |

### Authentication and Authorization

User Access Key is required to use the NHN AppGuard Public API. A User Access Key is an authentication key issued based on an NHN Cloud or IAM account. It is used in conjunction with a Secret Access Key to authenticate API requests.
User Access Key and Secret Access Key can be issued in the **API Security Settings** from the console. For more information on issuing and using User Access Key, refer to the [User Access Key](/nhncloud/en/public-api/user-access-key/).

!!! danger "Caution"
If a member with a User Access Key ID/Secret Access Key associated API calls withdraws, it may cause service failure. You must replace it with a valid member's key before withdrawing.

### Dashboard

#### Retrieve abnormal behavior detection status

Retrieves abnormal behavior detection status by user/device.
Data for the current day is not available.

##### Request

This API does not require a request body.

[URI]

| Method | URI |
| --- | --- |
| GET | /v1.0/appkeys/{appkey}/dashboard/abnormal-status |

[Header]

| Name | Type | Required | Description                                 |
| --- | --- | ----- |------------------------------------|
| X-TC-AUTHENTICATION-ID | String | Required | User Access Key issued by NHN Cloud Console |
| X-TC-AUTHENTICATION-SECRET | String | Required | Secret Access Key issued by NHN Cloud Console |

[Parameter]

| Name | Type | Required | Default value | Valid range              | Description                             |
| --- | --- |----------|---------------|--------------------|--------------------------------|
| targetType | Integer | Optional | 0             | 0, 1               | Type of ID to output (0=Device ID, 1=User ID) |
| targetDate | Date | Required | -             | (N-90) day ~ (N-1) day | Target date (format=`YYYY-MM-DD`)    |
| os | Integer | Required | -             | 1, 2               | Retrieve target OS (1=Android, 2=iOS)    |

<details><summary>Request example</summary>

<p>

```
curl -X GET "https://appguard.api.nhncloudservice.com/v1.0/appkeys/{appkey}/dashboard/abnormal-status?targetType=0&targetDate=2024-01-01&os=1" \
 -H "Content-Type: application/json" \
 -H "X-TC-AUTHENTICATION-ID: {user_access_key}" \
 -H "X-TC-AUTHENTICATION-SECRET: {secret_access_key}"
```

</p>
</details>

##### Response

[Field]

| Field                     | Type | Description                                                         |
|---------------------------| --- |------------------------------------------------------------|
| header                    | Object | Header area                                                      |
| header.isSuccessful       | Boolean | Successful or not                                                      |
| header.resultCode         | Integer | Result code                                                      |
| header.resultMessage      | String | Result message                                                     |
| data                      | List | Abnormal behavior detection status list by user                                          |
| data[0].abnormalId        | String | User ID or device ID (depending on the value of the path parameter `targetType` )        |
| data[0].total             | Integer | Abnormal behavior detection totals                                                 |
| data[0].cheatCount        | Integer | Cheating tool detection count                                                  |
| data[0].emulatorCount     | Integer | Emulator detection count                                                |
| data[0].modificationCount | Integer | Temper detection count                                                   |
| data[0].debuggerCount     | Integer | Debugger detection count                                                  |
| data[0].rootingCount      | Integer | Rooting detection count (based on the path parameter `os`, Android Only)          |
| data[0].speedHackCount    | Integer | Speed manipulation detection count (based on the path parameter `os`, Android Only)      |
| data[0].networkCount      | Integer | SSL Pinning detection count (based on the path parameter `os`, Android Only) |
| data[0].virtualCount      | Integer | Virtual environment detection count (based on the path parameter `os`, Android Only)       |
| data[0].remoteCount       | Integer | Remote control detection count (based on path parameter `os`, Android Only)       |
| data[0].macroCount        | Integer | Macro tool detection count (based on the path `parameter` os, Android Only)        |
| data[0].blackCount        | Integer | Blacklist detection count (based on the path parameter `os`, Android Only)       |
| data[0].macroSuspectCount | Integer | Macro suspect user detection count (based on the path parameter `os`, Android Only) |
| data[0].jailbreakCount    | Integer | Jailbreak detection count (based on the path parameter `os`, iOS Only)             |
| data[0].hookCount         | Integer | Hooking detection count (based on the path parameter `os`, iOS Only)             |

[Response Body].

<details><summary>Response example - Android (os=1)</summary>

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

<details><summary>Response Body - iOS (os=2)</summary>

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


#### Error Code

Codes not specified below follow the [Gateway error codes in API Gateway](https://docs.nhncloud.com/en/Application%20Service/API%20Gateway/en/error-code/) and HTTP Response Status Code (RFC9110).

| code | message | Description | Note |
| ---- | ------- | --- | --- |
| 4000001 | INVALID PARAMETER | Invalid argument |  |
| 4010001 | INVALID APPKEY | Invalid appkey | Verify that the user used for authentication is the user included in the appkey |
| 4010007 | Invalid user access key. | Invalid user access key |  |
| 4010008 | Invalid user access key or secret access key. | Invalid user access key or secret access key |  |

## Integrity Verification API Guide

To use the Integrity Verification API, you must request access via [Contact Us](https://www.nhncloud.com/kr/support/inquiry?alias=tab3_08).

[API Domain]

| Region | Domain |
| --- | --- |
| All regions | [https://api-integrityguard.nhncloudservice.com](https://api-integrityguard.nhncloudservice.com) |

### Get Token Info
Retrieves token information. A token can only be retrieved once and is deleted after retrieval.

#### Request


[URL]

| Method | URI |
| --- | --- |
| GET | /integrity-api/v1.0/client/apps/{appId}/token-info |

[Header]

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization | String | Required | Bearer token |


<details><summary>Request example</summary>

<p>

```bash
curl -X GET 'https://api-integrityguard.nhncloudservice.com/integrity-api/v1.0/client/apps/{appId}/token-info' \
  -H 'Authorization: Bearer {token}'
```

</p>
</details>

#### Response

[Field]

| Field | Type | Description |
| --- | --- | --- |
| header | Object | Header area |
| header.isSuccessful | Boolean | Whether the request was successful |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| body | Object | Token information |
| body.appId | String | App ID |
| body.expireAt | Long | Expiration time (timestamp) |
| body.integrityInfo | Object | App integrity information |
| body.integrityInfo.codeHash | String | Binary hash |
| body.integrityInfo.signature | String | Signature |
| body.integrityResult | Object | Integrity verification result |
| body.integrityResult.codeHashMatch | Boolean | Whether the code hash matches |
| body.integrityResult.signatureMatch | Boolean | Whether the signature matches |
| body.integrityResult.integrityChecked | Object | Integrity check information |
| body.integrityResult.integrityChecked.rootingDetected | Boolean | Whether rooting is detected (nullable) |
| body.integrityResult.integrityChecked.emulatorDetected | Boolean | Whether an emulator is detected (nullable) |
| body.integrityResult.integrityChecked.debugDetected | Boolean | Whether debugging is detected (nullable) |
| body.integrityResult.integrityChecked.hookingDetected | Boolean | Whether hooking is detected (nullable) |
| body.integrityResult.integrityChecked.untrustedEnv | Boolean | Whether the environment is untrusted (nullable) |


<details><summary>Response</summary>

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