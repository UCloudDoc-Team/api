# 导入自定义镜像-ImportUEdnCustomImage

导入自定义镜像

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|IdcId.n|string|镜像需要导入机房|**Yes**|
|ImageId|string|镜像Id，不传参表示新导入镜像，传参表示已有镜像分发到指定机房|No|
|ImageName|string|镜像名称，不带镜像ID时必填|No|
|UFileUrl|string|UFile镜像文件下载地址，不带镜像ID时必填|No|
|OsType|string|操作系统平台，linux、windows，不带镜像ID时必填|No|
|Format|string|镜像格式，可选RAW、qcow2， 不带镜像ID时必填|No|
|ImageDesc|string|镜像描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageId|string|镜像Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ImportUEdnCustomImage
&ProjectId=NMKlpokg
&ImageName=buufJkSJ
&UFileUrl=YWwobTcX
&OsType=xWZrLvIH
&Format=SrbnKCbS
&IdcId.n=yejuAhRZ
&ImageDesc=KjFVIejJ
&ImageId=EROnlqHT
```

# Response Example
```
{
    "Action": "ImportUEdnCustomImageResponse", 
    "RetCode": 0, 
    "ImageId": "DffcgmDT"
}
```

