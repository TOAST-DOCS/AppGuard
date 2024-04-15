## Security > NHN AppGuard > API Guide

To use the API, you must request permission through [1:1 Inquiry](https://www.toast.com/kr/support/inquiry?alias=tab3_08).

[API Domain]

| Region | Domain |
| --- | --- |
| All regions | [https://api-appguard.capi.nhncloudservice.com](https://api-appguard.capi.nhncloudservice.com) |

### Authentication and Authorization

User Access Key ID and Secret Access Key are required for authentication to use APIs. Go to **Member Information > API Security Settings** to create them.
The created Key must be included in the request Header.

> [Caution]
> If a member with the User Access Key ID/Secret Access Key linked to the API call withdraws, the customer's service may be interrupted, so the key must be replaced with a valid member's key before withdrawal.

## Dashboard

### Retrieve abnormal behavior detection status

Retrieves abnormal behavior detection status by user/device.
Data for the current day is not available.

#### Request

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
curl -X GET "https://api-appguard.capi.nhncloudservice.com/v1.0/appkeys/{appkey}/dashboard/abnormal-status?targetType=0&targetDate=2024-01-01&os=1" \ 
 -H "Content-Type: application/json" 
 -H "X-TC-AUTHENTICATION-ID: {user_access_jey}" 
 -H "X-TC-AUTHENTICATION-SECRET: {secret_access_key}"
```

</p>
</details>

#### Response

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
Example os=1 (Android) response

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

Codes not specified below follow the [Gateway error codes in API Gateway](https://docs.nhncloud.com/ko/Application%20Service/API%20Gateway/ko/error-code/) and HTTP Response Status Code (RFC9110).

| code | message | Description | Note |
| ---- | ------- | --- | --- |
| 4000001 | INVALID PARAMETER | Invalid argument |  |
| 4010001 | INVALID APPKEY | Invalid appkey | Verify that the user used for authentication is the user included in the appkey |
| 4010007 | Invalid user access key. | Invalid user access key |  |
| 4010008 | Invalid user access key or secret access key. | Invalid user access key or secret access key |  |

---