# pod yaml格式

> 需要将yaml进行base64加密后传入对应api字段。

```yaml
apiVersion: v1
kind: Pod
metadata:
spec:
  containers:
  - args:  # 非必填
    - '-R'
    command: # 非必填
    - php-fpm  
    env:  # 非必填
    - name: aaa
      value: '111'
    - name: bbb
      value: '222'
    image: 'uhub.service.ucloud.cn/xxx/xxx:xxx'  # 必填，镜像地址，已支持自建镜像仓库
    name: cube01  # 必填，名字，规则（^[a-zA-Z0-9-_]{1,32}）
    resources:
      limits:
        cpu: "1"  # 必填
        memory: 1Gi  # 必填
    volumeMounts:  #非必填，使用存储时必填
    - mountPath: /data  #mount路径
      name: ufs  #vloumes名字
    - mountPath: /data2
      name: udisk
    - mountPath: /etc/nginx/conf.d/default.conf
      name: defaultconf
      subPath: default.conf
  hostAliases:
  - hostnames:
    - www.abc.com
    ip: 1.1.1.1
  - hostnames:
    - www.def.com
    ip: 2.2.2.2
  initContainers: # 非必填 需要初始化环境是增加初始化容器
  - args: # 非必填
    - '-c'
    - >-
      wget xxx.tar && tar -zxvf xxx.tar
    command: # 非必填
    - sh
    env:  # 非必填 
    - name: aaa
      value: '111'
    - name: bbb
      value: '222'
    image: 'uhub.service.ucloud.cn/xxx/xxx:xxx' # 必填，镜像地址，已支持自建镜像仓库
    name: initcube01  # 必填，名字，规则（^[a-zA-Z0-9-_]{1,32}）
    volumeMounts:  # 非必填，使用存储时必填
    - mountPath: /data  # mount路径
      name: ufs  # vloumes名字
    - mountPath: /data2
      name: udisk
    - mountPath: /etc/nginx/conf.d/default.conf
      name: defaultconf
      subPath: default.conf
    - mountPath: /data3
      name: emptydir
      subPath: emptydir 
  volumes:  # 非必填，使用存储时必填
  - nfs:
      address: '10.19.71.52:/' #必填，ufs或其他nfs存储地址及挂载点
      mountOption: vers=4.0  #必填，存储协议，默认vers=4.0
    name: ufs  # 必填，vloumes名字
  - udisk:
      forceFormat: false  # 是否格式化挂载，true为格式化挂载，默认为false
      fs: ext4
      id: bsr-2zpjue50  # UDisk ID,现仅支持RSSD
    name: udisk  # 必填，vloumes名字
  - name: defaultconf  # 必填，vloumes名字
    secret:  # 必填，config
      default.conf: >-
        c2VydmVyIHsKICAgIGxpc3RlbiAgICAgICA4MDsKICAgIHNlcnZlcl9uYW1lICBsb2NhbGhvc3Q7CgogICAgbG9jYXRpb24gLyB7CiAgICAgICAgcm9vdCAgIC91c3Ivc2hhcmUvbmdpbngvaHRtbC93b3JkcHJlc3M7CiAgICAgICAgaW5kZXggIGluZGV4Lmh0bWwgaW5kZXgucGhwOwogICAgfQogICAgZXJyb3JfcGFnZSAgIDUwMCA1MDIgNTAzIDUwNCAgLzUweC5odG1sOwogICAgbG9jYXRpb24gPSAvNTB4Lmh0bWwgewogICAgICAgIHJvb3QgICAvdXNyL3NoYXJlL25naW54L2h0bWw7CiAgICB9CiAgICBsb2NhdGlvbiB+IFwucGhwJCB7CiAgICAgICAgZmFzdGNnaV9wYXNzIGxvY2FsaG9zdDo5MDAwOwogICAgICAgIGZhc3RjZ2lfaW5kZXggaW5kZXgucGhwOwogICAgICAgIGZhc3RjZ2lfYnVmZmVycyAxNiAxNms7CiAgICAgICAgZmFzdGNnaV9idWZmZXJfc2l6ZSAzMms7CiAgICAgICAgZmFzdGNnaV9wYXJhbSBTQ1JJUFRfRklMRU5BTUUgL3Zhci93d3cvaHRtbC93b3JkcHJlc3MvJGZhc3RjZ2lfc2NyaXB0X25hbWU7CiAgICAgICAgI2ZpeGVzIHRpbWVvdXRzCiAgICAgICAgZmFzdGNnaV9yZWFkX3RpbWVvdXQgNjAwOwogICAgICAgIGluY2x1ZGUgZmFzdGNnaV9wYXJhbXM7CiAgICB9Cn0=
  - emptyDir: {}
    name: emptydir  # 必填，vloumes名字
  imagePullSecrets: #镜像参数，非必填，仓库设置拉取密码时必须填写
  - registryServer: "uhub.service.ucloud.cn" # 镜像仓库域名
    username: "username"  # 镜像仓库用户名 
    password: "password"  # 镜像仓库密码
    registryaddr: "10.x.x.x"  # 镜像仓库内网地址，适用于自建镜像仓库
    vpcId: "uvnet-xxxxxxxx"  # 镜像仓库所在 VPC ID，适用于自建镜像仓库
  restartPolicy: Always  #非必填
```
