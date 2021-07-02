# 获取UMem列表 - DescribeUMem

## 简介

获取UMem列表

?> (Protocol=redis:展示主备Redis以及分布式Redis; Protocol= memcache:展示单机memcache)




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMem)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMem`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Protocol** | string | 协议类型: memcache, redis |No|
| **Offset** | int | 分页显示的起始偏移, 默认值为0 |No|
| **Limit** | int | 分页显示的条目数, 默认值为20 |No|
| **ResourceId** | string | 资源ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 根据过滤条件得到的总数 |No|
| **DataSet** | array[[*UMemDataSet*](#UMemDataSet)] | UMem实例列表, 详细参见UMemDataSet |No|

#### 数据模型


#### UMemDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 实例所在可用区，或者master redis所在可用区，参见 [可用区列表](api/summary/regionlist) |No|
| **OwnSlave** | string | 是否拥有只读Slave<br />“Yes” 包含<br />“No” 不包含 |**Yes**|
| **DataSet** | array[[*UMemSlaveDataSet*](#UMemSlaveDataSet)] | UMEM实例列表 UMemSlaveDataSet 如果没有slave，则没有该字段 |No|
| **Role** | string | 表示实例是主库还是从库,master,slave<br />仅主备redis返回该项参数 |No|
| **RewriteTime** | int | 主备redis和分布式redis运维时间<br />0  //0点<br />1  //1点<br />以此类推<br />单机版memcache不返回该项 |No|
| **VPCId** | string | vpc |No|
| **SubnetId** | string | 子网 |No|
| **ResourceId** | string | 资源ID |No|
| **Name** | string | 资源名称 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 到期时间 |No|
| **Type** | string | 空间类型:single(无热备),double(热备) |No|
| **Protocol** | string | 协议类型: memcache, redis |No|
| **Size** | int | 容量单位GB |No|
| **UsedSize** | int | 使用量单位MB |No|
| **State** | string | 实例状态                                  Starting                  // 创建中       Creating                  // 初始化中     CreateFail                // 创建失败     Fail                      // 创建失败     Deleting                  // 删除中       DeleteFail                // 删除失败     Running                   // 运行         Resizing                  // 容量调整中   ResizeFail                // 容量调整失败 Configing                 // 配置中       ConfigFail                // 配置失败Restarting                // 重启中<br />SetPasswordFail    //设置密码失败 |No|
| **ChargeType** | string | 计费模式，Year, Month, Dynamic, Trial |No|
| **Address** | array[[*UMemSpaceAddressSet*](#UMemSpaceAddressSet)] | IP端口信息请，参见UMemSpaceAddressSet |No|
| **Tag** | string | 业务组名称 |No|
| **ResourceType** | string | distributed: 分布式版Redis,或者分布式Memcache；single：主备版Redis,或者单机Memcache；performance：高性能版 |No|
| **ConfigId** | string | 节点的配置ID |No|
| **AutoBackup** | string | 是否需要自动备份,enable,disable |No|
| **BackupTime** | int | 自动备份开始时间,单位小时计,范围[0-23] |No|
| **HighAvailability** | string | 是否开启高可用,enable,disable |No|
| **Version** | string | Redis版本信息 |No|
| **SlaveZone** | string | 跨机房URedis，slave redis所在可用区，参见 [可用区列表](api/summary/regionlist) |No|

#### UMemSlaveDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 实例所在可用区，或者master redis所在可用区，参见 [可用区列表](api/summary/regionlist) |No|
| **SubnetId** | string | 子网 |**Yes**|
| **VPCId** | string | vpc |**Yes**|
| **VirtualIP** | string |  |**Yes**|
| **RewriteTime** | int | 主备Redis返回运维时间 0//0点 1 //1点 以此类推 |No|
| **MasterGroupId** | string | 主实例id |No|
| **GroupId** | string | 资源id |No|
| **Port** | int | 端口 |No|
| **MemorySize** | int | 实力大小 |No|
| **GroupName** | string | 资源名称 |No|
| **Role** | string | 表示实例是主库还是从库,master,slave |No|
| **ModifyTime** | int | 修改时间 |No|
| **Name** | string | 资源名称 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 到期时间 |No|
| **Size** | int | 容量单位GB |No|
| **UsedSize** | int | 使用量单位MB |No|
| **State** | string | 实例状态                                  Starting                  // 创建中       Creating                  // 初始化中     CreateFail                // 创建失败     Fail                      // 创建失败     Deleting                  // 删除中       DeleteFail                // 删除失败     Running                   // 运行         Resizing                  // 容量调整中   ResizeFail                // 容量调整失败 Configing                 // 配置中       ConfigFail                // 配置失败Restarting                // 重启中<br />SetPasswordFail  //设置密码失败 |No|
| **ChargeType** | string | 计费模式，Year, Month, Dynamic, Trial |No|
| **Tag** | string | 业务组名称 |No|
| **ResourceType** | string | distributed: 分布式版Redis,或者分布式Memcache；single：主备版Redis,或者单机Memcache；performance：高性能版 |No|
| **ConfigId** | string | 节点的配置ID |No|
| **Version** | string | Redis版本信息 |No|

#### UMemSpaceAddressSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | UMem实例访问IP |No|
| **Port** | int | UMem实例访问Port |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMem
&Region=CYfSjtfA
&Offset=5
&Limit=5
&ResourceId=wnfMfnQr
&Protocol=cGcleCur
&ProjectId=tWfLNsOR
&公共参数＝
&Zone=ATRtBpOx
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemResponse",
  "DataSet": [
    {
      "Address": [
        {
          "IP": "xdTFKPdq",
          "Port": 5
        },
        {
          "IP": "ICaNxwru",
          "Port": 1
        },
        {
          "IP": "KZqbVrIc",
          "Port": 7
        }
      ],
      "AutoBackup": "ooioDhuV",
      "BackupTime": 4,
      "ChargeType": "MtCuMDNq",
      "ConfigId": "GGDQMFVL",
      "CreateTime": 5,
      "ExpireTime": 1,
      "HighAvailability": "xYGVItde",
      "Name": "wTABuadt",
      "Protocol": "CMbNPLru",
      "ResourceId": "KNhCzsnD",
      "ResourceType": "nedYlOcN",
      "Size": 7,
      "State": "PkNmCXOe",
      "Tag": "BEgtahwU",
      "Type": "NOfFjyhX",
      "UsedSize": 4,
      "Version": "zFhXccwi"
    },
    {
      "Address": [
        {
          "IP": "ZTodkDol",
          "Port": 1
        },
        {
          "IP": "QkzdFKDl",
          "Port": 1
        },
        {
          "IP": "hwUHGGVi",
          "Port": 6
        },
        {
          "IP": "gJavQdmG",
          "Port": 2
        },
        {
          "IP": "OrwRojjw",
          "Port": 2
        },
        {
          "IP": "eJUebkxS",
          "Port": 5
        },
        {
          "IP": "uMVPWLkH",
          "Port": 6
        }
      ],
      "AutoBackup": "NfcBLyQI",
      "BackupTime": 5,
      "ChargeType": "uiZoHzyi",
      "ConfigId": "gDsoivjx",
      "CreateTime": 1,
      "ExpireTime": 8,
      "HighAvailability": "XrzqTFzK",
      "Name": "AbjCxxLb",
      "Protocol": "XzuuhHjf",
      "ResourceId": "HJjSlGLt",
      "ResourceType": "InWvDkJP",
      "Size": 9,
      "State": "VIjpXSCn",
      "Tag": "XSVehmBE",
      "Type": "ANOGVpPO",
      "UsedSize": 9,
      "Version": "ZFUDNVDq"
    },
    {
      "Address": [
        {
          "IP": "YShqePzv",
          "Port": 3
        },
        {
          "IP": "spznbmgM",
          "Port": 5
        },
        {
          "IP": "XCFVsQlL",
          "Port": 7
        },
        {
          "IP": "jCAUupec",
          "Port": 2
        },
        {
          "IP": "KorEUnXh",
          "Port": 6
        },
        {
          "IP": "LmcAuhbk",
          "Port": 7
        },
        {
          "IP": "CIvqCUOK",
          "Port": 4
        }
      ],
      "AutoBackup": "MQJPoYQr",
      "BackupTime": 5,
      "ChargeType": "CQviKnot",
      "ConfigId": "HBrVFASw",
      "CreateTime": 4,
      "ExpireTime": 5,
      "HighAvailability": "hVLLcNWN",
      "Name": "RZKzvpmh",
      "Protocol": "bAWgrRHF",
      "ResourceId": "eTwaSUzH",
      "ResourceType": "KoCPtlax",
      "Size": 3,
      "State": "wQidxUHZ",
      "Tag": "sRUNzpSY",
      "Type": "yoUDmTJX",
      "UsedSize": 4,
      "Version": "AYXbCivF"
    },
    {
      "Address": [
        {
          "IP": "cnjJWGva",
          "Port": 1
        },
        {
          "IP": "rAHqmynD",
          "Port": 1
        },
        {
          "IP": "VzuCmpAa",
          "Port": 9
        },
        {
          "IP": "IkVbzRfq",
          "Port": 4
        },
        {
          "IP": "CNPNweAR",
          "Port": 4
        },
        {
          "IP": "BsJAozyf",
          "Port": 4
        },
        {
          "IP": "vUFqoJBj",
          "Port": 7
        },
        {
          "IP": "ofvvqQZh",
          "Port": 7
        },
        {
          "IP": "FIraTIGo",
          "Port": 4
        }
      ],
      "AutoBackup": "vwdSLHVA",
      "BackupTime": 4,
      "ChargeType": "GwJzioLi",
      "ConfigId": "ULiQaVgb",
      "CreateTime": 1,
      "ExpireTime": 2,
      "HighAvailability": "nuuhdpWH",
      "Name": "QbmhcsNf",
      "Protocol": "gdeIrjKg",
      "ResourceId": "jIqIpSAp",
      "ResourceType": "fQrimsOM",
      "Size": 4,
      "State": "rxFqmOZf",
      "Tag": "kMmEoasr",
      "Type": "EVnsmeNx",
      "UsedSize": 9,
      "Version": "wEujwBHY"
    },
    {
      "Address": [
        {
          "IP": "wUfpOUYA",
          "Port": 5
        },
        {
          "IP": "BvSpBiLa",
          "Port": 3
        },
        {
          "IP": "FSUgdGnL",
          "Port": 7
        },
        {
          "IP": "GGixhLIS",
          "Port": 4
        },
        {
          "IP": "gQUiMBYV",
          "Port": 6
        },
        {
          "IP": "nejHKCBI",
          "Port": 5
        }
      ],
      "AutoBackup": "nzEkQVyH",
      "BackupTime": 6,
      "ChargeType": "qgxkWoPM",
      "ConfigId": "AIvmSCoB",
      "CreateTime": 9,
      "ExpireTime": 7,
      "HighAvailability": "qjqzRjHG",
      "Name": "ChBOhqxj",
      "Protocol": "lhgSDftR",
      "ResourceId": "bUTXOjYY",
      "ResourceType": "VylaOIJV",
      "Size": 2,
      "State": "ImYqMePS",
      "Tag": "CmCJJYAa",
      "Type": "vRdQdGTT",
      "UsedSize": 8,
      "Version": "QwICJfTd"
    },
    {
      "Address": [
        {
          "IP": "mQoEctdQ",
          "Port": 3
        },
        {
          "IP": "uZgHKYee",
          "Port": 5
        },
        {
          "IP": "leDBpMoL",
          "Port": 9
        },
        {
          "IP": "TsSuhKXT",
          "Port": 1
        },
        {
          "IP": "lOSGqWkY",
          "Port": 7
        },
        {
          "IP": "FBkomBaQ",
          "Port": 8
        },
        {
          "IP": "KtyyPoRv",
          "Port": 3
        },
        {
          "IP": "ukYmYeQa",
          "Port": 5
        }
      ],
      "AutoBackup": "anPEPEmG",
      "BackupTime": 1,
      "ChargeType": "wAffwhKn",
      "ConfigId": "ytRPrLgJ",
      "CreateTime": 5,
      "ExpireTime": 1,
      "HighAvailability": "JpeCMIqP",
      "Name": "RDFvxajX",
      "Protocol": "yJqpAmSN",
      "ResourceId": "roBVpTyn",
      "ResourceType": "HgncGXuN",
      "Size": 6,
      "State": "FyPMYAsH",
      "Tag": "NQMMBDrh",
      "Type": "saCvAuJl",
      "UsedSize": 3,
      "Version": "EkuVHZhK"
    },
    {
      "Address": [
        {
          "IP": "mvrqcHWI",
          "Port": 5
        },
        {
          "IP": "hRSPxQhf",
          "Port": 1
        },
        {
          "IP": "ffKEHpDA",
          "Port": 3
        },
        {
          "IP": "AnPwmonG",
          "Port": 9
        },
        {
          "IP": "FAuJExqC",
          "Port": 4
        },
        {
          "IP": "UzRUjIBE",
          "Port": 3
        }
      ],
      "AutoBackup": "EvPVHOmx",
      "BackupTime": 3,
      "ChargeType": "nYSzbBoP",
      "ConfigId": "vEVKUWMd",
      "CreateTime": 4,
      "ExpireTime": 1,
      "HighAvailability": "waGtiDlf",
      "Name": "VRFmczWo",
      "Protocol": "xiIwoTUv",
      "ResourceId": "PGouUYsk",
      "ResourceType": "ffIyEJqL",
      "Size": 2,
      "State": "rBeTVgaa",
      "Tag": "ZHIotklv",
      "Type": "zIiucsOC",
      "UsedSize": 7,
      "Version": "qhGDrkPo"
    },
    {
      "Address": [
        {
          "IP": "ZrVTKWBR",
          "Port": 3
        },
        {
          "IP": "EuuxPaBb",
          "Port": 6
        },
        {
          "IP": "YMEmcZQW",
          "Port": 2
        },
        {
          "IP": "NqYXHFiB",
          "Port": 7
        },
        {
          "IP": "WlRHoRYZ",
          "Port": 6
        },
        {
          "IP": "ojLcBaQA",
          "Port": 8
        },
        {
          "IP": "WahBbpNS",
          "Port": 1
        },
        {
          "IP": "qYimJEhr",
          "Port": 2
        },
        {
          "IP": "QNrwuenH",
          "Port": 9
        }
      ],
      "AutoBackup": "nnRAjmgM",
      "BackupTime": 8,
      "ChargeType": "jGeHUiMK",
      "ConfigId": "iImVJSTb",
      "CreateTime": 9,
      "ExpireTime": 6,
      "HighAvailability": "ralTPpQt",
      "Name": "SifJNKyo",
      "Protocol": "wsUXNQoi",
      "ResourceId": "XUJFsvxu",
      "ResourceType": "PdADkchN",
      "Size": 1,
      "State": "CmfSmehq",
      "Tag": "FMJrjZRv",
      "Type": "uluarTlm",
      "UsedSize": 7,
      "Version": "PSmpRZpd"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





