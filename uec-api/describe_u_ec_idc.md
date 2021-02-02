# 获取IDC机房列表 - DescribeUEcIDC

## 简介

获取IDC机房列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEcIDC`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Cpu** | int | 节点cpu核数 |**Yes**|
| **Memory** | int | 节点内存大小， 单位GB |**Yes**|
| **IdcId.N** | string | Idc机房id。默认全部机房 |No|
| **Type** | int | 0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通 |No|
| **ProductType** | string | 产品类型：normal（通用型），hf（高主频型） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IdcList** | array[[*IdcInfo*](#IdcInfo)] | 获取的机房信息，具体参考下面IdcInfo |No|

#### 数据模型


#### IdcInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IdcId** | string | 机房ID |No|
| **Name** | string | 机房名称 |No|
| **Isp** | string | 运营商 |No|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|
| **Type** | int | 运营商类型：0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通 |No|
| **MaxNodeCnt** | int | 机房可创建节点最大数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEcIDC
&ProjectId=XHBoiRSj
&Cpu=7
&Memory=8
&IdcId.n=PdMVSOSi
&Type=6
&ProductType=ddqgeqRa
```

### 响应示例
    
```json
{
  "Action": "DescribeUEcIDCResponse",
  "IdcList": [
    {
      "City": "VdDHNjAs",
      "IdcId": "pVKHWgIX",
      "Isp": "fPLwPtTx",
      "MaxNodeCnt": 4,
      "Name": "iPVUPLiU",
      "Province": "kzPqdCtX",
      "Type": 6
    }
  ],
  "RetCode": 0
}
```





