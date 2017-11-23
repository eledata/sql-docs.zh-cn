---
title: "IHpublisherindexes (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- IHpublisherindexes
- IHpublisherindexes_TSQL
dev_langs: TSQL
helpviewer_keywords: IHpublisherindexes system table
ms.assetid: 6008ef89-eeb9-46dc-93a2-f7623298cf0f
caps.latest.revision: "12"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4e8bf3c3e201c817fa76138df488eec70afb1173
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihpublisherindexes-transact-sql"></a>IHpublisherindexes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **IHpublisherindexes**系统表包含每个索引复制从非 SQL Server 发布服务器使用当前分发服务器的一行。 此表存储在分发数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**publisherindex_id**|**int**|标识已发布的索引。|  
|**针对 table_id 所**|**int**|标识从表[IHpublishertables](../../relational-databases/system-tables/ihpublishertables-transact-sql.md)索引所属。|  
|**publisher_id**|**int**|标识非 SQL Server 发布服务器从其发布索引。|  
|**名称**|**sysname**|已发布的索引的名称。|  
|**type**|**nvarchar(255)**|支持的索引类型从[IHindextypes](../../relational-databases/system-tables/ihindextypes-transact-sql.md)系统表。|  
  
## <a name="see-also"></a>另请参阅  
 [异类数据库复制](../../relational-databases/replication/non-sql/heterogeneous-database-replication.md)   
 [复制表 &#40;Transact SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图 (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  