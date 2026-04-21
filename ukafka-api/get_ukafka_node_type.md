# 获取节点机型配置 - GetUKafkaNodeType

## 简介

获取节点机型配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUKafkaNodeType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUKafkaNodeType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NodeType** | string | 传参时返回指定机型信息，参数为空时返回所有机型信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeTypeSet** | array[[*InstanceType*](#InstanceType)] | 机型信息列表 |**Yes**|

#### 数据模型


#### InstanceType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskSet** | [*DiskSet*](#DiskSet) | 机型磁盘类型信息 |No|
| **CPU** | int | CPU核心数 |No|
| **DiskType** | string | 磁盘类型。RSSD 表示固态云盘，SSD 表示本地固态盘，COMMON 表示本地 SATA 盘 |No|
| **NodeTypeName** | string | 机型名称 |No|
| **Memory** | string | 内存大小（单位 MB） |No|

#### DiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 磁盘类型。Boot 表示系统盘，Data 表示数据盘 |**Yes**|
| **Size** | string | 磁盘大小 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUKafkaNodeType
&Region=cn-zj
&Zone=cn-zj-01
&InstanceGroupType=PUjASMlY
&ProjectId=iKJxgdAc
```

### 响应示例
    
```json
{
  "Action": "GetUKafkaNodeTypeResponse",
  "InstanceTypeSet": [
    {
      "CPU": 2,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 200,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD",
      "InstanceTypeName": "J1-large",
      "IsUseable": "Yes",
      "Memory": 4096,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 4,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 400,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD",
      "InstanceTypeName": "J1-xlarge",
      "IsUseable": "Yes",
      "Memory": 8192,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 8,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 800,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD",
      "InstanceTypeName": "J1-2xlarge",
      "IsUseable": "Yes",
      "Memory": 16384,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 16,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 1500,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD",
      "InstanceTypeName": "J1-3xlarge",
      "IsUseable": "Yes",
      "Memory": 32768,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 16,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 2000,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD",
      "InstanceTypeName": "J1-4xlarge",
      "IsUseable": "Yes",
      "Memory": 65536,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 2,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 500,
          "Type": "Data"
        }
      ],
      "DiskType": "COMMON",
      "InstanceTypeName": "N1-large",
      "IsUseable": "Yes",
      "Memory": 8192,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 4,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 1000,
          "Type": "Data"
        }
      ],
      "DiskType": "COMMON",
      "InstanceTypeName": "N1-xlarge",
      "IsUseable": "Yes",
      "Memory": 16384,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 8,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 2000,
          "Type": "Data"
        }
      ],
      "DiskType": "COMMON",
      "InstanceTypeName": "N1-2xlarge",
      "IsUseable": "Yes",
      "Memory": 32768,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 16,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 2000,
          "Type": "Data"
        }
      ],
      "DiskType": "COMMON",
      "InstanceTypeName": "N1-4xlarge",
      "IsUseable": "Yes",
      "Memory": 65536,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 4,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 800,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD_LARGE_DATA",
      "InstanceTypeName": "Q1-large",
      "IsUseable": "No",
      "Memory": 8192,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 8,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 1600,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD_LARGE_DATA",
      "InstanceTypeName": "Q1-xlarge",
      "IsUseable": "No",
      "Memory": 16384,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    },
    {
      "CPU": 16,
      "DiskSet": [
        {
          "Size": 20,
          "Type": "Boot"
        },
        {
          "Size": 3700,
          "Type": "Data"
        }
      ],
      "DiskType": "SSD_LARGE_DATA",
      "InstanceTypeName": "Q1-2xlarge",
      "IsUseable": "No",
      "Memory": 32768,
      "SuitableRole": [
        "k",
        "a",
        "f",
        "k",
        "a"
      ]
    }
  ],
  "Message": "pXAPKgfv",
  "RetCode": 0,
  "TotalCount": 12
}
```





