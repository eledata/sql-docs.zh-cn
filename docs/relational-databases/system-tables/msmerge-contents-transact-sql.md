---
title: MSmerge_contents (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/04/2017
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
- MSmerge_contents
- MSmerge_contents_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_contents system table
ms.assetid: 8d68a61a-683f-4b20-92f9-c0a8d9ba0ad1
caps.latest.revision: 19
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 48c2320fa26b86f9ee221a65e3a81eb809021cf4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="msmergecontents-transact-sql"></a>MSmerge_contents (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSmerge_contents**表包含个修改当前数据库中，因为它已发布的每一行都占一行。 合并过程使用此表来确定已更改的行。 此表存储在发布和订阅数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**tablenick**|**int**|已发布表的别名。|  
|**rowguid**|**uniqueidentifier**|给定行的行标识符。|  
|**生成**|**bigint**|由标识的行生成**tablenick**和**rowguid**。|  
|**partchangegen**|**bigint**|与上次数据更改相关联的代（不论行是否属于已筛选发布，这些更改都可能已经发生）。|  
|**沿袭**|**Varbinary(501)**|用于维护此行的更改历史记录的订阅服务器的别名和版本号对。|  
|**colvl**|**varbinary(7489)**|列版本信息。|  
|**标记**|**uniqueidentifier**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**logical_record_parent_rowguid**|**uniqueidentifier**|标识中的顶级父行**MSmerge_contents** (通过**rowguid**) 的逻辑记录中每个相应的子行。|  
|**logical_record_lineage**|**Varbinary(501)**|用于维护逻辑记录中的顶级父行的更改的历史记录的订阅服务器的别名、版本号对。 对于逻辑记录中的所有子行，此值为 NULL。|  
|**logical_relation_change_gen**|**bigint**|与导致逻辑记录重新调整的上次更改相关联的代（即将现有行移入或移出逻辑记录）。|  
  
## <a name="see-also"></a>另请参阅  
 [复制表&#40;Transact SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图 (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
