# CC防御规则列表 - DescribeAntiCCRules

## 简介

CC防御规则列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeAntiCCRules`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Domain** | string | 要查询防护规则的域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Res** | [*AntiCcRes*](#AntiCcRes) | CC规则，参考AntiCcRes |No|

#### 数据模型


#### AntiCcRes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **State** | string | 指定域名的CC防护状态 |**Yes**|
| **Mode** | string | 指定域名的CC防护模式 |**Yes**|
| **Max** | string | CC规则最大容量 |**Yes**|
| **Rules** | array[[*AntiCcRule*](#AntiCcRule)] | CC规则列表，参考AntiCcRule |**Yes**|

#### AntiCcRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | int | 规则ID |**Yes**|
| **Uri** | string | URI |**Yes**|
| **Mode** | string | 模式 |**Yes**|
| **Duration** | int | 统计时长. 单位:秒 |**Yes**|
| **Reqs** | int | 请求次数 |**Yes**|
| **Action** | string | 执行动作 |**Yes**|
| **Validity** | string | 动作有效期,单位:分钟 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeAntiCCRules
&ProjectId=org-xxx
&Domain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "DescribeAntiCCRulesResponse",
  "Res": {
    "Max": 30,
    "Mode": "normal",
    "Rules": [
      {
        "Action": "forbidden",
        "Duration": 10,
        "Id": 43804,
        "Mode": "equal",
        "Reqs": 2,
        "Uri": "/index.html",
        "Validity": 60
      },
      {
        "Action": "forbidden",
        "Duration": 10,
        "Id": 44451,
        "Mode": "equal",
        "Reqs": 20,
        "Uri": "/index.html",
        "Validity": 60
      }
    ],
    "State": "on"
  },
  "RetCode": 0
}
```





