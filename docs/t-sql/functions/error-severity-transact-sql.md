---
title: ERROR_SEVERITY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ERROR_SEVERITY_TSQL
- ERROR_SEVERITY
dev_langs:
- TSQL
helpviewer_keywords:
- errors [SQL Server], severity
- messages [SQL Server], severity
- TRY...CATCH [SQL Server]
- CATCH block
- ERROR_SEVERITY function
ms.assetid: 50228f2f-6949-4d2e-8e43-fad11bf973ab
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: d5c8b4aa0a53a39ed6773fdf90ff42dc6128b2f3
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="errorseverity-transact-sql"></a>ERROR_SEVERITY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  返回导致 TRY…CATCH 构造的 CATCH 块运行的错误的严重性。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
ERROR_SEVERITY ( )  
```  
  
## <a name="return-types"></a>返回类型  
 **int**  
  
## <a name="return-value"></a>返回值  
 在 CATCH 块中调用时，返回导致 CATCH 块运行的错误消息的严重级别。  
  
 如果在 CATCH 块作用域以外调用，则返回 NULL。  
  
## <a name="remarks"></a>Remarks  
 ERROR_SEVERITY 可以在 CATCH 块范围内的任意位置调用。  
  
 ERROR_SEVERITY 返回错误严重级别，不管它运行多少次，或它运行在 CATCH 块的范围内的什么位置。 这与 @@ERROR 之类的函数形成鲜明对比，后者只在导致错误的语句的下一个语句中或者在 CATCH 块的第一个语句中返回错误号。  
  
 在嵌套 CATCH 块中，ERROR_SEVERITY 返回特定于引用它的 CATCH 块的范围的错误严重级别。 例如，外部 TRY...CATCH 构造的 CATCH 块可能具有嵌套 TRY...CATCH 构造。 在嵌套 CATCH 块中，ERROR_SEVERITY 返回调用了嵌套 CATCH 块的错误的严重级别。 如果 ERROR_SEVERITY 运行在 CATCH 块以外，则它会返回调用该 CATCH 块的错误的严重级别。  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-errorseverity-in-a-catch-block"></a>A. 在 CATCH 块中使用 ERROR_SEVERITY  
 下面的示例显示生成被零除错误的 `SELECT` 语句。 返回错误的严重级别。  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT ERROR_SEVERITY() AS ErrorSeverity;  
END CATCH;  
GO  
```  
  
### <a name="b-using-errorseverity-in-a-catch-block-with-other-error-handling-tools"></a>B. 使用其他错误处理工具在 CATCH 块中使用 ERROR_SEVERITY  
 下面的示例显示一个会生成被零除错误的 `SELECT` 语句。 同时与严重级别一起返回与该错误相关的信息。  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT  
        ERROR_NUMBER() AS ErrorNumber,  
        ERROR_SEVERITY() AS ErrorSeverity,  
        ERROR_STATE() AS ErrorState,  
        ERROR_PROCEDURE() AS ErrorProcedure,  
        ERROR_LINE() AS ErrorLine,  
        ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 和 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-using-errorseverity-in-a-catch-block-with-other-error-handling-tools"></a>C. 使用其他错误处理工具在 CATCH 块中使用 ERROR_SEVERITY  
 下面的示例显示一个会生成被零除错误的 `SELECT` 语句。 同时与严重级别一起返回与该错误相关的信息。  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT  
        ERROR_NUMBER() AS ErrorNumber,  
        ERROR_SEVERITY() AS ErrorSeverity,  
        ERROR_STATE() AS ErrorState,  
        ERROR_PROCEDURE() AS ErrorProcedure,  
        ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [sys.messages (Transact-SQL)](../../relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages.md)   
 [TRY...CATCH (Transact-SQL)](../../t-sql/language-elements/try-catch-transact-sql.md)   
 [ERROR_LINE (Transact-SQL)](../../t-sql/functions/error-line-transact-sql.md)   
 [ERROR_MESSAGE (Transact-SQL)](../../t-sql/functions/error-message-transact-sql.md)   
 [ERROR_NUMBER (Transact-SQL)](../../t-sql/functions/error-number-transact-sql.md)   
 [ERROR_PROCEDURE (Transact-SQL)](../../t-sql/functions/error-procedure-transact-sql.md)   
 [ERROR_STATE (Transact-SQL&)](../../t-sql/functions/error-state-transact-sql.md)   
 [RAISERROR (Transact-SQL)](../../t-sql/language-elements/raiserror-transact-sql.md)   
 [@@ERROR (Transact-SQL)](../../t-sql/functions/error-transact-sql.md)  
  
  

