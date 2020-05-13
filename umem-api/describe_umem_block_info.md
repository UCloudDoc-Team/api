# 拉取UDRedis分片信息 - DescribeUMemBlockInfo

## 简介

拉取UDRedis分片信息

?> 返回参数中，BlockSlotBegin/BlockSlotEnd 现部分机房支持，后续会全部机房支持



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemBlockInfo)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemBlockInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SpaceId** | string | UMem内存资源ID |**Yes**|
| **Offset** | int | 分页显示的起始偏移, 默认值为0 |**Yes**|
| **Limit** | int | 分页显示的条目数, 默认值为10 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UMemBlockInfo*](#UMemBlockInfo)] | 分布式redis 分片信息 |No|

#### 数据模型


#### UMemBlockInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BlockId** | string | 分片id |**Yes**|
| **BlockVip** | string | 分片ip |**Yes**|
| **BlockPort** | int | 分片端口 |**Yes**|
| **BlockSize** | int | 容量单位GB |**Yes**|
| **BlockUsedSize** | int | 使用量单位MB |**Yes**|
| **BlockState** | string | 实例状态 Starting // 创建中 Creating // 初始化中 CreateFail // 创建失败 Fail // 创建失败 Deleting // 删除中 DeleteFail // 删除失败 Running // 运行 Resizing // 容量调整中 ResizeFail // 容量调整失败 Configing // 配置中 ConfigFail // 配置失败Restarting // 重启中 SetPasswordFail //设置密码失败 |**Yes**|
| **BlockSlotBegin** | int | 分片维护的键槽起始值 |**Yes**|
| **BlockSlotEnd** | int | 分片维护的键槽结束值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemBlockInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=bBnOfqXi
&SpaceId=hKeZnYaq
&Offset=6
&Limit=6
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemBlockInfoResponse",
  "DataSet": [
    {
      "BlockId": "HAxVumkh",
      "BlockPort": 6,
      "BlockVip": "cwTBbxuy"
    }
  ],
  "RetCode": 0
}
```





