# 获取成员列表 - DescribeMemberList

## 简介

获取成员列表，限主账号使用。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeMemberList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeMemberList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，请参考[GetProjectList接口](api/summary/get_project_list)。不填写为查询所有项目。 |No|
| **Offset** | string | 成员列表的偏移量，默认为0 |No|
| **Limit** | string | 成员列表的最大数量，默认为200 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MemberSet** | array[[*MemberInfo*](#MemberInfo)] | JSON格式的成员列表实例 |**Yes**|
| **TotalCount** | int | 成员总数 |**Yes**|

#### 数据模型


#### MemberInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MemberEmail** | string | 成员邮箱 |**Yes**|
| **MemberPhone** | string | 成员手机 |**Yes**|
| **MemberName** | string | 成员名字 |**Yes**|
| **MemberPosition** | string | 成员地址 |**Yes**|
| **MemberQQ** | string | 成员QQ |**Yes**|
| **PublicKey** | string | 公钥 |**Yes**|
| **LastRegionId** | string | 最后访问的机房 |**Yes**|
| **DefultProjectId** | string | 默认项目 |**Yes**|
| **LastLogin** | int | 最后一次登录时间 |**Yes**|
| **Created** | int | 创建时间 |**Yes**|
| **State** | string | 状态 |**Yes**|
| **IsAdmin** | int | 是否主账号（0：子账号，1：主账号） |**Yes**|
| **IsFinance** | int | 是否有财务权限（0：无财务权限，1：有财务权限） |**Yes**|
| **ProjectSet** | array[[*ProjectInfo*](#ProjectInfo)] | 项目列表 |**Yes**|
| **ActivateFlag** | int | 激活状态（0：未激活，1：已激活） |**Yes**|
| **PasswordPolicyDate** | int | 密码安全策略开启时间，格式：unix timestamp |**Yes**|
| **TOTPStatus** | int | TOTP状态（0：未开启，1：已开启） |**Yes**|

#### ProjectInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **ProjectName** | string | 项目名 |**Yes**|
| **CharacterId** | string | 角色ID |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeMemberList
&ProjectId=gVhmRqSF
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribeMemberListResponse",
  "MemberSet": [
    {
      "ActivateFlag": 1,
      "Created": 1524125597,
      "DefultProjectId": "bjwoig",
      "IsAdmin": 1,
      "IsFinance": 0,
      "LastLogin": 0,
      "LastRegionId": "cn-east-04",
      "MemberEmail": "test1@ucloud.cn",
      "MemberName": "LGwo4hy",
      "MemberPhone": "(86)12345678901",
      "MemberPosition": "lBHo2",
      "MemberQQ": "BHow3",
      "PasswordPolicyDate": 0,
      "ProjectSet": [
        {
          "CharacterId": "Lbhi2bw",
          "ProjectId": "fzzfcBg1",
          "ProjectName": "gejaE45"
        }
      ],
      "PublicKey": "BLihwFHoiyo24ihyLIBHFOIWRgho24yosihdlh+=",
      "State": "Normal",
      "TOTPStatus": 0
    },
    {
      "ActivateFlag": 1,
      "Created": 1524125597,
      "DefultProjectId": "Bliwhe",
      "IsAdmin": 1,
      "IsFinance": 0,
      "LastLogin": 0,
      "LastRegionId": "cn-east-03",
      "MemberEmail": "test2@ucloud.cn",
      "MemberName": "xnwo33y",
      "MemberPhone": "(86)12345678902",
      "MemberPosition": "LBho2",
      "MemberQQ": "BHJowf",
      "PasswordPolicyDate": 0,
      "ProjectSet": [
        {
          "CharacterId": "gwhoeigh",
          "ProjectId": "BHOWIlgho",
          "ProjectName": "woihgoBH"
        }
      ],
      "PublicKey": "xLihwFHoiyo114gyLBWOHFOIWRgho24yosi23dl42BSk",
      "State": "Normal",
      "TOTPStatus": 0
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





