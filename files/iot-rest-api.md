# Commom Api

## 查询操作方法说明

>满足关键字 :
$ne，$lt，$gt，$lte，$gte，$in，$nin，$exists，$regex

>配列の比較
$all

>比較の集合
$or

>关联
$relatedTo（部分支持）

>位置函数
$nearSphere


不支持关键字：
$select ,$inquery

查询支持mongodb的所有关键字
参考文档：http://www.360doc.com/content/16/0706/17/15113968_573576574.shtml



注意事项 "_id" 是一个object对象，请查询的时候new 一个object对象

>where ={"_id":objid}(服务器已经处理)

>where="{"_id":{"$in":{object(objId)}}}" （调用段需要自行new 一个object对象出来）


order 关键字修正  ：现在排序的时候关键字 变成sort

>排序规则：
sort=“{'a':-1}”

## 更新操作方法说明

<b>Increment</b>

*** 对应字段增加数字 ***

` ``
  {"score":{"__op":"Increment","amount":1}}
` ``

<b>Add</b>

*** 对应列中追加指定参数 ***

` ``
  {"food":{"__op":"Add","objects":["vegetable"]}}
` ``

<b>Remove</b>

*** 对应列中删除指定参数 ***

` ``
  {"food":{"__op":"Remove","objects":["meat"]}}
` ``

<b>RemoveField</b>

*** 删除对应数据中的指定字段 ***

` ``
  {"food":{"__op":"RemoveField"}}
` ``

<b>AddRelation</b>

*** 追加对应字段的关联条件（暂时没有验证对应的objid是否正确） ***

` ``
  {"opponents":{"__op":"AddRelation","objects":[{"__type":"Pointer","className":"Player","objectId":"Vx4nudeWn"}]}}
` ``

<b>RemoveRelation</b>

*** 删除对应字段的关联条件 ***

` ``
  {"opponents":{"__op":"RemoveRelation","objects":[{"__type":"Pointer","className":"Player","objectId":"Vx4nudeWn"}]}}
` ``

## 版本更新(ok)

### /api/v1/version/check （检测版本）

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| client_id | true | string | domain key |
| client_secret | true | string | Domain_secret |
<b>method</b> 
post
### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "hasnew": 1,
    "updatetype": 1,
    "message": "",
    "lastversion": "9000.0123.123.1234",
    "url": "https://www.osksh.link/localhsot.aapp.com"
  }
}
` ``

*** 参数说明 ***

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| hasnew | true | bool | 是否有最新的 |
| updatetype | true | string | 更新flg 1:强制,0:非强制 |
| message | true | string | 描述 |
| lastversion | true | string | 最新版本号 |
| url | true | string | 下载url |


### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-9999999|   服务器系统错误 | |
|-1100002|   Iot App Interface 头部信息缺失 | |
|-1200001|   版本格式不正确 | |
|-1300001|   对应app 不存在 | |


## 日志上传(暂无)


# Oauth Api

## 用户 Access_token获取 (ok)

### /api/v1/oauth/access_token （用户获取access_token）

### 请求参数
<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| client_id | true | string | domain key |
| client_secret | true | string | Domain_secret |
| grant_type | true | string | 请求类型：注册默认 password |
| username | true | string | 登入邮箱 |
| password | true | string | 登入密码 |

<b>method</b> 
post

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "token_type": "Bearer",
    "expires_in": 1296000,
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImNiNzNiZTQ2ZjFkNWYzZTg4ZGE5NTVjMTJmYzZiMDRjY2VkMTQxYTJhYzljYTA2ZjVkYTQzM2VmOTZiNmUwYTM0Yzc2M2ZhNTNkNGFlMmM1In0.eyJhdWQiOiI1OTE1NzQxZTA1Mzc5MDA4YTg3MTkxYjIiLCJqdGkiOiJjYjczYmU0NmYxZDVmM2U4OGRhOTU1YzEyZmM2YjA0Y2NlZDE0MWEyYWM5Y2EwNmY1ZGE0MzNlZjk2YjZlMGEzNGM3NjNmYTUzZDRhZTJjNSIsImlhdCI6MTQ5NTA3OTU4NCwibmJmIjoxNDk1MDc5NTg0LCJleHAiOjE0OTYzNzU1ODQsInN1YiI6IjU5MWQxYWEwMDUzNzkwMDBjMTdjY2FjNSIsInNjb3BlcyI6W119.KMugpy03M4uB_wyig9OC20q4uJE3QpyNK9ZAlhptPNKrAHSNloRHWleYrGo2WlmmGb94t9GJqicC2UOZ-V-HkJtHqyzSJGqGam4uMFTtAzgbSug4ZaRGBq2bAchaHXRyG2qKTho5tnwGGqXM1LymmH_7J5yJRrWAPqJL10wFNLNosy0A2vZqgNaq5VFOdYaY0SUxTxBOloq9kFOyNNXYd1g56s5_PuTmEHtW4kg0Q3_XOk06OkhzGVcdjuc0urTLcndbfdKNqyKzciGf3DHQgHxpXtoMvJw4KqOxR6pAkOS3ZscTKLMeso5Q8zFDr_WZSiML2Y8n7Bp3Cq3BQYJR4hjdT4I3LZIU53i00kUbDBCqPaWd_ZurJGjkc4g55shU21VIsTQ39vhDDaAeNccsxgmfkvRW_3qdxUDSn5mToNZ5JDvhBU3ucZdC013d9cTvTBOKRZyHtnJ9xNoN2WDJr7mB2yDDREfJ2PKSTc_3h5WiPORKkZdHxJJS4yEoA4O8FU0REXIjqRivaKegrRMmt7M2c0DzOGFNw0zELkrCGM8QiHd0-YxUSGqXznakej49xNYsCHyyyQhMJVhu2sGXa2ojkdO7h46HEAQA6iYs2vClN31jmqe7RZny6Isy9TG_VIcClTgKz5v1knK8nfIX1olJBELm_27sRZqVAI5B7jg",
    "refresh_token": "p6ke+eMGbL4qMLuz9PejfoCDDJHGLTfaYM3ZOeWyU0tRYb1oV58mr1N0VntAH4zK2KoO3mm//rPafthBzdkObTnBQLdgPVNFzh2RCQbF62H5eMttF7Nl9ktgctv4cu3wgA1gSNoV25w998TVwa+ZKancpXlbCFQTy6cvBNRj8K7NGBaw8H4iA9Bh2x9aFPu2Gz9Lf+ZT7JIrBvrW2Z3luAuKH5Q47ijuZb3khhu3CUN693SxMIPP7ky8sh8xG1gqDiPLCDigqsF0SDJnc0KfVPRsBCWgLoHv50eAgS8RsamJM8mhxOqR8QBUhlpLUD0EKAdm4Xz6lJiwAHGEf/HPJMIEcbSr3vW9X7AqEHoFwHLxszGxOwFNSt5UpwWYoW3KA7biAbSthPEWoA8ox3uLnG0Ba40nviiCzPauEKVDFYtC3yoHBsevvKsxtLHgbO7DHVreI3fhJyAESFYLke1nh+UTeERLOpkXX1ZL+cGXJVADbUj6IfH+z0hooRf1p86xW2xqihGnztRC9r4yqjM1BUwITlFDDlN2jc3LrdGRfMr4Gtm5DYnqL6fA53hjK1KrB8+dlBg7Ly6rIwC4kDaPYIu1lq6n9uEWOp4Gqk3hQA4Jq9E9thcIBQpf1gFz8hV+T+1c8+fNIGj75ZOzkVz3Tn2cK1bMsDbxqdq1JnJ6tII="
  }
}

` `

*** 错误JSON示例 ***

` ``

{
  "code": -100004,
  "error": "The user credentials were incorrect."
}

` ``

### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-1100002|   Iot App Interface 头部信息缺失 | |
|-100001|   invalid_request |   oauth缺失|
|-100002|   unsupported_grant_type |    无效的grat_type|
|-100003|   invalid_client |    无效client|
|-100004|   invalid_credentials |   用户password无效|

关于其它错误返回值与错误代码，参见 [错误代码说明](#ErrorCode List) http的status_code为400

## 刷新接口 (ok)

### /api/v1/oauth/access_token（用户刷新access_token）

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| client_id | true | string | domain key |
| client_secret | true | string | Domain_secret |
| grant_type | true | string | 请求类型：刷新默认 refresh_token |
| refresh_token | true | string | refresh_token |

<b>method</b> 
post

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "token_type": "Bearer",
    "expires_in": 1296000,
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImNiNzNiZTQ2ZjFkNWYzZTg4ZGE5NTVjMTJmYzZiMDRjY2VkMTQxYTJhYzljYTA2ZjVkYTQzM2VmOTZiNmUwYTM0Yzc2M2ZhNTNkNGFlMmM1In0.eyJhdWQiOiI1OTE1NzQxZTA1Mzc5MDA4YTg3MTkxYjIiLCJqdGkiOiJjYjczYmU0NmYxZDVmM2U4OGRhOTU1YzEyZmM2YjA0Y2NlZDE0MWEyYWM5Y2EwNmY1ZGE0MzNlZjk2YjZlMGEzNGM3NjNmYTUzZDRhZTJjNSIsImlhdCI6MTQ5NTA3OTU4NCwibmJmIjoxNDk1MDc5NTg0LCJleHAiOjE0OTYzNzU1ODQsInN1YiI6IjU5MWQxYWEwMDUzNzkwMDBjMTdjY2FjNSIsInNjb3BlcyI6W119.KMugpy03M4uB_wyig9OC20q4uJE3QpyNK9ZAlhptPNKrAHSNloRHWleYrGo2WlmmGb94t9GJqicC2UOZ-V-HkJtHqyzSJGqGam4uMFTtAzgbSug4ZaRGBq2bAchaHXRyG2qKTho5tnwGGqXM1LymmH_7J5yJRrWAPqJL10wFNLNosy0A2vZqgNaq5VFOdYaY0SUxTxBOloq9kFOyNNXYd1g56s5_PuTmEHtW4kg0Q3_XOk06OkhzGVcdjuc0urTLcndbfdKNqyKzciGf3DHQgHxpXtoMvJw4KqOxR6pAkOS3ZscTKLMeso5Q8zFDr_WZSiML2Y8n7Bp3Cq3BQYJR4hjdT4I3LZIU53i00kUbDBCqPaWd_ZurJGjkc4g55shU21VIsTQ39vhDDaAeNccsxgmfkvRW_3qdxUDSn5mToNZ5JDvhBU3ucZdC013d9cTvTBOKRZyHtnJ9xNoN2WDJr7mB2yDDREfJ2PKSTc_3h5WiPORKkZdHxJJS4yEoA4O8FU0REXIjqRivaKegrRMmt7M2c0DzOGFNw0zELkrCGM8QiHd0-YxUSGqXznakej49xNYsCHyyyQhMJVhu2sGXa2ojkdO7h46HEAQA6iYs2vClN31jmqe7RZny6Isy9TG_VIcClTgKz5v1knK8nfIX1olJBELm_27sRZqVAI5B7jg",
    "refresh_token": "p6ke+eMGbL4qMLuz9PejfoCDDJHGLTfaYM3ZOeWyU0tRYb1oV58mr1N0VntAH4zK2KoO3mm//rPafthBzdkObTnBQLdgPVNFzh2RCQbF62H5eMttF7Nl9ktgctv4cu3wgA1gSNoV25w998TVwa+ZKancpXlbCFQTy6cvBNRj8K7NGBaw8H4iA9Bh2x9aFPu2Gz9Lf+ZT7JIrBvrW2Z3luAuKH5Q47ijuZb3khhu3CUN693SxMIPP7ky8sh8xG1gqDiPLCDigqsF0SDJnc0KfVPRsBCWgLoHv50eAgS8RsamJM8mhxOqR8QBUhlpLUD0EKAdm4Xz6lJiwAHGEf/HPJMIEcbSr3vW9X7AqEHoFwHLxszGxOwFNSt5UpwWYoW3KA7biAbSthPEWoA8ox3uLnG0Ba40nviiCzPauEKVDFYtC3yoHBsevvKsxtLHgbO7DHVreI3fhJyAESFYLke1nh+UTeERLOpkXX1ZL+cGXJVADbUj6IfH+z0hooRf1p86xW2xqihGnztRC9r4yqjM1BUwITlFDDlN2jc3LrdGRfMr4Gtm5DYnqL6fA53hjK1KrB8+dlBg7Ly6rIwC4kDaPYIu1lq6n9uEWOp4Gqk3hQA4Jq9E9thcIBQpf1gFz8hV+T+1c8+fNIGj75ZOzkVz3Tn2cK1bMsDbxqdq1JnJ6tII="
  }
}

` `

*** 错误JSON示例 ***

` ``

{
  "code": -100004,
  "error": "The user credentials were incorrect."
}

` ``

### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-1100002|   Iot App Interface 头部信息缺失 | |
|-100001|   invalid_request |   oauth缺失|
|-100002|   unsupported_grant_type |    无效的grat_type|
|-100003|   invalid_client |    无效client|
|-100005|   invalid_credentials |   refresh_token无效|

关于其它错误返回值与错误代码，参见 [错误代码说明](#ErrorCode List) http的status_code为400

## 用户注册 (ok)

### /api/v1/oauth/register（用户注册）

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| client_id | true | string | domain key |
| client_secret | true | string | Domain_secret |
| grant_type | true | string | 请求类型：注册默认 register |
| username | true | string | 登入邮箱 |
| password | true | string | 登入密码 |

<b>method</b> 
post

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "token_type": "Bearer",
    "expires_in": 1296000,
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImNiNzNiZTQ2ZjFkNWYzZTg4ZGE5NTVjMTJmYzZiMDRjY2VkMTQxYTJhYzljYTA2ZjVkYTQzM2VmOTZiNmUwYTM0Yzc2M2ZhNTNkNGFlMmM1In0.eyJhdWQiOiI1OTE1NzQxZTA1Mzc5MDA4YTg3MTkxYjIiLCJqdGkiOiJjYjczYmU0NmYxZDVmM2U4OGRhOTU1YzEyZmM2YjA0Y2NlZDE0MWEyYWM5Y2EwNmY1ZGE0MzNlZjk2YjZlMGEzNGM3NjNmYTUzZDRhZTJjNSIsImlhdCI6MTQ5NTA3OTU4NCwibmJmIjoxNDk1MDc5NTg0LCJleHAiOjE0OTYzNzU1ODQsInN1YiI6IjU5MWQxYWEwMDUzNzkwMDBjMTdjY2FjNSIsInNjb3BlcyI6W119.KMugpy03M4uB_wyig9OC20q4uJE3QpyNK9ZAlhptPNKrAHSNloRHWleYrGo2WlmmGb94t9GJqicC2UOZ-V-HkJtHqyzSJGqGam4uMFTtAzgbSug4ZaRGBq2bAchaHXRyG2qKTho5tnwGGqXM1LymmH_7J5yJRrWAPqJL10wFNLNosy0A2vZqgNaq5VFOdYaY0SUxTxBOloq9kFOyNNXYd1g56s5_PuTmEHtW4kg0Q3_XOk06OkhzGVcdjuc0urTLcndbfdKNqyKzciGf3DHQgHxpXtoMvJw4KqOxR6pAkOS3ZscTKLMeso5Q8zFDr_WZSiML2Y8n7Bp3Cq3BQYJR4hjdT4I3LZIU53i00kUbDBCqPaWd_ZurJGjkc4g55shU21VIsTQ39vhDDaAeNccsxgmfkvRW_3qdxUDSn5mToNZ5JDvhBU3ucZdC013d9cTvTBOKRZyHtnJ9xNoN2WDJr7mB2yDDREfJ2PKSTc_3h5WiPORKkZdHxJJS4yEoA4O8FU0REXIjqRivaKegrRMmt7M2c0DzOGFNw0zELkrCGM8QiHd0-YxUSGqXznakej49xNYsCHyyyQhMJVhu2sGXa2ojkdO7h46HEAQA6iYs2vClN31jmqe7RZny6Isy9TG_VIcClTgKz5v1knK8nfIX1olJBELm_27sRZqVAI5B7jg",
    "refresh_token": "p6ke+eMGbL4qMLuz9PejfoCDDJHGLTfaYM3ZOeWyU0tRYb1oV58mr1N0VntAH4zK2KoO3mm//rPafthBzdkObTnBQLdgPVNFzh2RCQbF62H5eMttF7Nl9ktgctv4cu3wgA1gSNoV25w998TVwa+ZKancpXlbCFQTy6cvBNRj8K7NGBaw8H4iA9Bh2x9aFPu2Gz9Lf+ZT7JIrBvrW2Z3luAuKH5Q47ijuZb3khhu3CUN693SxMIPP7ky8sh8xG1gqDiPLCDigqsF0SDJnc0KfVPRsBCWgLoHv50eAgS8RsamJM8mhxOqR8QBUhlpLUD0EKAdm4Xz6lJiwAHGEf/HPJMIEcbSr3vW9X7AqEHoFwHLxszGxOwFNSt5UpwWYoW3KA7biAbSthPEWoA8ox3uLnG0Ba40nviiCzPauEKVDFYtC3yoHBsevvKsxtLHgbO7DHVreI3fhJyAESFYLke1nh+UTeERLOpkXX1ZL+cGXJVADbUj6IfH+z0hooRf1p86xW2xqihGnztRC9r4yqjM1BUwITlFDDlN2jc3LrdGRfMr4Gtm5DYnqL6fA53hjK1KrB8+dlBg7Ly6rIwC4kDaPYIu1lq6n9uEWOp4Gqk3hQA4Jq9E9thcIBQpf1gFz8hV+T+1c8+fNIGj75ZOzkVz3Tn2cK1bMsDbxqdq1JnJ6tII="
  }
}

` ``

*** 错误JSON示例 ***

` ``

{
  "code": -100004,
  "error": "The user credentials were incorrect."
}

` ``


### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-110001|   输入参数缺失或格式不正确 |   输入参数缺失或格式不正确|
|-130001|   注册用户名已经存在 |   注册用户名已经存在|
|-100001|   invalid_request |   oauth缺失|
|-100002|   unsupported_grant_type |    无效的grat_type|
|-100003|   invalid_client |    无效client|

关于其它错误返回值与错误代码，参见 [错误代码说明](#ErrorCode List) http的status_code为400

## ouath失效设置

### /api/oauth/logout

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b> 
Get

# 用户操作

## 获取登入用户详细(ok)

### api/v1/owner

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b> 
Get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "_id": "5927d1aa05379000c17ccd54",
    "userName": "shentraroardf99d0rff48@live.cn",
    "email": "shentraroardf99d0rff48@live.cn",
    "updateDate": "2017-05-26 14:56:42",
    "createDate": "2017-05-26 14:56:42"
  }
}

` `

*** 错误JSON示例 ***

` ``
{
  "code": "-1300003",
  "error": "未找到对应用户"
}

` ``

### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-110001|   输入参数缺失或格式不正确 | |
|-1300003|   未找到对应用户 |  |

关于其它错误返回值与错误代码，参见 [错误代码说明](#ErrorCode List) http的status_code为400

## 获取指定用户详细(ok)

### api/v1/users/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b> 
Get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "_id": "5927d1aa05379000c17ccd54",
    "userName": "shentraroardf99d0rff48@live.cn",
    "email": "shentraroardf99d0rff48@live.cn",
    "updateDate": "2017-05-26 14:56:42",
    "createDate": "2017-05-26 14:56:42"
  }
}

` `

*** 错误JSON示例 ***

` ``
{
  "code": "-1300003",
  "error": "未找到对应用户"
}

` ``

### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-110001|   输入参数缺失或格式不正确 | |
|-1300003|   未找到对应用户 |  |

关于其它错误返回值与错误代码，参见 [错误代码说明](#ErrorCode List) http的status_code为400


## 获取用户列表(ok)

### api/v1/users

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| where | false | string | 检索条件 |
| sort | false | string | 排序 |
| limit | false | string | 取多少条 |
| skip | false | string | 从xx条取 |
| count | false | string | 获取数据条数( 传递count=1  返回个数，其他返回具体数据)|

<b>method</b> 
Get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "_id": "592e9a6d05379000c17ccef1",
    "userName": "shentraroardf994rd0rff48@live.cn",
    "email": "shentraroardf994rd0rff48@live.cn",
    "updateDate": "2017-05-31 19:03:22",
    "createDate": "2017-05-31 18:26:53",
    "test": 1234,
    "acl": null
  }
}

` `

{
  "code": 1,
  "data": {
    "count": 4
  }
}

*** 错误JSON示例 ***

` ``
{
  "code": "-1300003",
  "error": "未找到对应用户"
}

` ``

### 错误返回值

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-110001|   输入参数缺失或格式不正确 | |
|-1300003|   未找到对应用户 |  |

关于其它错误返回值与错误代码，参见 [错误代码说明](#ErrorCode List) http的status_code为400

## 用户信息编辑(ok)

### api/v1/users/{objId?}(无的情况下 auth的objId)

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| userName | false | string | 用户名( 暂时没提供该的需求，因为有变更用户名这个问题在)|
| email | false | string | 邮箱( 暂时没提供该的需求，因为有变更用户名这个问题在)|
| password | false | string | 密码|
| acl | false | string | 权限|
| ... | false | string | 自定义字段|

<b>method</b> 
put

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "updateDate": "2017-06-14 11:49:26"
  }
}

` ``

## 重置密码

### /api/v1/users/passwordreset(一分钟只能调查一次)

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| email | false | string | 邮箱|

<b>method</b> 
post

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
}

` ``


# 用户角色管理

## 用户角色获取(ok)

### /api/v1/roles/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b> 
get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "_id": "59293bfa05379000c24d2105",
    "name": "13f2f4fffasdf",
    "belongRole": null,
    "createDate": "2017-05-27 16:42:34",
    "belongUser": null,
    "acl": null
  }
}

` ``


## 用户角色列表(ok)

### /api/v1/roles

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |roles<b>body</b>

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| where | flase | string | 检索条件 |
| sort | flase | string | 排序 |
| limit | flase | string | 取多少条 |
| skip | false | string | 从xx条取 |
| count | flase | string | 获取条数 |
<b>method</b> 
get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "_id": "59293bfa05379000c24d2105",
    "name": "13f2f4fffasdf",
    "belongRole": null,
    "createDate": "2017-05-27 16:42:34",
    "belongUser": null,
    "acl": null
  }
}

` ``


## 用户角色追加

### /api/roles


### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| roleName | true | string | 角色名字|
| belongRole | false | string | 所属角色 |
| belongUser | false | string | 所属用户 |
| acl | false | string | 权限 |

<b>method</b> 
post

### 返回参数

*** JSON示例 ***

` ``

{
  "code": 1,
  "data": {
    "_id": "59293bfa05379000c24d2105",
    "name": "13f2f4fffasdf",
    "belongRole": null,
    "createDate": "2017-05-27 16:42:34",
    "belongUser": null,
    "acl": null
  }
}

` ``


## 用户角色编辑

### api/v1/roles/{objId}


### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| belongRole | false | string | 所属角色 |
| belongUser | false | string | 所属用户 |
| ... | false | string | 自定义字段|

<b>请求实例说明</b>

` ``
"belongRole": {
  "__op": "AddRelation",
  "objects": [
    {
      "__type": "Pointer",
      "className": "role",
      "objectId": "TPhjGyOXin"
    },
    {
      "__type": "Pointer",
      "className": "role",
      "objectId": "NhkAxHRSRH"
    },
    {
      "__type": "Pointer",
      "className": "role",
      "objectId": "TZCGzVkyc9"
    }
  ]
}
` ``

<b>method</b> 
put

### 返回参数

*** JSON示例 ***

` ``

{
  "code": 1,
  "data": {
  }
}

` `

## 用户角色删除(暂不支持)

# Table Operation

## 对应表操作（索引,唯一键操作）

### api/v1/{class}/Opearion （表操作）

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| client_id | true | string | domain key |
| client_secret | true | string | Domain_secret |
| class | true | string | 对于存储table |
| Object | true | json | 具体操作 |


<b>method</b> 
Get

### 说明

<b>追加索引</b>

` ``
{"skills":{"__op":"AddIndex","objects":["flying","kungfu"]}}
` ``

<b>删除索引</b>

` ``
{"skills":{"__op":"AddIndex","objects":["flying","kungfu"]}}
` ``

<b>追加唯一键</b>

` ``
{"skills":{"__op":"AddUnique","objects":["flying","kungfu"]}}
` ``

 <b>删除唯一键</b>

` ``
{"skills":{"__op":"RemoveUnique","objects":["flying","kungfu"]}}
` ``


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": [
    
  ]
}

` ``

*** 错误JSON示例 ***

` ``


` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |


# Data Operation

## 根据id获取详细(ok)

### api/v1/classes/{class}/{objId}（获取数据详细详细）

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| class | true | string | 对于存储table |
| objId | true | string | 索引id |


<b>method</b> 
get


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": 
    {
      "_id": "591d4d5405379000c17ccace",
      "a": 135,
      "updateDate": "2017-05-19 15:35:35",
      "createDate": "2017-05-18 15:29:24"
    }
}
` ``

*** 错误JSON示例 ***

` ``

` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400

## 根据参数查找数据(ok)

### api/v1/classes/{class}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |


<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| where | false | string | 检索条件 |
| sort | false | string | 排序 |
| limit | false | string | 取多少条 |
| skip | false | string | 从xx条取 |
| count | false | string | 获取数据条数( 传递count=1  返回个数，其他返回具体数据)|

<b>method</b> 
get

### 说明

<b>where</b>

` ``
where={ "$or" : [ { "a" : 135 } , {" b" : 2 } ] }  //完全操作mongo sql规范
` ``

<b>sort</b>

` ``
 sort={“a”:-1}  //完全操作mongo sql规范
` ``

<b>limit</b>

` ``
limit=10
` ``

 <b>skip</b>

` ``
skip=10
` ``
 <b>count</b>

` ``
count=1
` ``


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": [
    {
      "_id": "591d4d5405379000c17ccace",
      "a": 135,
      "updateDate": "2017-05-19 15:35:35",
      "createDate": "2017-05-18 15:29:24"
    }
  ]
}

` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-9999999|   服务器错误 | |
|-100005|   登入用户信息不正确 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400

## 创建数据(ok)

### api/v1/classes/{class}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| class | true | string | 对于存储table |
| ... | false | string | 自定义字段|

<b>method</b> 
post


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": [
    {
      "_id": "591d4d5405379000c17ccace",
      "a": 135,
      "updateDate": "2017-05-19 15:35:35",
      "createDate": "2017-05-18 15:29:24"
    }
  ]
}
` ``


*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-100005|   登入用户信息不正确 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400

## 根据id 更新数据(ok)

### api/v1/classes/{class}/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| class | true | string | 对于存储table |
| objId | true | string | 索引id |
| ... | false | string | 自定义字段|

<b>method</b> 
put


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "updateDate": "2017-06-13 14:51:25"
  }
}
` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-100005|   登入用户信息不正确 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400

## 数据删除(ok)

### api/v1/classes/{class}/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| class | true | string | 对于存储table |
| objId | true | string | 索引id |


<b>method</b>
delete


### 返回参数

---

*** 正确JSON示例 ***

` ``

{
  "code": 1
}

` ``

*** 错误JSON示例 ***

` ``

` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |
|-100005|   登入用户信息不正确 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400


# 文件操作

## 追加文件
### api/v1/files/{file_name}（创建文件）

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| file | true | string | 上传文件 |
| acl | false | string | 权限 |

<b>method</b>
post

### 返回参数

---

*** 正确JSON示例 ***

` ``
{
    "code": 1,
    "data": {
        "mimeType": "text/html",
        "fileSize": 29906,
        "acl": null,
        "updateDate": "2017-06-19 09:32:18",
        "createDate": "2017-06-19 09:32:18",
        "_id": "59479a22053790778e05ae65"
    }
}

` ``



*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400



## 获取文件

### api/v1/files/{file_name}{获取文件}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b>
get

### 返回参数
  返回文件内容


## 公开获取文件

>auth认证取消，获取获得acl 中*号对象，包含read权限的用户,

### api/v1/publicfiles/{file_name}?app_id=?


### 请求参数

<b>header</b>

--只通过api请求的时候 可以传递header

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | flase | string | appid  
| version | flase | string | version

<b>method</b>
get

### 返回参数
  返回文件内容


## 获取文件url(只有公开的情况)

### api/v1/files/{file_name}/url{获取文件url}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b>
get

### 返回参数
*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "name": "test45.gif",
    "mime_type": "text/html",
    "url": "http://omron-test.oss-cn-shanghai.aliyuncs.com/51341341234arqwerwe/NvXiYfXQqIm4rIBtq3qppSUybfbXAbYYVlnpUMjo.html"
  }
}

` ``


## 公开文件设定 /私有化文件

### api/v1/files/public/{file_name}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |


<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| is_public | true | bool | 0:非公开，1:公开|


<b>method</b>
post

### 返回参数

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": []
}

` ``

## 文件更新
### api/v1/files/{file_name}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| acl | true | string | 权限 |

<b>method</b>
put

### 返回参数

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "updateDate": "2017-06-13 14:51:25"
  }
}

` ``

## 文件删除

### api/v1/files/{file_name}{删除文件}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b>
delete

### 返回参数

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": []
}

` ``

## 文件检索 
### api/v1/files

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| where | flase | string | 检索条件 |
| sort | flase | string | 排序 |
| limit | flase | string | 取多少条 |
| skip | false | string | 从xx条取 |
| count | flase | string | 获取条数 |

<b>where参数说明</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| fileName | false | string | 文件名 |
| mimeType | false | string | 文件类型 |
| fileSize | false | string | 文件大小 |
| createDate | false | string | 创建时间 |
| updateDate | false | string | 更新时间 |

<b>method</b>
get


### 返回参数

*** 正确JSON示例 ***

` ``
{
    "code": 1,
    "data": [
        {
            "_id": "59479a22053790778e05ae65",
            "mimeType": "text/html",
            "fileSize": 29906,
            "acl": null,
            "updateDate": "2017-06-19 09:32:18",
            "createDate": "2017-06-19 09:32:18"
        }
    ]
}


` ``





# push设备绑定

## push绑定登入

### api/v1/installations

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| badge | false | string | 哪种push（jpush） |
| channels | false | string |  通道 |
| deviceToken | true | string | 设备token |
| deviceType | true | string | jpush |
| sdkVersion | false | string | sdk版本 |
| timeZone | false | string | 时区  |
| acl | false | string | 跳转地址 |

<b>method</b>
post

### 返回参数

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "devicetoken": "1234123412341234",
    "devicetype": "jpu4shf",
    "appid": "12341234123",
    "version": "1341234",
    "updateDate": "2017-06-13 13:35:28",
    "createDate": "2017-06-13 13:35:28",
    "_id": "593f79a00537900dcd4073df"
  }
}

` ``


##  push设备更新

### api/v1/installations/{objId}


### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| channels | false | string | 安卓,ios |
| deviceToken | false | string | 设备token |
| deviceType | false | string | jpush |
| sdkVersion | false | string | sdk版本 |
| timeZone | false | string | 时区  |
| acl | false | string | 全新啊 |

<b>method</b>
put

### 注意
> devicetoken和devicetype同时输入的时候才会更新，输入单个时不更新

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "updateDate": "2017-06-13 14:51:25"
  }
}

` ``

## push设备取得

### api/v1/installations/{objId}

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |


<b>method</b> 
get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "_id": "593f7df005379000cc2843a4",
    "devicetoken": "1234123412341234",
    "devicetype": "jpu4ffshf",
    "channels": "{\"foo\"}",
    "appid": "12341234123",
    "version": "1341234",
    "updateDate": "2017-06-13 13:53:52",
    "createDate": "2017-06-13 13:53:52",
    "acl": null
  }
}

` ``

## push设备检索

### api/v1/installations

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| where | flase | string | 检索条件 |
| sort | flase | string | 排序 |
| limit | flase | string | 取多少条 |
| skip | false | string | 从xx条取 |
| count | flase | string | 获取条数 |

<b>method</b> 
get

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": [
    {
      "_id": "593f7df005379000cc2843a4",
      "devicetoken": "1234123412341234",
      "devicetype": "jpu4ffshf",
      "channels": "{\"foo\"}",
      "appid": "12341234123",
      "version": "1341234",
      "updateDate": "2017-06-13 13:53:52",
      "createDate": "2017-06-13 13:53:52",
      "acl": null
    }
  ]
}

` ``

## push设备删除

### api/v1/installations/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b> 
DELETE

### 返回参数

*** JSON示例 ***

` ``
{
  "code": 1,
  "data": []
}


` ``


# 通知

> 通知可以发送将来通知和即时通知，将来通知 再距离发送十分钟之内不能修改和删除。

## 通知登入

### api/v1/notification/push

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| deliveryTime | true | date | 发送时间 |
| immediateDeliveryFlag | true | bool | 是否立即配信 |
| tempCode | true | string | 发送模板 |
| data | true | object | 对应数据 |
| userSettingValue | false | string | 发送用户 |
| channel | false | string | 通道 ：jpush，sms，email |
| deliveryExpirationDate | false | string | 信息有效天数 |
| deliveryExpirationTime | false | string | 信息有效时间 |
| target | false | string | 发送对象 安卓 ios  |
| richUrl | false | string | 跳转地址 |
| category | false | string | 类别 |
| searchCondition | false | object | 検索条件 |
| title | false | string |  |
| action | false | string |  |
| dialog | false | string |  |
| badgeIncrementFlag | false | string |  |
| badgeSetting | false | string |  |
| sound | false | string |  |
| contentAvailable | false | string |  |
| category | false | string |  |
| acl | false | string | 权限 |

<b>method</b>
post


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "deliveryTime": "1234123412341234",
    "immediateDeliveryFlag": "0",
    "tempCode": "G608048771746104",
    "data": "{\"name\":\"test\",\"ps\":\"1\"}",
    "message": "你好:test,测试:1",
    "updateDate": "2017-06-15 04:50:29",
    "createDate": "2017-06-15 04:50:29",
    "_id": "5942121505379000cb2a2f49"
  }
}

` ``

*** 错误JSON示例 ***

` ``

` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-999999|   服务器错误 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400


## 通知获取


### api/v1/notification/push/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b>
get


### 返回参数说明

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| deliveryTime | true | date | 发送时间  |
| immediateDeliveryFlag | true | bool | 是否立即配信 |
| tempCode | true | string | 发送模板 |
| data | true | object | 对应数据 |
| userSettingValue | true | string | 发送用户 |
| channel | true | string | 通道 ：jpush，sms，email |
| target | true | string | 发送对象 安卓 ios  |
| richUrl | true | string | 跳转地址 |
| category | true | string | 类别 |
| deliveryExpirationDate | false | string | 信息有效天数 |
| deliveryExpirationTime | false | string | 信息有效时间 |
| status | true | int  | 下面有说明 |
> deliveryTime和immediateDeliveryFlag两个必须有一个

> stauts 说明   有bug 
数値  内容
0 未配信
1 配信中
2 配信済み
3 配信上限越えのため未送信で終了
4 エラーのため未送信で終了（API キー不正、証明書不正 等）
5 フラグOFFのため未送信で終了
6 送信完了だが一部送信でエラー発生

## 通知更新

### api/v1/notification/push/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| deliveryTime | false | date | 发送时间 |
| immediateDeliveryFlag | false | bool | 是否立即配信 |
| tempCode | false | string | 发送模板 |
| data | false | object | 对应数据 |
| userSettingValue | false | string | 发送用户 |
| channel | false | string | 通道 ：jpush，sms，email |
| deliveryExpirationDate | false | string | 信息有效天数 |
| deliveryExpirationTime | false | string | 信息有效时间 |
| target | false | string | 发送对象 安卓 ios  |
| richUrl | false | string | 跳转地址 |
| category | false | string | 类别 |
| searchCondition | false | object | 検索条件 |
| title | false | string |  |
| action | false | string |  |
| dialog | false | string |  |
| badgeIncrementFlag | false | string |  |
| badgeSetting | false | string |  |
| sound | false | string |  |
| contentAvailable | false | string |  |
| category | false | string |  |
| acl | false | string | 权限 |

<b>method</b>
put


### 返回参数


*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": {
    "updateDate": "2017-06-15 04:57:23"
  }
}


` ``

## 通知检索



### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |


<b>body</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| where | false | string | 检索条件 |
| sort | false | string | 排序 |
| limit | false | string | 取多少条 |
| skip | false | string | 从xx条取 |
| count | false | string | 获取数据条数( 传递count=1  返回个数，其他返回具体数据)|

<b>method</b> 
get

### 说明

<b>where</b>

` ``
where={ "$or" : [ { "a" : 135 } , {" b" : 2 } ] }  //完全操作mongo sql规范
` ``

<b>sort</b>

` ``
 sort={“a”:-1}  //完全操作mongo sql规范
` ``

<b>limit</b>

` ``
limit=10
` ``

 <b>skip</b>

` ``
skip=10
` ``

 <b>count</b>

` ``
count=1

` ``


### 返回参数

---

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": [
    {
      "_id": "593fd92305379000cb2a2ed5",
      "deliveryTime": "1234123412341234",
      "immediateDeliveryFlag": "jpu4fshf",
      "temp_code": "12341324",
      "data": "{\"name\":\"test\"}",
      "status": 0,
      "message": "姓名:test",
      "updateDate": "2017-06-13 12:22:59",
      "createDate": "2017-06-13 12:22:59"
    }
  ]
}

` ``

*** 错误返回值 ***

| code | msg | 说明 |
|:-------------|:-------------|:-------------|
|-9999999|   服务器错误 | |
|-100005|   登入用户信息不正确 | |

关于其它错误返回值与错误代码，参见 [错误代码说明](#errorcode) http的status_code为400



## 通知删除

### api/v1/notification/push/{objId}

### 请求参数

<b>header</b>

| 参数| 必选 | 类型 | 说明 |
|:-------------|:-------------|:-------------|:-------------|
| appid | true | string | appid
| version | true | string | version
| Authorization | true | string | token_type access_token |

<b>method</b>
delete


### 返回参数

*** 正确JSON示例 ***

` ``
{
  "code": 1,
  "data": []
}

` ``



<span id="ErrorCode List"></span>
# ErrorCode List

## 系统级错误

---

| 错误代码 | 返回msg | 详细描述 |
|:-------------:|:-------------|:-------------|
|-9999998|   系统错误，请重新操作 |  |
|-9999999|   服务器系统错误 | |

## 业务级错误

---

| 错误代码 |返回msg | 详细描述 |
|:-------------:|:-------------|:-------------|
|-100001|   oauth 请求api参数缺失 | |
|-100002|   无效的grat_type | |
|-100003|   无效client | |
|-100004|   用户名密码无效 | |
|-100005|   用户未登入 | |
|-1000001|  参数不能为空  | |
|-1100001|  参数必须输入  | |
|-1100002|   Iot App Interface 头部信息缺失 | |
|-1200001|   版本格式不正确 | |
|-1200002|   string参数格式不正确 | |
|-1200003|   参数值不是有效的format类型 | |
|-1200004|   参数值size大小不符合 | |
|-1200005|   参数值不是object对象 | |
|-1300001|   对应app 不存在 | |
|-1300002|   操作数据不存在 | |
|-1300003|   未找到对应用户 | |
|-1300004|   所在主域中未找到对应class | |
|-1300005|   未找到对应的appid | |
|-1300006|   未找到对应的domain | |
|-1300007|   未找到对应模板code | |
|-1300008|   验证token已经过期 | |
|-1300008|   验证token已经过期 | |
|-1300009|   该文件名已经存在 | |
|-1300010|   该RoleName已经存在 | |
|-1300011|   对应用户名已经存在 | |
|-1400002|   消息已经执行，不能删除 | |
|-1400003|   消息已经在处理中，以无法修改 | |
|-1500001|   操作太频繁 | |
|-1500002|   acl权限不支持 | |


