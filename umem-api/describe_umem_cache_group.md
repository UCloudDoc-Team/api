# 显示Memcache - DescribeUMemcacheGroup

## 简介

显示Memcache





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemcacheGroup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemcacheGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **GroupId** | string | 组的ID,如果指定则获取描述，否则为列表操 作,需指定Offset/Limit |No|
| **Offset** | int | 分页显示的起始偏移, 默认值为0 |No|
| **Limit** | int | 分页显示的条目数, 默认值为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 组的总的节点个数 |No|
| **DataSet** | array[[*UMemcacheGroupSet*](#UMemcacheGroupSet)] | 组列表,参见 UMemcacheGroupSet |No|

#### 数据模型


#### UMemcacheGroupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupId** | string | 组ID |No|
| **Name** | string | 组名称 |No|
| **ConfigId** | string | 节点的配置ID |No|
| **VirtualIP** | string | 节点的虚拟IP地址 |No|
| **Port** | int | 节点分配的服务端口 |No|
| **Size** | int | 容量单位GB |No|
| **UsedSize** | int | 使用量单位MB |No|
| **Version** | string | Memcache版本信息,默认为1.4.31 |No|
| **State** | string | 状态标记 Creating // 初始化中 CreateFail // 创建失败 Deleting // 删除中 DeleteFail // 删除失败 Running // 运行 Resizing // 容量调整中 ResizeFail // 容量调整失败 Configing // 配置中 ConfigFail // 配置失败Restarting // 重启中 |No|
| **CreateTime** | int | 创建时间 (UNIX时间戳) |No|
| **ModifyTime** | int | 修改时间 (UNIX时间戳) |No|
| **ExpireTime** | int | 过期时间 (UNIX时间戳) |No|
| **ChargeType** | string | 计费类型:Year,Month,Dynamic 默认Dynamic |No|
| **Tag** | string | 业务组名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemcacheGroup
&Region=cn-east-01
&GroupId=umemcache-00f986
&Offset=0
&Limit=20
&Tag=Default
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemcacheGroupResponse",
  "DataSet": [
    {
      "ChargeType": "Month",
      "ConfigId": "9a891891-c245-4b66-bcexxxxxxxxx",
      "CreateTime": 1522222,
      "ExpireTime": 12345,
      "GroupId": "umemcache-xxxxx",
      "ModifyTime": 1522222,
      "Name": "test1233",
      "Port": 11211,
      "Size": 2,
      "State": "Running",
      "Tag": "Default",
      "UsedSize": 0,
      "Version": "1.4.33",
      "VirtualIP": "x.xx.x.x"
    }
  ],
  "RetCode": 0
}
```





