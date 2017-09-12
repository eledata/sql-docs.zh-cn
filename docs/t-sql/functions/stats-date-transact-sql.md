---
title: "STATS_DATE (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STATS_DATE_TSQL
- STATS_DATE
dev_langs:
- TSQL
helpviewer_keywords:
- statistical information [SQL Server], last time updated
- STATS_DATE function
- query optimization statistics [SQL Server], last time updated
- last time statistics updated
ms.assetid: f9ec3101-1e41-489d-b519-496a0d6089fb
caps.latest.revision: 43
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 44fc7524040db874abc5d596b641cba985dcf893
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="statsdate-transact-sql"></a>STATS_DATE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  返回表或索引视图上统计信息的最新更新的日期。  
  
 有关更新统计信息的详细信息，请参阅[统计信息](../../relational-databases/statistics/statistics.md)。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
STATS_DATE ( object_id , stats_id )  
```  
  
## <a name="arguments"></a>参数  
 *object_id*  
 具有统计信息的表或索引视图的 ID。  
  
 *stats_id*  
 统计信息对象的 ID。  
  
## <a name="return-types"></a>返回类型  
 返回**datetime**成功。 返回**NULL**错误。  
  
## <a name="remarks"></a>注释  
 系统函数可以在选择列表、WHERE 子句和任何允许使用表达式的地方使用。  
  
## <a name="permissions"></a>Permissions  
 若要查看表或索引视图的元数据，需要 db_owner 固定数据库角色中的成员身份或权限。  
  
## <a name="examples"></a>示例  
  
### <a name="a-return-the-dates-of-the-most-recent-statistics-for-a-table"></a>A. 返回表的最近统计信息的日期  
 下面的示例返回 `Person.Address` 表上的每个统计信息对象的最新更新的日期。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT name AS stats_name,   
    STATS_DATE(object_id, stats_id) AS statistics_update_date  
FROM sys.stats   
WHERE object_id = OBJECT_ID('Person.Address');  
GO  
```  
  
 如果统计信息对应于索引， *stats_id*中的值[sys.stats](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md)目录视图等同于*index_id*中的值[sys.indexes](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)目录视图和以下查询将返回与前面的查询相同的结果。 如果统计信息不对应于索引，它们是 sys.stats 结果中但不是在 sys.indexes 结果。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT name AS index_name,   
    STATS_DATE(object_id, index_id) AS statistics_update_date  
FROM sys.indexes   
WHERE object_id = OBJECT_ID('Person.Address');  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-learn-when-a-named-statistics-was-last-updated"></a>B. 了解上次更新命名统计信息  
 下面的示例在 DimCustomer 表的 LastName 列上创建统计信息。 然后，它将运行查询以显示统计信息的日期。 然后对其进行更新统计信息和运行查询后，再次以显示更新的日期。  
  
```  
  
--First, create a statistics object  
USE AdventureWorksPDW2012;  
GO  
CREATE STATISTICS Customer_LastName_Stats  
ON AdventureWorksPDW2012.dbo.DimCustomer (LastName)  
WITH SAMPLE 50 PERCENT;  
GO  
  
--Return the date when Customer_LastName_Stats was last updated  
USE AdventureWorksPDW2012;  
GO  
SELECT stats_id, name AS stats_name,   
    STATS_DATE(object_id, stats_id) AS statistics_date  
FROM sys.stats s  
WHERE s.object_id = OBJECT_ID('dbo.DimCustomer')  
    AND s.name = 'Customer_LastName_Stats';  
GO  
  
--Update Customer_LastName_Stats so it will have a different timestamp in the next query  
GO  
UPDATE STATISTICS dbo.dimCustomer (Customer_LastName_Stats);  
  
--Return the date when Customer_LastName_Stats was last updated.  
SELECT stats_id, name AS stats_name,   
    STATS_DATE(object_id, stats_id) AS statistics_date  
FROM sys.stats s  
WHERE s.object_id = OBJECT_ID('dbo.DimCustomer')  
    AND s.name = 'Customer_LastName_Stats';  
GO  
  
```  
  
### <a name="c-view-the-date-of-the-last-update-for-all-statistics-on-a-table"></a>C. 查看表中的所有统计信息的上次更新日期  
 上次更新 DimCustomer 表上的每个统计信息对象时，此示例将返回的日期。  
  
```  
--Return the dates all statistics on the table were last updated.  
SELECT stats_id, name AS stats_name,   
    STATS_DATE(object_id, stats_id) AS statistics_date  
FROM sys.stats s  
WHERE s.object_id = OBJECT_ID('dbo.DimCustomer');  
GO  
```  
  
 如果统计信息对应于索引， *stats_id*中的值[sys.stats](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md)目录视图等同于*index_id*中的值[sys.indexes](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)目录视图和以下查询将返回与前面的查询相同的结果。 如果统计信息不对应于索引，它们是 sys.stats 结果中但不是在 sys.indexes 结果。  
  
```  
USE AdventureWorksPDW2012;  
GO  
SELECT name AS index_name,   
    STATS_DATE(object_id, index_id) AS statistics_update_date  
FROM sys.indexes   
WHERE object_id = OBJECT_ID('dbo.DimCustomer');  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [System Functions (Transact-SQL)](../../relational-databases/system-functions/system-functions-for-transact-sql.md)   
 [UPDATE STATISTICS (Transact-SQL)](../../t-sql/statements/update-statistics-transact-sql.md)   
 [sp_autostats &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-autostats-transact-sql.md)   
 [统计信息](../../relational-databases/statistics/statistics.md)  
  
  

