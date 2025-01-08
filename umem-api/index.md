# API 索引

## Memcached

| API | 描述信息 |
|:---|:---|
|[RestartUMemcacheGroup](api/umem-api/restart_umem_cache_group)|重启单机Memcache|
|[DescribeUMemcacheGroup](api/umem-api/describe_umem_cache_group)|显示Memcache|
|[DescribeUMemcacheUpgradePrice](api/umem-api/describe_umem_cache_upgrade_price)|获取umemcache升级价格|
|[DescribeUMemcachePrice](api/umem-api/describe_umem_cache_price)|获取umemcache组价格|
|[CreateUMemcacheGroup](api/umem-api/create_umem_cache_group)|创建单机Memcache|
|[GetUMemSpaceState](api/umem-api/get_umem_space_state)|获取空间状态|
|[DeleteUMemcacheGroup](api/umem-api/delete_umem_cache_group)|删除单机Memcache|

## Redis

| API | 描述信息 |
|:---|:---|
|[CreateURedisGroup](api/umem-api/create_uredis_group)|创建主备redis|
|[DescribeURedisSlowlog](api/umem-api/describe_uredis_slowlog)|查询URedis慢日志|
|[ResizeURedisGroup](api/umem-api/resize_uredis_group)|调整容量|
|[DescribeURedisPrice](api/umem-api/describe_uredis_price)|获取URedis价格信息|
|[ModifyUMemSpaceName](api/umem-api/modify_umem_space_name)|修改名称|
|[DescribeURedisBackupURL](api/umem-api/describe_uredis_backup_url)|获取主备Redis备份下载链接|
|[DescribeURedisUpgradePrice](api/umem-api/describe_uredis_upgrade_price)|获取uredis升级价格信息|
|[DescribeURedisConfig](api/umem-api/describe_uredis_config)|查询主备Redis所有配置文件|
|[ResizeUMemSpace](api/umem-api/resize_umem_space)|调整容量|
|[DescribeUMemPrice](api/umem-api/describe_umem_price)|获取价格|
|[DescribeUMemUpgradePrice](api/umem-api/describe_umem_upgrade_price)|获取升级价格|
|[DeleteUMemSpace](api/umem-api/delete_umem_space)|删除空间|
|[DescribeURedisBackup](api/umem-api/describe_uredis_backup)|查询主备redis备份|
|[DescribeUMemSpace](api/umem-api/describe_umem_space)|查询空间|
|[DescribeURedisGroup](api/umem-api/describe_uredis_group)|查询主备Redis|
|[ModifyURedisGroupName](api/umem-api/modify_uredis_group_name)|修改名称|
|[DeleteURedisGroup](api/umem-api/delete_uredis_group)|删除主备redis|
|[CreateUMemSpace](api/umem-api/create_umem_space)|创建内存空间|
|[ModifyURedisGroupPassword](api/umem-api/modify_uredis_group_password)|修改主备密码|
|[CreateUMemBackup](api/umem-api/create_umem_backup)|创建分布式redis备份|
|[DescribeUMemBackup](api/umem-api/describe_umem_backup)|查询分布式redis备份|
|[DescribeUMemBackupURL](api/umem-api/describe_umem_backup_url)|获取分布式redis 备份下载链接|
|[CheckUDredisSpaceAllowance](api/umem-api/check_udredis_space_allowance)|检查高性能UMem剩余资源|
|[CheckURedisAllowance](api/umem-api/check_uredis_allowance)|检查URedis资源是否足够|
|[CreateScanHotBigKeys](api/umem-api/create_scan_hot_big_keys)|创建扫大key和热key的任务|
|[CreateURedisBackup](api/umem-api/create_uredis_backup)|创建主备Redis备份|
|[DescribeUDRedisProxyInfo](api/umem-api/describe_ud_redis_proxy_info)|拉取udredis代理信息|
|[DescribeUDRedisSlowlog](api/umem-api/describe_ud_redis_slowlog)|查询UDRedis慢日志|
|[DescribeUMem](api/umem-api/describe_umem)|获取UMem列表|
|[DescribeUMemBlockInfo](api/umem-api/describe_umem_block_info)|拉取UDRedis分片信息|
|[DescribeURedisVersion](api/umem-api/describe_uredis_version)|获取主Redis可用版本|
|[FlushallURedisGroup](api/umem-api/flushall_uredis_group)|清除主备redis数据|
|[ISolationURedisGroup](api/umem-api/i_solation_uredis_group)|打开/关闭URedis|
|[ModifyURedisConfig](api/umem-api/modify_uredis_config)|修改主备Redis配置文件参数|
|[RegisterUMemDefrag](api/umem-api/register_umem_defrag)|动态开关redis碎片整理选项|
|[RemoveUDRedisData](api/umem-api/remove_ud_redis_data)|清除udredis实例数据|
|[RestartURedisGroup](api/umem-api/restart_uredis_group)|重启主备实例|
|[UpdateURedisBackupStrategy](api/umem-api/update_uredis_backup_strategy)|更改主备Redis备份策略|
|[UpdateURedisRewriteTime](api/umem-api/update_uredis_rewrite_time)|修改主备redis重写时间|
|[ResizeUDRedisBlockSize](api/umem-api/resize_ud_redis_block_size)|更改udredis分片容量|
