# 创建USMC迁移计划 - CreateUSMCPlan

## 简介

创建USMC迁移计划









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUSMCPlan`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 名称，长度不能超过 128 |**Yes**|
| **SourceVendor** | string | 迁移源，可取值 “Ali、Tecent、IDC、Huawei、Amazon” |**Yes**|
| **SourceRegion** | string | 迁移来源地域 |**Yes**|
| **TargetRegion** | string | 迁移目标地域 |**Yes**|
| **NetworkType** | string | 网络类型， 10:外网, 20: 内网, 30:专线。 默认10：外网 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*CreatePlanResData*](#CreatePlanResData) | CreatePlanResData |**Yes**|

#### 数据模型


#### CreatePlanResData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PlanId** | string | 迁移计划ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUSMCPlan
&Name=rmvfupfL
&SourceVendor=sLaorqHq
&SourceRegion=NMRiCsGz
&TargetRegion=LIzZTRLB
&NetworkType=dLNBcUHK
&ProjectId=GODKXUnL
&ProjectId=RhLwgeXu
```

### 响应示例
    
```json
{
  "Action": "CreateUSMCPlanResponse",
  "Data": "aWdcVAmx",
  "Message": "yCphtYrj",
  "RetCode": 0
}
```





