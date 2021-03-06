---
title: sys.query_store_query (TRANSACT-SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/29/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- QUERY_STORE_QUERY
- SYS.QUERY_STORE_QUERY_TSQL
- SYS.QUERY_STORE_QUERY
- QUERY_STORE_QUERY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- query_store_query catalog view
- sys.query_store_query catalog view
ms.assetid: bdee149e-7556-4fc3-8242-925dd4b7b6ac
caps.latest.revision: 15
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 698478831feeb5ad8719147e03a006ab56ba0eb3
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysquerystorequery-transact-sql"></a>sys.query_store_query (TRANSACT-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  包含有关查询和其关联的总体聚合运行时执行统计信息的信息。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**query_id**|**bigint**|主键。|  
|**query_text_id**|**bigint**|外键。 将联接到[sys.query_store_query_text &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql.md)|  
|**context_settings_id**|**bigint**|外键。 将联接到[sys.query_context_settings &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/sys-query-context-settings-transact-sql.md)。|  
|**object_id**|**bigint**|查询的一部分的数据库对象的 ID (存储过程、 触发器、 CLR UDF/UDAgg，等等。)。 如果查询未执行数据库对象 （即席查询） 的一部分，则为 0。|  
|**batch_sql_handle**|**varbinary(64)**|语句批处理查询 ID 是的一部分。 填充仅当查询引用了临时表或表变量。|  
|**query_hash**|**binary(8)**|MD5 哈希值的单个查询，基于逻辑查询树。 包含优化器提示。|  
|**is_internal_query**|**bit**|内部生成查询。|  
|**query_parameterization_type**|**tinyint**|参数化的类型：<br /><br /> 0 – 无<br /><br /> 1 – 用户<br /><br /> 2-简单<br /><br /> 3 – 强制|  
|**query_parameterization_type_desc**|**nvarchar(60)**|参数化类型的文本说明。|  
|**initial_compile_start_time**|**datetimeoffset**|编译开始时间。|  
|**last_compile_start_time**|**datetimeoffset**|编译开始时间。|  
|**last_execution_time**|**datetimeoffset**|上次执行时间的最后一个引用查询计划的结束的时间。|  
|**last_compile_batch_sql_handle**|**varbinary(64)**|最后一个查询在其中使用上一次的 SQL 批处理的句柄。 它可以作为输入提供[sys.dm_exec_sql_text &#40;TRANSACT-SQL&#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-sql-text-transact-sql.md)以获取批处理的完整文本。|  
|**last_compile_batch_offset_start**|**bigint**|可以向以及 last_compile_batch_sql_handle sys.dm_exec_sql_text 提供的信息。|  
|**last_compile_batch_offset_end**|**bigint**|可以向以及 last_compile_batch_sql_handle sys.dm_exec_sql_text 提供的信息。|  
|**count_compiles**|**bigint**|编译的统计信息。|  
|**avg_compile_duration**|**float**|编译以微秒为单位的统计信息。|  
|**last_compile_duration**|**bigint**|编译以微秒为单位的统计信息。|  
|**avg_bind_duration**|**float**|绑定以微秒为单位的统计信息。|  
|**last_bind_duration**|**bigint**|绑定的统计信息。|  
|**avg_bind_cpu_time**|**float**|绑定的统计信息。|  
|**last_bind_cpu_time**|**bigint**|绑定的统计信息。|  
|**avg_optimize_duration**|**float**|以微秒为单位的优化统计信息。|  
|**last_optimize_duration**|**bigint**|优化的统计信息。|  
|**avg_optimize_cpu_time**|**float**|以微秒为单位的优化统计信息。|  
|**last_optimize_cpu_time**|**bigint**|优化的统计信息。|  
|**avg_compile_memory_kb**|**float**|编译内存统计信息。|  
|**last_compile_memory_kb**|**bigint**|编译内存统计信息。|  
|**max_compile_memory_kb**|**bigint**|编译内存统计信息。|  
|**is_clouddb_internal_query**|**bit**|始终为 0 中[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]本地。|  
  
## <a name="permissions"></a>权限  
 需要**VIEW DATABASE STATE**权限。  
  
## <a name="see-also"></a>另请参阅  
 [sys.database_query_store_options &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql.md)   
 [sys.query_context_settings &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-query-context-settings-transact-sql.md)   
 [sys.query_store_plan &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-query-store-plan-transact-sql.md)   
 [sys.query_store_query_text &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql.md)   
 [sys.query_store_wait_stats (Transact-SQL)](../../relational-databases/system-catalog-views/sys-query-store-wait-stats-transact-sql.md)  
 [sys.query_store_runtime_stats &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql.md)   
 [sys.query_store_runtime_stats_interval &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql.md)   
 [相关视图、函数和过程](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)   
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [查询存储存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql.md)   
 [sys.fn_stmt_sql_handle_from_sql_stmt (Transact-SQL)](../../relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql.md)  
  
  
