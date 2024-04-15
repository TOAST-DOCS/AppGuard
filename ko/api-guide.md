## Security > NHN AppGuard > API 가이드

API를 사용하려면 [1:1 문의](https://www.toast.com/kr/support/inquiry?alias=tab3_08)를 통해 권한을 요청해야 합니다.

[API 도메인]

| 리전 | 도메인 |
| --- | --- |
| 모든 리전 | [https://api-appguard.capi.nhncloudservice.com](https://api-appguard.capi.nhncloudservice.com) |

### 인증 및 권한

API를 사용하려면 인증을 위해 User Access Key ID와 Secret Access Key가 필요합니다. **회원 정보 > API 보안 설정**에서 생성할 수 있습니다.
생성된 Key는 요청 Header에 포함해야 합니다.

> [주의]
> API를 호출하는 작업에 연동된 User Access Key ID/Secret Access Key를 가진 멤버가 탈퇴하는 경우 고객의 서비스에 장애가 발생할 수 있으므로 탈퇴 전 유효한 멤버의 키로 교체해야 합니다.

## 대시보드

### 이상행위 탐지현황 조회

유저/디바이스별 이상행위 탐지현황을 조회합니다.
당일 데이터는 조회할 수 없습니다.

#### 요청

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
curl -X GET "https://api-appguard.capi.nhncloudservice.com/v1.0/appkeys/{appkey}/dashboard/abnormal-status?targetType=0&targetDate=2024-01-01&os=1" \ 
 -H "Content-Type: application/json" 
 -H "X-TC-AUTHENTICATION-ID: {user_access_jey}" 
 -H "X-TC-AUTHENTICATION-SECRET: {secret_access_key}"
```

</p>
</details>

#### 응답

[필드]

| 필드                        | 타입 | 설명                                                         |
|---------------------------| --- |------------------------------------------------------------|
| header                    | Object | 헤더 영역                                                      |
| header.isSuccessful       | Boolean | 성공 여부                                                      |
| header.resultCode         | Integer | 결과 코드                                                      |
| header.resultMessage      | String | 결과 메시지                                                     |
| data                      | List | 유저별 이상행위 탐지 현황 목록                                          |
| data[0].abnormalId        | String | 유저 ID 또는 디바이스 ID(path parameter `targetType` 값에 따름)        |
| data[0].total             | Integer | 이상행위 탐지 총계                                                 |
| data[0].cheatCount        | Integer | 치팅툴 탐지 횟수                                                  |
| data[0].emulatorCount     | Integer | 에뮬레이터 탐지 횟수                                                |
| data[0].modificationCount | Integer | 변조 탐지 횟수                                                   |
| data[0].debuggerCount     | Integer | 디버거 탐지 횟수                                                  |
| data[0].rootingCount      | Integer | 루팅 탐지 횟수(path parameter `os` 값에 따름, Android Only)          |
| data[0].speedHackCount    | Integer | 스피드 조작 탐지 횟수(path parameter `os` 값에 따름, Android Only)      |
| data[0].networkCount      | Integer | SSL Pinning 탐지 횟수(path parameter `os` 값에 따름, Android Only) |
| data[0].virtualCount      | Integer | 가상 환경 탐지 횟수(path parameter `os` 값에 따름, Android Only)       |
| data[0].remoteCount       | Integer | 원격 제어 탐지 횟수(path parameter `os` 값에 따름, Android Only)       |
| data[0].macroCount        | Integer | 매크로툴 탐지 횟수(path parameter `os` 값에 따름, Android Only)        |
| data[0].blackCount        | Integer | 블랙리스트 탐지 횟수(path parameter `os` 값에 따름, Android Only)       |
| data[0].macroSuspectCount | Integer | 매크로 의심 사용자 탐지 횟수(path parameter `os` 값에 따름, Android Only) |
| data[0].jailbreakCount    | Integer | 탈옥 탐지 횟수(path parameter `os` 값에 따름, iOS Only)             |
| data[0].hookCount         | Integer | 후킹 탐지 횟수(path parameter `os` 값에 따름, iOS Only)             |

[응답 본문]
os=1(Android) 응답 예시

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

---