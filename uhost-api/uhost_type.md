

# 【参考】云主机机型 

## 主机概念2.0版本

主机概念2.0采用 MachineType + MinimalCpuPlatform的模式进行调用以创建主机，若不传递MinimalCpuPlatform，默认采用Intel/Auto（自动分配）。

## MachineType枚举

| 传递值                              | 机型           | MinimalCpuPlatform                                                             | 配置范围                                                                                        | 可选磁盘（系统盘+数据盘）                                           |
|---|---|---|---|---|
| MachineType = O                  | 快杰型          | Intel/Auto,<br>  Intel/CascadeLake | 4C4G-64C256G                                                                                | SSD云盘 + RSSD云盘 |
| MachineType = N                  | 通用型          | Intel/Auto,<br>  Intel/IvyBridge,<br>  Intel/Haswell,<br> Intel/Broadwell，<br>Intel/Skylake | 1C1G-32C128G                                                                                | 普通本地盘 + 普通本地盘<br>SSD云盘 + 普通云盘/SSD云盘<br>SSD本地盘 + SSD本地盘  |
| MachineType = C                  | 高主频型         | Intel/Auto, <br> Intel/Skylake                                                         | 1C1G-32C128G                                                                                | SSD本地盘 + SSD本地盘<br> SSD云盘 + 普通云盘/SSD云盘                   |
| MachineType = G, GpuType = V100  | GPU型 - V100  | Intel/Auto,<br> Intel/Broadwell                                                        | 4C 8G,16G + 1颗GPU<br> 8C 16G,32G + 1颗/2颗GPU<br> 16C 32G,64G + 2颗/4颗GPU<br>32C 64G,128G + 4颗GPU  | SSD本地盘 + SSD本地盘<br>SSD云盘 + 普通云盘/SSD云盘                    | 
| MachineType = G, GpuType = P40   | GPU型 - P40   | Intel/Auto, <br> Intel/Broadwell                                                       | 4C 8G,16G + 1颗GPU<br> 8C 16G,32G + 1颗/2颗GPU<br> 16C 32G,64G + 2颗/4颗GPU <br> 32C 64G,128G + 4颗GPU  | SSD本地盘 + SSD本地盘 <br>SSD云盘 + 普通云盘/SSD云盘                    | 
| Machinetype = G, GpuType = K80   | GPU型 - K80   | Intel/Auto,<br>  Intel/Haswell                                                         | 4C 8G,16G <br> 8C 16G,32G<br> 16C 32G,64G<br>  *各配置均可配备1-2颗GPU                                  | SSD本地盘 + SSD本地盘                                         | 

具体机型信息请参考 [机型与CPU平台](compute/uhost/introduction/uhost/type_new.md)不同机房的主机类型支持情况不同。详情请参考控制台。

## 主机概念1.0版本

机型概念1.0通过传入UHostType，即可创建指定机型。

## UHostType枚举 

| 传递值  | 机型          | 所属系列           | 配置范围 | 可选磁盘（系统盘+数据盘）    | 
|---|---|---|---|---|
| N3   | 标准型 N3      | 系列3 - Skylake  | 1C1G-32C128G  | 普通本地盘 + 普通本地盘 <br> SSD云盘 + 普通云盘 <br> SSD云盘 + SSD云盘 |
| C1   | 高主频型 C1      | 系列3 - Skylake  | 1C1G-32C128G  | SSD本地盘 + SSD本地盘 <br> SSD云盘 + SSD云盘 |
| N2   | 标准型 N2      | 系列2 - Broadwell  | 1C1G-32C128G  | 普通本地盘 + 普通本地盘 <br> SSD云盘 + 普通云盘 <br> SSD云盘 + SSD云盘 |
| I2   | 高IO型 I2      | 系列2 - Broadwell  | 1C1G-32C128G  | SSD本地盘 + SSD本地盘 <br> SSD云盘 + SSD云盘 |
| G2   | GPU型 - P40  | 系列2 - Broadwell  | 4C 8G,16G + 1颗GPU<br> 8C 16G,32G + 1颗/2颗GPU<br> 16C 32G,64G + 2颗/4颗GPU <br> 32C 64G,128G + 4颗GPU  | SSD本地盘 + SSD本地盘<br> SSD云盘 + SSD云盘 |
| G3   | GPU型 - V100  | 系列2 - Broadwell  | 4C 8G,16G + 1颗GPU<br> 8C 16G,32G + 1颗/2颗GPU<br> 16C 32G,64G + 2颗/4颗GPU <br> 32C 64G,128G + 4颗GPU  | SSD本地盘 + SSD本地盘<br> SSD云盘 + SSD云盘 |
| N1   | 标准型 N1      | 系列1 - Haswell  | 1C1G-16C64G  | 普通本地盘 + 普通本地盘 |
| I1   | 高IO型 I1     | 系列1 - Haswell  | 1C1G-16C64G     | SSD本地盘 + SSD本地盘   |
| G1   | GPU型 - K80  | 系列1 - Haswell  | 4C 8G,16G <br> 8C 16G,32G<br> 16C 32G,64G <br>  *各配置均可配备1-2颗GPU  | SSD本地盘 + SSD本地盘 |

具体机型信息请参考 [机型与规格](compute/uhost/introduction/uhost/type)。不同机房的主机类型支持情况不同。详情请参考控制台。

## UHostType默认值 

北京A、北京C、上海二A、香港A可用区默认N1，其他机房默认N2。
