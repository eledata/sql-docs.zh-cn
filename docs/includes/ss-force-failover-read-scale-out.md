---
title: "SQL Server 强制可用性组故障转移"
description: "对于群集类型为 NONE 的可用性组强制故障转移"
services: 
author: MikeRayMSFT
ms.service: 
ms.topic: include
ms.date: 02/05/2018
ms.author: mikeray
ms.custom: include file
ms.openlocfilehash: 10a2af2cb5bc9e98605a3ee988439e3c3be60c1e
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
每个可用性组具有一个主副本。 主要副本允许读取和写入操作。 若要更改哪个副本是主，可以故障转移。 在高可用性 AG，群集管理器自动执行故障转移过程。 在与群集类型 NONE AG，故障转移过程为手动。 

有两种方法群集类型 NONE 一起故障转移可用性组中的主副本：

- 强制手动故障转移（会丢失数据）
- 手动故障转移（无数据丢失）

### <a name="forced-manual-failover-with-data-loss"></a>强制手动故障转移（会丢失数据）

当主副本不可用并且无法恢复，请使用此方法。 

若要强制故障转移数据丢失，连接到承载目标辅助副本和运行的 SQL Server 实例：

```SQL
ALTER AVAILABILITY GROUP [ag1] FORCE_FAILOVER_ALLOW_DATA_LOSS;
```

### <a name="manual-failover-without-data-loss"></a>手动故障转移（无数据丢失）

主要副本可用时使用此方法，但需要暂时或永久更改配置，并更改托管主要副本的 SQL Server 实例。 发出手动故障转移之前，请确保目标辅助副本是最新，以避免潜在的数据丢失。 

若要手动故障转移而不丢失数据：

1. 使目标辅助副本成为`SYNCHRONOUS_COMMIT`。

   ```SQL
   ALTER AVAILABILITY GROUP [ag1] 
        MODIFY REPLICA ON N'<node2>' 
        WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);
   ```

2. 运行以下查询以确定活动的事务是提交到主副本和至少一个同步的辅助副本： 

   ```SQL
   SELECT ag.name, 
      drs.database_id, 
      drs.group_id, 
      drs.replica_id, 
      drs.synchronization_state_desc, 
      ag.sequence_number
   FROM sys.dm_hadr_database_replica_states drs, sys.availability_groups ag
   WHERE drs.group_id = ag.group_id; 
   ```

   当 `synchronization_state_desc` 为 `SYNCHRONIZED` 时，会同步次要副本。

3. 更新`REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT`为 1。

   以下脚本集`REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT`上名为可用性组的 1 到`ag1`。 运行以下脚本之前，将`ag1`替换为你的可用性组的名称：

   ```SQL
   ALTER AVAILABILITY GROUP [ag1] 
        SET REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT = 1;
   ```

   此设置可以确保每个活动的事务是提交到主副本和至少一个同步的辅助副本。 

4. 降级到辅助副本的主副本。 降级的主副本后，它是只读的。 在承载主副本来更新到角色的 SQL Server 实例上运行此命令`SECONDARY`:

   ```SQL
   ALTER AVAILABILITY GROUP [ag1] 
        SET (ROLE = SECONDARY); 
   ```

5. 将目标次要副本升级为主要副本。 

   ```SQL
   ALTER AVAILABILITY GROUP ag1 FORCE_FAILOVER_ALLOW_DATA_LOSS; 
   ```  

   > [!NOTE] 
   > 若要删除可用性组，使用[DROP AVAILABILITY GROUP](https://docs.microsoft.com/en-us/sql/t-sql/statements/drop-availability-group-transact-sql)。 有关使用群集创建可用性组键入一个或外部，该命令必须在属于可用性组的所有副本上执行。