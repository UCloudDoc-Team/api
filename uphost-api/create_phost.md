# 创建物理机 - CreatePHost

## 简介

指定数据中心，根据资源使用量创建指定数量的UPHost物理云主机实例。

?> 密码需要通过base64进行编码<br /><br /># echo -n password1 \| base<br />cGFzc3dvcmQx




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreatePHost)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreatePHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageId** | string | ImageId，可以通过接口 [DescribePHostImage](api/uphost-api/describe_phost_image.html)获取 |**Yes**|
| **Password** | string | 密码（密码需使用base64进行编码） |**Yes**|
| **Type** | string | 物理机类型，默认为：db-2(基础型-SAS-V3) |No|
| **Name** | string | 物理机名称，默认为phost |No|
| **Remark** | string | 物理机备注，默认为空 |No|
| **Tag** | string | 业务组，默认为default |No|
| **ChargeType** | string | 计费模式，枚举值为：Year, 按年付费； Month,按月付费；默认按月付费 |No|
| **Quantity** | string | 购买时长，1-10个月或1-10年；默认值为1。月付时，此参数传0，代表购买至月末，1代表整月。 |No|
| **SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **Raid** | string | 本地盘和裸金属1.0需要的参数。Raid配置，默认Raid10  支持:Raid0、Raid1、Raid5、Raid10，NoRaid |No|
| **VPCId** | string | VPC ID，不填为默认，VPC2.0下需要填写此字段。 |No|
| **SubnetId** | string | 子网ID，不填为默认，VPC2.0下需要填写此字段。 |No|
| **Cluster** | string | 网络环境，可选千兆：1G ，万兆：10G， 默认1G。智能网卡可以选择25G。 |No|
| **Disks.N.IsBoot** | string | 裸金属机型参数->是否是系统盘。枚举值： True，是系统盘。 False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |No|
| **Disks.N.Type** | string | 裸金属机型参数->磁盘类型：枚举值：CLOUD_RSSD |No|
| **Disks.N.Size** | int | 裸金属机型参数->磁盘大小，单位GB，必须是10GB的整数倍。系统盘20-500GB，数据盘单块盘20-32000GB。 |No|
| **Disks.N.CouponId** | string | 裸金属机型参数->云盘代金券id。不适用于系统盘。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|
| **VpcIp** | string | 指定内网ip创建 |No|
| **ActivityId** | int | 短期促销活动时所需参数 |No|
| **RuleId** | int | 短期促销活动时所需参数 |No|
| **NetworkInterface.N.EIP.Bandwidth** | string | 【若绑定EIP，此参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式必须指定0M带宽, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800] |No|
| **NetworkInterface.N.EIP.PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式,默认为 "Bandwidth" |No|
| **NetworkInterface.N.EIP.ShareBandwidthId** | string | 绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效 |No|
| **NetworkInterface.N.EIP.OperatorName** | string | 【若绑定EIP，此参数必填】弹性IP的线路。枚举值: 国际: International BGP: Bgp 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International |No|
| **NetworkInterface.N.EIP.CouponId** | string | 当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看。 |No|
| **CouponId** | string | 代金券 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PHostId** | array[string] | PHost的资源ID数组 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreatePHost
&Region=BqkGovfY
&Zone=iDdYQGOm
&ProjectId=fElWtlMQ
&ImageId=sxdCFGzq
&Password=nMNtjgYM
&Type=lHQxZUvy
&Name=mxqNHeqr
&Remark=tujHeoKztbfagmsbNAwQgkBFzfCLTWUNuXKpwQXtzQwFNdMawOyPRouLdZMuezKkyHmHvujRLBCwZqNYFtmehSDdowWzpXUuMmWgjnkyerzgncXzMxhoQTEOTkuPSojp
&Tag=uerGHrup
&ChargeType=BuChuPmk
&Quantity=DgbHAEBp
&Count=6
&SecurityGroupId=DuueiYgv
&Raid=XDJZHSQt
&VPCId=JoyUhbrc
&SubnetId=YBMQSOOj
&Cluster=BTJvvyCm
&Disks.N.IsBoot=UxWWeVmL
&Disks.N.Type=NjRvbaPt
&Disks.N.Size=7
&Disks.N.CouponId=NKehxKWX
&CouponId=nDNLOYMb
&VpcIp=UZNQMwbL
&ActivityId=7
&RuleId=5
&CharacterName=rBuhSnga
&NetworkInterface.N.EIP.Bandwidth=BsEioBBJ
&NetworkInterface.N.EIP.PayMode=HKUSPfdn
&NetworkInterface.N.EIP.ShareBandwidthId=ORapYtXt
&NetworkInterface.N.EIP.OperatorName=Ipkulqrt
&NetworkInterface.N.EIP.CouponId=jqGeqYvH
&NetworkInterface.N.EIP.Bandwidth=XIOVRpWP
&NetworkInterface.N.EIP.PayMode=akQZEiQl
&NetworkInterface.N.EIP.ShareBandwidthId=OFPiSwyR
&NetworkInterface.N.EIP.OperatorName=wwKNXlZu
&NetworkInterface.N.EIP.CouponId=yfCllFRn
```

### 响应示例
    
```json
{
  "Action": "CreatePHostResponse",
  "PHostId": [
    "FLICopDY"
  ],
  "RetCode": 0
}
```





