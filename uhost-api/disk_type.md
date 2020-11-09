

# 【参考】磁盘类型 

### 枚举值说明 

| 枚举值 | 磁盘类型 | 可选范围（系统盘） | 可选范围（数据盘） | 数据方舟支持情况 |
|---|---|---|---|---|
| LOCAL\_NORMAL| 普通本地盘| 创建时/重装时：仅支持当前镜像大小 <br> 改配时 [1]：当前镜像大小-100G  | 20G - 2000G，默认20G | 支持，系统盘与数据盘必须同时开启 |
| LOCAL\_SSD| SSD本地盘 | 创建时/重装时：仅支持当前镜像大小 <br> 改配时 [1]：当前镜像大小-100G | 20G - 1000G，默认20G | 不支持 |
| CLOUD\_NORMAL| 普通云盘 | （不支持） | 20G - 8000G，默认20G | 仅支持数据盘 |
| CLOUD\_SSD| SSD云盘 | 20-500G <br> 支持创建/重装/改配 [2] | 20G - 4000G，默认20G | 不支持 |
| CLOUD\_RSSD| RSSD云盘 | 20-500G <br> 支持创建/重装/改配 [2] | 20G - 32000G，默认20G | 不支持 |
| EXCLUSIVE\_LOCAL\_DISK|  （不支持） |  独享本地盘 | 4096G / 3072G | 不支持 |

[1] 本地盘不支持在创建/重装主机时传入>镜像大小的系统盘Size。但扩容完成后，无需进入系统操作。

[2] 云盘支持在创建/重装主机时传入>镜像大小的系统盘Size。扩容完成后，需要进入系统进行对文件系统的扩容，操作步骤请参照[文档](https://docs.ucloud.cn/uhost/guide/disk#云硬盘)。

### 机型与磁盘关系（V2.0概念-MachineType）

| MachineType枚举值  | 机型           | 可选磁盘（系统盘+数据盘）                           |
|---|---|---|
| OS   | 快杰S型 OS   | RSSD云盘 + RSSD本地盘  |
| OPRO   | 快杰PRO型 OPRO   | RSSD云盘 + RSSD本地盘  |
| OMAX   | 快杰Max型 OMAX   | RSSD云盘 + RSSD本地盘  |
| N   | 通用型 N       | 普通本地盘 + 普通本地盘 <br> SSD云盘 + 普通云盘 <br> SSD云盘 + SSD云盘 <br> SSD本地盘 + SSD本地盘  |
| C   | 高主频型 C      | SSD本地盘 + SSD本地盘 <br> SSD云盘 + SSD云盘                |
| G   | GPU型 G  | SSD本地盘 + SSD本地盘  <br> SSD云盘 + SSD云盘   |
| O   | 快杰型 O   | RSSD云盘 + RSSD本地盘  |

### 机型与磁盘关系（V1.0概念-UHostType） 

| MachineType枚举值  | 机型           | 可选磁盘（系统盘+数据盘）                      |
|---|---|--|
| N3   | 标准型 N3       | 普通本地盘 + 普通本地盘 <br> SSD云盘 + 普通云盘 <br> SSD云盘 + SSD云盘  |
| C1   | 高主频型 C1      | SSD本地盘 + SSD本地盘 <br> SSD云盘 + SSD云盘                |
| N2   | 标准型 N2       | 普通本地盘 + 普通本地盘 <br> SSD云盘 + 普通云盘 <br> SSD云盘 + SSD云盘  |
| I2   | 高IO型 I2      | SSD本地盘 + SSD本地盘 <br>SSD云盘 + SSD云盘                |
| G2   | GPU型 - P40   | SSD本地盘 + SSD本地盘<br> SSD云盘 + SSD云盘                 |
| G3   | GPU型 - V100  | SSD本地盘 + SSD本地盘<br> SSD云盘 + SSD云盘                 |
| N1   | 标准型 N1       | 普通本地盘 + 普通本地盘                                   |
| I1   | 高IO型 I1      | SSD本地盘 + SSD本地盘                                 |
| D1   | 大数据型 D1      | 普通本地盘 + 独享本地盘                                   |
| G1   | GPU型 - K80   | SSD本地盘 + SSD本地盘                                 |
