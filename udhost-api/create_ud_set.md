# 创建专区资源池 - CreateUDSet

## 简介

创建专区资源池






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDSet)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDSet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **CPU** | string | 宿主机CPU核数, 单位:个， 默认值: 32，可取值：32/48 |No|
| **Memory** | string | 内存大小, 单位: MB, 范围[65536，163840], 步长: 32768, 默认值: 163840 |No|
| **DiskSpace** | string | 数据盘大小, 单位: GB, 范围[4096,6144], 步长: 2048, 默认值: 6144 |No|
| **Name** | string | 资源池名称, 默认:ResourceBlock |No|
| **Remark** | string | 资源池备注, 默认:”” |No|
| **Tag** | string | 资源池业务组, 默认:Default |No|
| **ChargeType** | string | Year, Month默认:Year |No|
| **Quantity** | string | 购买时长，默认:1 |No|
| **Count** | string | 购买台数，范围[1] 默认:1 |No|
| **CouponId** | string | 代金券 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HostIds** | array[string] | 资源池的实例短ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn?Action=CreateUDSetInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&CPU=48
&Memory=163840
&Disk=6144
```

### 响应示例
    
```json
{
  "Action": "CreateUDSetResponse",
  "HostIds": "udset-xxx",
  "RetCode": 0
}
```





