---
title: sys.database_recovery_status (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 08/12/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- database_recovery_status_TSQL
- database_recovery_status
- sys.database_recovery_status
- sys.database_recovery_status_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.database_recovery_status catalog view
ms.assetid: 46fab234-1542-49be-8edf-aa101e728acf
caps.latest.revision: 31
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ddf36b834adb7fd3addb6df9cc6cc4dd9c96dcc4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysdatabaserecoverystatus-transact-sql"></a>sys.database_recovery_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  每个数据库占一行。 如果数据库未打开，则 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]尝试启动它。  
  
 若要查看数据库所在行以外**master**或**tempdb**，必须应用以下项之一：  
  
-   是数据库的所有者。  
  
-   拥有 ALTER ANY DATABASE 或 VIEW ANY DATABASE 服务器级别的权限。  
  
-   在中具有 CREATE DATABASE 权限**master**数据库。    
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**database_id**|**int**|数据库 ID（在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例中唯一）。|  
|**database_guid**|**uniqueidentifier**|用于将数据库的所有数据库文件关联在一起。 所有文件必须在其标题页中包含此 GUID，才能使数据库按预期方式启动。 仅有一个数据库拥有此 GUID，但可以通过复制和附加数据库来创建副本。 RESTORE 总是在您还原某个尚不存在的数据库时生成一个新的 GUID。<br /><br /> NULL 表示数据库脱机，或将不启动数据库。|  
|**family_guid**|**uniqueidentifier**|数据库“备份家族”的标识符，用于检测匹配的还原状态。<br /><br /> NULL = 数据库处于脱机状态或数据库将不会启动。|  
|**last_log_backup_lsn**|**numeric(25,0)**|下一次日志备份的起始日志序列号。<br /><br /> 如果为 NULL，事务日志备份最多不能执行，因为数据库处于简单恢复或没有当前数据库备份。|  
|**recovery_fork_guid**|**uniqueidentifier**|标识数据库当前在其上处于活动状态的当前恢复分叉。<br /><br /> NULL 表示数据库脱机，或将不启动数据库。|  
|**first_recovery_fork_guid**|**uniqueidentifier**|恢复分叉开始的标识符。<br /><br /> NULL 表示数据库脱机，或将不启动数据库。|  
|**fork_point_lsn**|**numeric(25,0)**|如果**first_recovery_fork_guid**不等于 (！ =) 到**recovery_fork_guid**， **fork_point_lsn**是当前的分叉点的日志序列号。 否则，该值为 NULL。|  
  
## <a name="permissions"></a>权限  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [数据库和文件目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql.md)   
 [RESTORE HEADERONLY (Transact-SQL)](../../t-sql/statements/restore-statements-headeronly-transact-sql.md)   
 [查询 SQL Server 系统目录常见问题解答](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
