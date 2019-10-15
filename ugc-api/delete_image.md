# 删除镜像-DeleteImage

删除用户私有镜像，支持一次删除镜像多个tag，一次最多删除100个。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ImageName|string|私有镜像名，仅可以使用数字，字母，下划线，减号。|**Yes**|
|Tag.n|string|tag名称，例如Tag.0代表希望删除Tag1，Tag.1代表希望删除Tag2。一次最多删除100个，从Tag.0到Tag.99|**Yes**|
|BucketName|string|Bucket名称，仅可使用数字，字母，下划线。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|RetCode对应的描述信息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteImage
&BucketName=helloworld
&ImageName=image1
&PublicKey=6uRRmG67WK8KI9bBUv7Kw==fdsfsdfasdfdsafdsafdsafdsfdsafd
&Region=cn-bj2
&Tag.0=v0.1.20170602.1-test-DeleteImage40
&Tag.1=v0.1.20170602.1-test-DeleteImage41
&Signature=fsfdsfdsfsd602345e30b9f87fbc8c6e39f48d7dafa
```

# Response Example
```
{
    "Action": "DeleteImageResponse", 
    "Message": "成功", 
    "RetCode": 0
}
```

