---
title: sys.traces (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
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
- traces
- sys.traces_TSQL
- sys.traces
- traces_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.traces catalog view
ms.assetid: 4a03be22-b7da-4e2a-97ff-94bed890a620
caps.latest.revision: 23
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6539df43dfab32bf1ebfa44bc7088653db75ccb0
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="systraces-transact-sql"></a>sys.traces (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **Sys.traces**目录视图包含系统上当前运行的跟踪。 此视图旨在作为替换**fn_trace_getinfo**函数。  
  
 有关受支持的跟踪事件的完整列表，请参阅[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md)。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 请改用扩展事件目录视图。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|跟踪 ID。|  
|**status**|**int**|跟踪状态：<br /><br /> 0 = 停止<br /><br /> 1 = 正在运行|  
|path|nvarchar(260)|跟踪文件的路径。 如果跟踪为行集跟踪，则此值为空值。|  
|**max_size**|**bigint**|跟踪文件的最大大小限制，以兆字节 (MB) 表示。 如果跟踪为行集跟踪，则此值为空值。|  
|**stop_time**|**datetime**|停止运行跟踪的时间。|  
|**max_files**|**int**|滚动更新文件的最大数目。 如果未设置最大数目，则此值是零。|  
|**is_rowset**|**bit**|1 = 行集跟踪。|  
|**is_rollover**|**bit**|1 = 启用滚动更新选项。|  
|**is_shutdown**|**bit**|1 = 启用关闭选项。|  
|**is_default**|**bit**|1 = 默认跟踪。|  
|**buffer_count**|**int**|跟踪使用的内存缓冲区的数目。|  
|**buffer_size**|**int**|每个缓冲区的大小 (KB)。|  
|**file_position**|**bigint**|上一个跟踪文件的位置。 如果跟踪为行集跟踪，则此值为空值。|  
|**reader_spid**|**int**|行集跟踪读取器会话 ID。 如果跟踪为文件跟踪，则此值为 null。|  
|**start_time**|**datetime**|跟踪开始时间。|  
|**last_event_time**|**datetime**|上一个事件触发的时间。|  
|**event_count**|**bigint**|已发生事件的总数。|  
|**dropped_event_count**|**int**|已除去事件的总数。|  
  
## <a name="permissions"></a>权限  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [对象目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [sys.trace_categories &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-categories-transact-sql.md)   
 [sys.trace_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-columns-transact-sql.md)   
 [sys.trace_events &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-events-transact-sql.md)   
 [sys.trace_event_bindings &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)   
 [sys.trace_subclass_values &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-subclass-values-transact-sql.md)  
  
  
