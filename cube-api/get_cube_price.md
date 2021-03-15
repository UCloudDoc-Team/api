# 获取cube的价格 - GetCubePrice

## 简介

获取cube的价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCubePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Count** | string | 购买数量 |**Yes**|
| **Cpu** | string | cpu配置 |**Yes**|
| **Mem** | string | 内存配置 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按秒后付费，默认为月付 |No|
| **Quantity** | string | 购买时长。默认:值 1。按小时购买（Dynamic/Postpay）时无需此参数。 月付时，此参数传0，代表购买至月末。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int |  |**Yes**|
| **OriginalPrice** | string |  |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCubePrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=WcYmOlWO
&Count=crmBHpsf
&Cpu=giPvbWun
&Mem=FSlShRcN
&ChargeType=YLtBxuvr
&Quantity=ILiBsGAn
```

### 响应示例
    
```json
{
  "Action": "GetCubePriceResponse",
  "OriginalPrice": "FWYRdDnz",
  "Price": 4,
  "RetCode": 0
}
```





