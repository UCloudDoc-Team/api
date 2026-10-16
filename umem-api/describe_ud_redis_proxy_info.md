# 拉取udredis代理信息 - DescribeUDRedisProxyInfo

## 简介

拉取udredis所有的代理信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDRedisProxyInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDRedisProxyInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SpaceId** | string | udredis实例id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDRedisProxyInfo*](#UDRedisProxyInfo)] | 代理数据集 |**Yes**|

#### 数据模型


#### UDRedisProxyInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 代理资源id |**Yes**|
| **ProxyId** | string | 代理id |**Yes**|
| **Vip** | string | 代理ip |**Yes**|
| **State** | string | 代理状态 [PROXY_CREATING:创建中, PROXY_NORMAL:正常运行, PROXY_FAILED:创建失败, PROXY_CLOSED:关闭, PROXY_INIT_RESIZE:初始化核数调整, PROXY_WAIT_RESIZE:等待核数调整, PROXY_RESIZING:核数调整中, PROXY_RESIZE_ERROR:核数调整失败] |**Yes**|
| **CPU** | int | 代理CPU核数 |**Yes**|
| **ProxyType** | int | 0 : 物理机版分布式代理, 1: NVME(或SSD)版分布式代理 |**Yes**|
| **PublicIp** | string | 开启外网状态下的外网IP，否则为空 |No|
| **SupportReadOnly** | boolean | 代理是否支持设置为只读 |No|
| **ReadOnly** | boolean | 代理是否为只读 |No|
| **ReadMode** | string | 读写分离策略, "Custom": 用户自定义节点权重， "Uniform": 包括主节点在内的所有节点平均读请求， "ReadOnly": 读请求均分至只读节点 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDRedisProxyInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=TjgvEJaX
&SpaceId=WACSTNZf
```

### 响应示例
    
```json
{
  "Action": "DescribeUDRedisProxyInfoResponse",
  "DataSet": [
    {
      "CPU": 6,
      "ProxyId": "wjhBFGjw",
      "ProxyType": 4,
      "ResourceId": "gVaugysY",
      "State": "HnRVTTox",
      "Vip": "XbBCnxli"
    }
  ],
  "RetCode": 0
}
```





