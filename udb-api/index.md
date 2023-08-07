# API 索引

## MySQL

| API | 描述信息 |
|:---|:---|
|[DescribeUDBLogBackupURL](api/udb-api/describe_udb_log_backup_url)|获取UDB的日志备份地址|
|[SwitchUDBInstanceToHA](api/udb-api/switch_udb_instance_to_ha)|普通UDB切换为高可用|
|[CheckUDBInstanceToHAAllowance](api/udb-api/check_udb_instance_to_ha_allowance)|核查db是否可以升级为高可用|
|[PromoteUDBSlave](api/udb-api/promote_udb_slave)|提升从库|
|[DescribeUDBBinlogBackupURL](api/udb-api/describe_udb_binlog_backup_url)|(新)获取UDB的日志备份地址|
|[DescribeUDBInstanceBinlog](api/udb-api/describe_udb_instance_binlog)|获取UDBbinlog列表|
|[DescribeUDBBackupBlacklist](api/udb-api/describe_udb_backup_blacklist)|获取备份黑名单|
|[FetchUDBInstanceEarliestRecoverTime](api/udb-api/fetch_udb_instance_earliest_recover_time)|获取最早可回档时间|
|[CheckRecoverUDBInstance](api/udb-api/check_recover_udb_instance)|核查db是否可以使用回档功能|
|[EditUDBBackupBlacklist](api/udb-api/edit_udb_backup_blacklist)|编辑备份黑名单|
|[SwitchUDBHAToSentinel](api/udb-api/switch_udb_ha_to_sentinel)|UDB高可用实例升级为Sentinel版本（不带HAProxy）升级耗时5-10秒|
|[BackupUDBInstanceSlowLog](api/udb-api/backup_udb_instance_slow_log)|备份UDB指定时间段的slowlog分析结果|
|[BackupUDBInstanceBinlog](api/udb-api/backup_udb_instance_binlog)|备份UDB指定时间段的binlog列表|
|[CreateUDBInstanceByRecovery](api/udb-api/create_udb_instance_by_recovery)|将新建的db恢复到指定db某个指定时间点|
|[UpdateUDBInstanceSlaveBackupSwitch](api/udb-api/update_udb_instance_slave_backup_switch)|开启或者关闭UDB从库备份|
|[PromoteUDBInstanceToHA](api/udb-api/promote_udb_instance_to_ha)|普通db升级为高可用|
|[CreateUDBSlave](api/udb-api/create_udb_slave)|创建从库|
|[EnableUDBRWSplitting](api/udb-api/enable_udb_rw_splitting)|启用读写分离功能|
|[DisableUDBRWSplitting](api/udb-api/disable_udb_rw_splitting)|关闭读写分离功能|
|[RestartRWSplitting](api/udb-api/restart_rw_splitting)|读写分离中间件重启|
|[SetUDBRWSplitting](api/udb-api/set_udb_rw_splitting)|设置读写分离|

## MongoDB

| API | 描述信息 |
|:---|:---|
|[CreateUDBRouteInstance](api/udb-api/create_udb_route_instance)|创建mongos实例|
|[CreateMongoDBReplicaSet](api/udb-api/create_mongo_db_replica_set)|创建DB副本集|
|[CreateUDBReplicationInstance](api/udb-api/create_udb_replication_instance)|创建副本|

## 公共 API

| API | 描述信息 |
|:---|:---|
|[DescribeUDBInstance](api/udb-api/describe_udb_instance)|获取云数据库信息|
|[DescribeUDBInstancePrice](api/udb-api/describe_udb_instance_price)|获取云数据库价格|
|[ClearUDBLog](api/udb-api/clear_udb_log)|清除日志|
|[RestartUDBInstance](api/udb-api/restart_udb_instance)|重启云数据库|
|[ResizeUDBInstance](api/udb-api/resize_udb_instance)|修改UDB实例的配置|
|[ChangeUDBParamGroup](api/udb-api/change_udb_param_group)|修改配置文件|
|[DescribeUDBInstanceLog](api/udb-api/describe_udb_instance_log)|获取UDB错误日志或慢查询日志|
|[DescribeUDBLogPackage](api/udb-api/describe_udb_log_package)|列表UDB实例日志备份信息|
|[DescribeUDBInstanceState](api/udb-api/describe_udb_instance_state)|获取云数据库状态|
|[DescribeUDBInstanceBackupState](api/udb-api/describe_udb_instance_backup_state)|获取实例备份状态|
|[ModifyUDBInstanceName](api/udb-api/modify_udb_instance_name)|修改云数据库名称|
|[StartUDBInstance](api/udb-api/start_udb_instance)|启动云数据库|
|[ModifyUDBInstancePassword](api/udb-api/modify_udb_instance_password)|修改DB实例的管理员密码|
|[ExtractUDBParamGroup](api/udb-api/extract_udb_param_group)|获取配置文件内容|
|[DescribeUDBType](api/udb-api/describe_udb_type)|获取云数据库支持类型|
|[StopUDBInstance](api/udb-api/stop_udb_instance)|关闭云数据库|
|[DeleteUDBInstance](api/udb-api/delete_udb_instance)|删除云数据库|
|[BackupUDBInstance](api/udb-api/backup_udb_instance)|备份云数据库|
|[DescribeUDBInstanceBinlogBackupState](api/udb-api/describe_udb_instance_binlog_backup_state)|获取udb实例备份状态|
|[DeleteUDBParamGroup](api/udb-api/delete_udb_param_group)|删除配置|
|[DescribeUDBInstanceBackupURL](api/udb-api/describe_udb_instance_backup_url)|获取UDB备份下载地址|
|[CreateUDBInstance](api/udb-api/create_udb_instance)|创建数据库|
|[UpdateUDBInstanceBackupStrategy](api/udb-api/update_udb_instance_backup_strategy)|修改UDB自动备份策略|
|[BackupUDBInstanceErrorLog](api/udb-api/backup_udb_instance_error_log)|备份UDB指定时间段的errorlog|
|[UploadUDBParamGroup](api/udb-api/upload_udb_param_group)|导入配置|
|[DeleteUDBLogPackage](api/udb-api/delete_udb_log_package)|删除UDB日志包|
|[CreateUDBParamGroup](api/udb-api/create_udb_param_group)|创建配置文件|
|[DescribeUDBParamGroup](api/udb-api/describe_udb_param_group)|获取参数信息|
|[DescribeUDBBackup](api/udb-api/describe_udb_backup)|获取备份列表|
|[UpdateUDBParamGroup](api/udb-api/update_udb_param_group)|更新配置|
|[DescribeUDBInstanceUpgradePrice](api/udb-api/describe_udb_instance_upgrade_price)|获取UDB实例升降级价格信息|

## API

| API | 描述信息 |
|:---|:---|
|[DescribeUDBSplittingInfo](api/udb-api/describe_udb_splitting_info)|描述读写分离功能|
|[GetUDBClientConnNum](api/udb-api/get_udb_client_conn_num)|获取连接实例客户端Ip和连接数|
|[ModifyUDBInstanceRemarkName](api/udb-api/modify_udb_instance_remark_name)|修改云数据库备注|
|[UpgradeUDBInstanceToHA](api/udb-api/upgrade_udb_instance_to_ha)|快杰普通db升级为高可用|
