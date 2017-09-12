---
title: "修改现有跟踪 (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
caps.latest.revision: 18
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 0f58e12e1c04c65974dbc985c8acc525ed44be06
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="modify-an-existing-trace-transact-sql"></a>修改现有跟踪 (Transact-SQL)
  本主题介绍了如何使用存储过程修改现有跟踪。  
  
### <a name="to-modify-an-existing-trace"></a>修改现有跟踪  
  
1.  如果跟踪已在运行，请在执行 **sp_trace_setstatus** 时通过指定 **@status = 0** 停止跟踪。  
  
2.  若要修改跟踪事件，请执行 **sp_trace_setevent** ，并通过参数指定更改。 下面按顺序列出了参数：  
  
    -   **@traceid** (Trace ID)  
  
    -   **@eventid** (Event ID)  
  
    -   **@columnid** (Column ID)  
  
    -   **@on** (ON)  
  
     修改 **@on** 参数时，请记住它与 **@columnid** 参数是相互作用的：  
  
    |ON|列 ID|结果|  
    |--------|---------------|------------|  
    |ON (**1**)|NULL|事件打开， 所有列被清除。|  
    ||NOT NULL|指定事件的列打开。|  
    |OFF (**0**)|NULL|事件关闭， 所有列被清除。|  
    ||NOT NULL|指定事件的列关闭。|  
  
> [!IMPORTANT]  
>  与常规的存储过程不同，所有 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 存储过程 (**sp_trace_*xx***) 参数的类型都受到严格限制，不支持自动的数据类型转换。 如果这些参数不是使用正确的输入参数数据类型（正如参数说明中指定的一样）调用的，则存储过程会返回错误。  
  
## <a name="see-also"></a>另请参阅  
 [sp_trace_setevent (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [sp_trace_setstatus (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [SQL Server Profiler 存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql.md)  
  
  