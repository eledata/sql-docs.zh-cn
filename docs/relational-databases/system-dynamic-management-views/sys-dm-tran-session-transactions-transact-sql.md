---
title: sys.dm_tran_session_transactions (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: dmv's
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- dm_tran_session_transactions
- sys.dm_tran_session_transactions
- sys.dm_tran_session_transactions_TSQL
- dm_tran_session_transactions_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_tran_session_transactions dynamic management view
ms.assetid: c7157491-58c2-49fe-87d7-0c9723113adf
caps.latest.revision: 30
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: e8d4c88db1a654fc4afcd045ec20e9e8e49ad8d6
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysdmtransessiontransactions-transact-sql"></a>sys.dm_tran_session_transactions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  返回关联事务和会话的相关信息。  
  
> [!NOTE]  
>  若要从我们称之为[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]或[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]，使用名称**sys.dm_pdw_nodes_tran_session_transactions**。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|session_id|**int**|正在运行事务的会话的 ID。|  
|transaction_id|**bigint**|事务 ID。|  
|transaction_descriptor|**binary(8)**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 在与客户端驱动程序通信时使用的事务标识符。|  
|enlist_count|**int**|正在处理事务的会话中的活动请求数。|  
|is_user_transaction|**bit**|1 = 事务由用户请求启动。<br /><br /> 0 = 系统事务。|  
|is_local|**bit**|1 = 本地事务。<br /><br /> 0 = 分布式事务或登记的绑定会话事务。|  
|is_enlisted|**bit**|1 = 登记的分布式事务。<br /><br /> 0 = 非登记的分布式事务。|  
|is_bound|**bit**|1 = 事务在通过绑定会话的会话中处于活动状态。<br /><br /> 0 = 事务在通过绑定会话的会话中处于非活动状态。|  
|open_transaction_count||每个会话的打开的事务数。|  
|pdw_node_id|**int**|**适用于**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]， [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> 此分布的节点标识符。|  
  
## <a name="permissions"></a>权限

上[!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)]，需要`VIEW SERVER STATE`权限。   
上[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]，需要`VIEW DATABASE STATE`数据库中的权限。   

## <a name="remarks"></a>注释  
 通过绑定会话和分布式事务，一个事务可以运行于多个会话中。 在这种情况下，sys.dm_tran_session_transactions 将对同一 transaction_id 显示多个行，当前运行事务的每个会话对应一行。  
  
 通过使用多个活动的结果集 (MARS) 以自动提交模式执行多个请求，一个会话中可以有多个活动事务。 在这种情况下，sys.dm_tran_session_transactions 将对同一 session_id 显示多个行，在该会话中运行的每个事务对应一行。  
  
## <a name="see-also"></a>另请参阅  
 [动态管理视图和函数 (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [与事务相关的动态管理视图和函数 (Transact-SQL)](../../relational-databases/system-dynamic-management-views/transaction-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  


