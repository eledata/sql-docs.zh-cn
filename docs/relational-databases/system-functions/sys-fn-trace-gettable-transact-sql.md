---
title: sys.fn_trace_gettable (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-functions
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- fn_trace_gettable
- fn_trace_gettable_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_trace_gettable function
- sys.fn_trace_gettable function
ms.assetid: c2590159-6ec5-4510-81ab-e935cc4216cd
caps.latest.revision: 35
author: rothja
ms.author: jroth
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 461807f1d79032c85316551adb5229d02aa67b06
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysfntracegettable-transact-sql"></a>sys.fn_trace_gettable (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  以表格形式返回一个或多个跟踪文件的内容。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 请改用扩展事件。  
   
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
fn_trace_gettable ( 'filename' , number_files )  
```  
  
## <a name="arguments"></a>参数  
 *filename*  
 指定要读取的初始跟踪文件。 *filename*是**nvarchar(256)**，无默认值。  
  
 *number_files*  
 指定要读取的滚动更新文件数。 此数字包括中指定的初始文件*filename*。 *number_files*是**int**。  
  
## <a name="remarks"></a>注释  
 如果*number_files*指定为**默认**， **fn_trace_gettable**读取所有滚动更新文件，直到它达到跟踪的末尾。 **fn_trace_gettable**返回包含所有列的表对指定的跟踪有效。 有关详细信息，请参阅[sp_trace_setevent &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)。  
  
 请注意 fn_trace_gettable 函数将不会加载滚动更新文件 (如果通过指定此选项*number_files*自变量) 原始跟踪文件名称与一条下划线和数字值的结束位置。 （这不适用于在文件滚动更新时自动追加的下划线和数字。）作为一种解决方法，您可以重命名这些跟踪文件以便删除原始文件名中的下划线。 例如，如果原始文件命名为**Trace_Oct_5.trc**和滚动更新文件命名为**Trace_Oct_5_1.trc**，你可以重命名的文件**TraceOct5.trc**和**TraceOct5_1.trc**。  
  
 该函数可以读取在执行该函数所在实例中仍处于活动状态的跟踪。  
  
## <a name="permissions"></a>权限  
 要求对服务器具有 ALTER TRACE 权限。  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-fntracegettable-to-import-rows-from-a-trace-file"></a>A. 使用 fn_trace_gettable 从跟踪文件导入行  
 下面的示例在 `fn_trace_gettable` 语句的 `FROM` 子句内部调用 `SELECT...INTO`。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT * INTO temp_trc  
FROM fn_trace_gettable('c:\temp\mytrace.trc', default);  
GO  
```  
  
### <a name="b-using-fntracegettable-to-return-a-table-with-an-identity-column-that-can-be-loaded-into-a-sql-server-table"></a>B. 使用 fn_trace_gettable 返回一个表，其中具有可以加载到 SQL Server 表中的 IDENTITY 列  
 以下示例在 `SELECT...INTO` 语句中调用该函数，并返回一个表，其中具有可加载到表 `IDENTITY` 中的 `temp_trc` 列。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT IDENTITY(int, 1, 1) AS RowNumber, * INTO temp_trc  
FROM fn_trace_gettable('c:\temp\mytrace.trc', default);  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_trace_generateevent &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql.md)   
 [sp_trace_setevent (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [sp_trace_setfilter (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql.md)   
 [sp_trace_setstatus (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql.md)  
  
  
