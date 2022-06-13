# 获取云手机支持绑定独立IP的城市列表 - DescribeUPhoneIpRegions

## 简介

获取云手机支持绑定独立IP的城市列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneIpRegions`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，eg: cn-shanghai, cn-hangzhou |**Yes**|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Regions** | array[[*IpRegion*](#IpRegion)] | 独立IP地域信息。 |**Yes**|
| **TotalCount** | int | 总数量 |No|

#### 数据模型


#### IpRegion

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 已开通地域。参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **StockStatus** | string | 库存状态。枚举值：有库存：Available；无库存：SoldOut |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneIpRegions
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=xOrhNUTr
&CityId=wtchwGYc
&BizType=SfqqISyb
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneIpRegionsResponse",
  "Region": "aFGBvKqC",
  "RetCode": 0,
  "TotalCount": 1
}
```





