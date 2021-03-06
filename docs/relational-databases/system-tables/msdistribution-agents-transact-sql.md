---
title: MSdistribution_agents (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 10/28/2015
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSdistribution_agents_TSQL
- MSdistribution_agents
dev_langs:
- TSQL
helpviewer_keywords:
- MSdistribution_agents system table
ms.assetid: 0e8f0653-1351-41d1-95d2-40f6d5a050ca
caps.latest.revision: 30
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1cfaf9388efc32949540731d0b311ac4f42c9110
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="msdistributionagents-transact-sql"></a>MSdistribution_agents (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSdistribution_agents**表包含用于显示本地分发服务器上运行每个分发代理的一个行。 此表存储在分发数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|分发代理的 ID。|  
|**名称**|**nvarchar(100)**|分发代理的名称。|  
|**publisher_database_id**|**int**|发布服务器数据库的 ID。|  
|**publisher_id**|**int**|发布服务器的 ID。|  
|**publisher_db**|**sysname**|发布服务器数据库的名称。|  
|**发布**|**sysname**|发布的名称。|  
|**subscriber_id**|**int**|订阅服务器的 ID，仅限已知代理使用。 对于匿名代理程序，此列是保留的。|  
|**subscriber_db**|**sysname**|订阅数据库的名称。|  
|**subscription_type**|**int**|订阅的类型：<br /><br /> **0** = 推送。<br /><br /> **1** = 请求。<br /><br /> **2** = 匿名。|  
|**local_job**|**bit**|指示本地分发服务器上是否存在 SQL Server 代理作业。|  
|**job_id**|**binary(16)**|作业标识号。|  
|**subscription_guid**|**binary(16)**|此代理的订阅 ID。|  
|**profile_id**|**int**|中的配置 ID [MSagent_profiles &#40;TRANSACT-SQL&#41; ](../../relational-databases/system-tables/msagent-profiles-transact-sql.md)表。|  
|**anonymous_subid**|**uniqueidentifier**|匿名代理的 ID。|  
|**subscriber_name**|**sysname**|订阅服务器名称，仅供匿名代理使用。|  
|**virtual_agent_id**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**anonymous_agent_id**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**creation_date**|**datetime**|创建分发或合并代理时的日期时间。|  
|**queue_id**|**sysname**|用于查找已排队的更新订阅操作所在队列的标识符。 对非排队订阅，该值为 NULL。 对于基于 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 消息队列的发布，该值为 GUID，它唯一标识用于订阅的队列。 对于基于 SQL Server 的队列发布，列包含值**SQL**。<br /><br /> 注意： 使用[!INCLUDE[msCoName](../../includes/msconame-md.md)]消息队列已弃用，不再受支持。|  
|**queue_status**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**offload_enabled**|**bit**|指示是否可以远程激活代理。<br /><br /> **0**指定代理不能远程激活。<br /><br /> **1**指定远程，并在指定的远程计算机上，将激活代理*offload_server*属性。|  
|**offload_server**|**sysname**|用于远程代理激活的服务器网络名称。|  
|**dts_package_name**|**sysname**|DTS 包的名称。 例如，对于名为包**DTSPub_Package**，指定`@dts_package_name = N'DTSPub_Package'`。|  
|**dts_package_password**|**nvarchar(524)**|包上的密码。|  
|**dts_package_location**|**int**|包位置。 包的位置可以是**分发服务器**或**订阅服务器**。|  
|**sid**|**varbinary(85)**|分发代理或合并代理第一次执行时的安全标识号 (SID)。|  
|**queue_server**|**sysname**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**subscriber_security_mode**|**int**|代理在连接订阅服务器时所使用的安全模式，可以是下列模式之一：<br /><br /> **0**  =  [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQL Server 身份验证<br /><br /> **1**  =  [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 身份验证。|  
|**subscriber_login**|**sysname**|连接订阅服务器时所使用的登录名。|  
|**subscriber_password**|**nvarchar(524)**|当连接到订阅服务器时使用的密码的加密值。|  
|**reset_partial_snapshot_progress**|**bit**|表示是否将放弃部分已下载的快照，以便可以再次启动整个快照进程。|  
|**job_step_uid**|**uniqueidentifier**|中，代理启动步骤的 SQL Server 代理作业的唯一 ID。|  
|**订阅流**|**tinyint**|设置每个分发代理允许的连接数，以将更改批并行应用于订阅服务器。 支持使用 1 到 64 之间的值。|  
|**memory_optimized**|**bit**|1 表示订阅服务器可用于内存优化表。|  
  
## <a name="see-also"></a>另请参阅  
 [复制表 (Transact-SQL)](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
