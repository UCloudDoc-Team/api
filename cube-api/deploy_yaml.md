# Deployment yaml 格式

> 需要将yaml进行base64加密后传入对应api字段。

```yaml
apiVersion: v1
kind: Deployment
spec:
  replicas: N # Pod 副本数，支持最大 50 个
  resourceClassInfo:
    firewall: # 防火墙信息，可不填写
      - name: resource-fw # 对应下文 network 中 firewall 的 resourceName 字段
        resoureId: firewall-xxxxxxxx # 需要绑定的防火墙策略
    eip:  # EIP 信息，可不填写
      - name: resouce-eip # 对应下文 network 中 eip 的 resourceName 字段
        template:
          reclaimPolicy: Retain # EIP 回收策略，Retain 为删除 Cube 时保留，Delete 为删除时直接释放
          name: eip-123 # EIP 资源名，显示在 EIP 资源列表中
          bandwidth: 1 # 带宽，单位为 MB
          chargeType: Month # 付费模式，支持 Year（年付），Month（月付）, Dynamic（时付）
          quantity: 1 # 购买时长，默认为 1，chargeType 为 Dynamic 时无需填写
          payMode: Bandwidth # 计费模式，支持 Traffic（流量计费）、Bandwidth（带宽计费）、ShareBandwidth（共享带宽）
          tag: xxii # EIP 业务组
        preDeclared:   # 绑定已有 EIP，优先使用已有EIP
          - resoureId: eip-xxxxxxxx
          - resoureId: eip-xxxxxxxx
    udisk: # UDisk 信息，可不填写
      - name: resouce-udisk # 对应下文 volumes 中 udisk 的 resourceName 字段
        template: 
          size: 20 # 磁盘容量，单位为 GB
          reclaimPolicy: Retain # UDisk 回收策略，Retain 为删除 Cube 时保留，Delete 为删除时直接删除
          name: udisk-123 # UDisk 资源名，显示在 UDisk 资源列表中
          chargeType: Month # 付费模式，支持 Year（年付），Month（月付）, Dynamic（时付）
          quantity: 1 # 购买时长，默认为 1，chargeType 为 Dynamic 时无需填写
          snapshotService: No # 是否需要快照功能，Yes 为开启，No 为不开启
          diskType: SSDDataDisk  # 磁盘类型，支持 DataDisk（普通数据盘），SSDDataDisk（SSD数据盘），RSSDDataDisk（RSSD数据盘）
          ukmsMode: No # 是否加密，Yes 为需要，No 为不需要，默认 No
          cmkId: # 加密需要的cmk id，UKmsMode为Yes时，必填
          accessModes: ReadWriteOnce/ReadWriteMany  # 单独写就根据pod实例创建，多读写就只创建一个
        preDeclared:  # 使用已有 UDisk，优先使用已有 UDisk
          - resoureId: udisk-xxxxxxxx
          - resoureId: udisk-xxxxxxxx
  cubePodSpec:
    containers:
      - args: ["1000000"] # 参数
        command: ["whatever_command"] # 启动命令
        env: # 环境变量
        - name: "ENV_NAME"
          value: "ENV_VALUE"
        image: uhub.service.ucloud.cn/library/busybox:latest
        name: test-container
        resources:
          limits:
            memory: 1024Mi
            cpu: 1000m
        workingDir: "/etc" # 工作目录
        volumeMounts: # 挂载卷
        - name: configmap-volume
          mountPath: /whatever/path/configmap-volume
        - name: encodemap-volume
          mountPath: /whatever/path/encodemap-volume
        - name: emptydir-volume
          mountPath: /whatever/path/emptydir-volume
        - name: udisk-volume
          mountPath: /whatever/path/udisk-volume
        - name: nfs-volume
          mountPath: /whatever/path/nfs-volume
    dnsConfig: # DNS 配置
      nameservers: # 自定义 DNS
        - 1.2.3.4
    hostAliases:
      - ip: "127.0.0.1"
        hostnames:
        - "foo.local"
        - "bar.local"
      - ip: "10.1.2.3"
        hostnames:
        - "foo.remote"
        - "bar.remote"
    hostname: "aaa-bbb-ccc" # Cube 主机名称
    imagePullSecrets: # 镜像参数，非必填，仓库设置拉取密码时必须填写
    - registryServer: "uhub.service.ucloud.cn" # 镜像仓库域名
      username: "username"  # 镜像仓库用户名 
      password: "password"  # 镜像仓库密码
      registryaddr: "10.x.x.x"  # 镜像仓库内网地址，适用于自建镜像仓库
      vpcId: "uvnet-xxxxxxxx"  # 镜像仓库所在 VPC ID，适用于自建镜像仓库
    restartPolicy: Never # 容器重启策略，支持 Always, OnFailure, 及 Never
    volumes: # 卷设置
      - name: configmap-volume
        configMap:
          aaa: "whatever aaa utf8 byte"
          bbb: "whatever bbb utf8 byte"
      - name: encodemap-volume
        secret:
          ccc: "whatever ccc base64 encoded"
          ddd: "whatever ddd base64 encoded"
      - name: emptydir-volume
        emptyDir: {}
      - name: udisk-volume
        udisk:
          resourceName: resouce-udisk
          fs: ext4
          forceFormat: true
    network:
      firewall:
        resourceName: resource-fw
      eip:
        resourceName: resouce-eip
```
