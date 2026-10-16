# 防火墙绑定的资源列表 - DescribeUEcFirewallResource

## 简介

防火墙绑定的资源列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEcFirewallResource`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **FirewallId** | string | 防火墙Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceSet** | array[[*ResourceInfo*](#ResourceInfo)] | 资源列表，详情参见ResourceInfo |**Yes**|
| **TotalCount** | int | 资源总数 |**Yes**|

#### 数据模型


#### ResourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源Id |**Yes**|
| **PublicIpList** | array[string] | 节点公网Ip列表 |**Yes**|
| **Name** | string | 节点名称 |**Yes**|
| **State** | int | 节点状态，1部署中，2待启动，3启动中，4运行中，5正在停止，6已停止，7正在更新，8正在重启，9正在删除， 10已经删除,11异常 |**Yes**|
| **Remark** | string | 节点备注 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEcFirewallResource
&ProjectId=eUEZHOzX
&FirewallId=SPKpaVvr
```

### 响应示例
    
```json
{
  "Action": "DescribeUEcFirewallResourceResponse",
  "ResourceSet": [
    {
      "Name": "IXhEfDOZ",
      "PublicIpList": [
        "euhKqQxD"
      ],
      "Remark": "jTdTRWKV",
      "ResourceId": "aOXjZyJl",
      "State": 5
    }
  ],
  "RetCode": 0,
  "TotalCount": 7
}
```





