#导入镜像-ImportCustomImage

把UFile的镜像文件导入到UHost，生成自定义镜像。

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ImageName|string|镜像名称|**Yes**|
|UFileUrl|string|UFile私有空间地址|**Yes**|
|OsType|string|操作系统平台，比如CentOS、Ubuntu、Windows、RedHat等，请参考控制台的镜像版本；若导入控制台上没有的操作系统，参数为Other|**Yes**|
|OsName|string|操作系统详细版本，请参考控制台的镜像版本；OsType为Other时，输入参数为Other|**Yes**|
|Format|string|镜像格式，可选RAW、VHD、VMDK、qcow2|**Yes**|
|Auth|bool|是否授权。必须填true|**Yes**|
|ImageDescription|string|镜像描述|No|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageId|string|镜像Id|No|

#Request Example
```
https://api.ucloud.cn/?Action=ImportCustomImage
&Region=cn-bj2
&ProjectId=asdf
&ImageName=mbfThSeV
&UFileUrl=https://***.cn-bj.ufileos.com/***
&OsType=CentOS
&OsName=CentOS 6.5 32位
&Format=VMDK
&Auth=1
```
#Response Example
```
{
    "Action": "ImportCustomImageResponse",
    "RetCode": 0,
    "ImageId": "uimage-xxxxx"
}
```

{{indexmenu_n>1000}}