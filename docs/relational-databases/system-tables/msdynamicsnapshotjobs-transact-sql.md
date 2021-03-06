---
title: MSdynamicsnapshotjobs (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/06/2017
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
- MSdynamicsnapshotjobs_TSQL
- MSdynamicsnapshotjobs
dev_langs:
- TSQL
helpviewer_keywords:
- MSdynamicsnapshotjobs system table
ms.assetid: 4f36a325-0e3c-46c4-aeeb-416346cce0bc
caps.latest.revision: 26
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b32385c63ca8cc4906aee876ac76edd776350b53
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="msdynamicsnapshotjobs-transact-sql"></a>MSdynamicsnapshotjobs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSdynamicsnapshotjobs**表跟踪应用以生成已筛选的数据的快照的参数化的行筛选器信息。 此表存储在发布和订阅数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|筛选数据快照作业的 ID。|  
|**名称**|**sysname**|已筛选的数据快照作业的名称。|  
|**pubid**|**uniqueidentifier**|此发布的唯一标识号。|  
|**job_id**|**uniqueidentifier**|分发服务器上的 SQL Server 代理作业的 ID。|  
|**agent_id**|**int**|SQL Server 代理的 ID。|  
|**dynamic_filter_login**|**sysname**|用于评估的值[SUSER_SNAME](../../t-sql/functions/suser-sname-transact-sql.md)中为发布定义的参数化的行筛选器函数。|  
|**dynamic_filter_hostname**|**sysname**|用于评估的值[HOST_NAME](../../t-sql/functions/host-name-transact-sql.md)中为发布定义的参数化的行筛选器函数。|  
|**dynamic_snapshot_location**|**nvarchar(255)**|如果使用筛选数据快照则从中读取快照文件的文件夹的路径。|  
|**partition_id**|**int**|作业所属数据分区的 ID。|  
  
## <a name="see-also"></a>另请参阅  
 [复制表 (Transact-SQL)](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
