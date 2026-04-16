## Security > NHN AppGuard > API 가이드

## NHN AppGuard Public API
NHN AppGuard Public API를 사용하려면 [문의하기](https://www.nhncloud.com/kr/support/inquiry?alias=tab3_08)에서 권한을 요청해야 합니다.

[API 도메인]

| 리전 | 도메인 |
| --- | --- |
| 모든 리전 | [https://appguard.api.nhncloudservice.com](https://appguard.api.nhncloudservice.com) |

### 인증 및 권한

NHN AppGuard Public API를 사용하려면 User Access Key가 필요합니다. User Access Key는 NHN Cloud 계정 또는 IAM 계정을 기반으로 발급되는 인증 키로, Secret Access Key와 함께 사용하여 API 요청에 대한 인증 수단으로 활용됩니다.
User Access Key와 Secret Access Key는 콘솔의 **API 보안 설정**에서 발급할 수 있습니다. User Access Key 발급 및 사용에 대한 자세한 내용은 [User Access Key](/nhncloud/ko/public-api/user-access-key/)를 참고하세요.

!!! danger "주의"
    API 호출에 연동된 User Access Key ID/Secret Access Key를 가진 멤버가 탈퇴하면 서비스 장애가 발생할 수 있습니다. 탈퇴 전에 유효한 멤버의 키로 교체해야 합니다.

### 대시보드

#### 이상 행위 탐지 현황 조회

유저/디바이스별 이상 행위 탐지 현황을 조회합니다.
당일 데이터는 조회할 수 없습니다.

##### 요청

이 API는 요청 본문을 요구하지 않습니다.

[URI]

| 메서드 | URI |
| --- | --- |
| GET | /v1.0/appkeys/{appkey}/dashboard/abnormal-status |

[헤더]

| 이름 | 타입 | 필수 여부 | 설명                                 |
| --- | --- | ----- |------------------------------------|
| X-TC-AUTHENTICATION-ID | String | 필수 | NHN Cloud 콘솔에서 발급한 User Access Key |
| X-TC-AUTHENTICATION-SECRET | String | 필수 | NHN Cloud 콘솔에서 발급한 Secret Access Key |

[파라미터]

| 이름 | 타입 | 필수 여부 | 기본값 | 유효 범위              | 설명                             |
| --- | --- |-------|-----|--------------------|--------------------------------|
| targetType | Integer | 선택    | 0   | 0, 1               | 출력할 ID 타입(0=디바이스 ID, 1=유저 ID) |
| targetDate | Date | 필수    | -   | (N-90)일 ~ (N-1)일 | 대상 일자(format=`YYYY-MM-DD`)    |
| os | Integer | 필수    | -   | 1, 2               | 조회 대상 OS(1=Android, 2=iOS)    |

<details><summary>요청 예시</summary>

<p>

```
curl -X GET "https://appguard.api.nhncloudservice.com/v1.0/appkeys/{appkey}/dashboard/abnormal-status?targetType=0&targetDate=2024-01-01&os=1" \
 -H "Content-Type: application/json" \
 -H "X-TC-AUTHENTICATION-ID: {user_access_key}" \
 -H "X-TC-AUTHENTICATION-SECRET: {secret_access_key}"
```

</p>
</details>

##### 응답

[필드]

| 필드                        | 타입 | 설명                                                         |
|---------------------------| --- |------------------------------------------------------------|
| header                    | Object | 헤더 영역                                                      |
| header.isSuccessful       | Boolean | 성공 여부                                                      |
| header.resultCode         | Integer | 결과 코드                                                      |
| header.resultMessage      | String | 결과 메시지                                                     |
| data                      | List | 유저별 이상 행위 탐지 현황 목록                                          |
| data[0].abnormalId        | String | 유저 ID 또는 디바이스 ID(path parameter `targetType` 값에 따름)        |
| data[0].total             | Integer | 이상 행위 탐지 총계                                                 |
| data[0].cheatCount        | Integer | 치팅 툴 탐지 횟수                                                  |
| data[0].emulatorCount     | Integer | 에뮬레이터 탐지 횟수                                                |
| data[0].modificationCount | Integer | 변조 탐지 횟수                                                   |
| data[0].debuggerCount     | Integer | 디버거 탐지 횟수                                                  |
| data[0].rootingCount      | Integer | 루팅 탐지 횟수(path parameter `os` 값에 따름, Android Only)          |
| data[0].speedHackCount    | Integer | 스피드 조작 탐지 횟수(path parameter `os` 값에 따름, Android Only)      |
| data[0].networkCount      | Integer | SSL Pinning 탐지 횟수(path parameter `os` 값에 따름, Android Only) |
| data[0].virtualCount      | Integer | 가상 환경 탐지 횟수(path parameter `os` 값에 따름, Android Only)       |
| data[0].remoteCount       | Integer | 원격 제어 탐지 횟수(path parameter `os` 값에 따름, Android Only)       |
| data[0].macroCount        | Integer | 매크로 툴 탐지 횟수(path parameter `os` 값에 따름, Android Only)        |
| data[0].blackCount        | Integer | 블랙리스트 탐지 횟수(path parameter `os` 값에 따름, Android Only)       |
| data[0].macroSuspectCount | Integer | 매크로 의심 사용자 탐지 횟수(path parameter `os` 값에 따름, Android Only) |
| data[0].jailbreakCount    | Integer | 탈옥 탐지 횟수(path parameter `os` 값에 따름, iOS Only)             |
| data[0].hookCount         | Integer | 후킹 탐지 횟수(path parameter `os` 값에 따름, iOS Only)             |

[응답 본문]

<details><summary>응답 예시 - Android(os=1)</summary>

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

<details><summary>응답 예시 - iOS(os=2)</summary>

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


#### 오류 코드

아래에 명시되지 않은 코드는 [API Gateway의 Gateway 오류 코드](https://docs.nhncloud.com/ko/Application%20Service/API%20Gateway/ko/error-code/)와 HTTP Response Status Code (RFC9110)를 따릅니다.

| code | message | 설명 | 비고 |
| ---- | ------- | --- | --- |
| 4000001 | INVALID PARAMETER | 잘못된 인자 |  |
| 4010001 | INVALID APPKEY | 잘못된 appkey | 인증에 사용한 사용자가 appkey에 포함된 유저인지 확인 |
| 4010007 | Invalid user access key. | 잘못된 user access key |  |
| 4010008 | Invalid user access key or secret access key. | 잘못된 user access key 또는 secret access key |  |

## 무결성 검증 API 가이드

무결성 검증 API를 사용하려면 [문의하기](https://www.nhncloud.com/kr/support/inquiry?alias=tab3_08)에서 권한을 요청해야 합니다.

[API 도메인]

| 리전 | 도메인 |
| --- | --- |
| 모든 리전 | [https://api-integrityguard.nhncloudservice.com](https://api-integrityguard.nhncloudservice.com) |

### 토큰 정보 조회
토큰을 조회합니다. 한 번 조회한 토큰은 사라집니다.

#### 요청


[URL]

| 메서드 | URI |
| --- | --- |
| GET | /integrity-api/v1.0/client/apps/{appId}/token-info |

[헤더]

| 이름 | 타입 | 필수 | 설명 |
| --- | --- | --- | --- |
| Authorization | String | 필수 | Bearer 토큰 |


<details><summary>요청 예시</summary>

<p>

```bash
curl -X GET 'https://api-integrityguard.nhncloudservice.com/integrity-api/v1.0/client/apps/{appId}/token-info' \
  -H 'Authorization: Bearer {token}'
```

</p>
</details>

#### 응답

[필드]

| 필드 | 타입 | 설명 |
| --- | --- | --- |
| header | Object | 헤더 영역 |
| header.isSuccessful | Boolean | 성공 여부 |
| header.resultCode | Integer | 결과 코드 |
| header.resultMessage | String | 결과 메시지 |
| body | Object | 토큰 정보 |
| body.appId | String | 앱 ID |
| body.expireAt | Long | 만료 시간 (timestamp) |
| body.integrityInfo | Object | 앱 무결성 정보 |
| body.integrityInfo.codeHash | String | 바이너리 해시 |
| body.integrityInfo.signature | String | 서명 |
| body.integrityResult | Object | 무결성 검증 결과 |
| body.integrityResult.codeHashMatch | Boolean | 코드 해시 일치 여부 |
| body.integrityResult.signatureMatch | Boolean | 서명 일치 여부 |
| body.integrityResult.integrityChecked | Object | 무결성 검사 정보 |
| body.integrityResult.integrityChecked.rootingDetected | Boolean | 루팅 탐지 여부 (nullable) |
| body.integrityResult.integrityChecked.emulatorDetected | Boolean | 에뮬레이터 탐지 여부 (nullable) |
| body.integrityResult.integrityChecked.debugDetected | Boolean | 디버그 탐지 여부 (nullable) |
| body.integrityResult.integrityChecked.hookingDetected | Boolean | 후킹 탐지 여부 (nullable) |
| body.integrityResult.integrityChecked.untrustedEnv | Boolean | 신뢰할 수 없는 환경 여부 (nullable) |


<details><summary>응답 예시</summary>

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
