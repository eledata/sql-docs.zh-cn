---
title: '@@CURSOR_ROWS (Transact-SQL) | Microsoft Docs'
ms.custom: 
ms.date: 08/18/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@CURSOR_ROWS'
- '@@CURSOR_ROWS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@CURSOR_ROWS function'
- cursors [SQL Server], last-opened
- last-opened cursor
- asynchronous cursors [SQL Server]
ms.assetid: 31bd7a97-7f28-42a8-ba24-24d16d22973d
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 8c4c1fac4c5d9dacddfb942a3e5b9238e5be16a4
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="x40x40cursorrows-transact-sql"></a>&#x40;&#x40;CURSOR_ROWS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回连接上打开的上一个游标中的当前限定行的数目。 为了提高性能，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 可异步填充大型键集和静态游标。 可调用 @@CURSOR_ROWS 以确定当 @@CURSOR_ROWS 被调用时检索了游标符合条件的行数。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```
@@CURSOR_ROWS  
```  
  
## <a name="return-types"></a>返回类型
**integer**
  
## <a name="return-value"></a>返回值  
  
|返回值|Description|  
|---|---|
|-m|游标被异步填充。 返回的值 (-m) 是键集中当前的行数*m*。|  
|-1|游标为动态游标。 因为动态游标可反映所有更改，所以游标符合条件的行数不断变化。 因此，永远不能确定已检索到所有符合条件的行。|  
|0|没有已打开的游标，对于上一个打开的游标没有符合条件的行，或上一个打开的游标已被关闭或被释放。|  
|*n*|游标已完全填充。 返回值 (n) 是游标中的总行数。|  
  
## <a name="remarks"></a>Remarks  
如果上一个游标是异步打开的，则 @@CURSOR_ROWS 返回的数字是负数。 如果 sp_configure cursor threshold 的值大于 0，且游标结果集中的行数大于游标阈值，则异步打开键集驱动程序或静态游标。
  
## <a name="examples"></a>示例  
下面的示例声明了一个游标，并且使用 `SELECT` 显示 `@@CURSOR_ROWS` 的值。 在游标打开前，该设置的值为 `0`，值 `-1` 则表示游标键集被异步填充。
  
```sql
USE AdventureWorks2012;  
GO  
SELECT @@CURSOR_ROWS;  
DECLARE Name_Cursor CURSOR FOR  
SELECT LastName ,@@CURSOR_ROWS FROM Person.Person;  
OPEN Name_Cursor;  
FETCH NEXT FROM Name_Cursor;  
SELECT @@CURSOR_ROWS;  
CLOSE Name_Cursor;  
DEALLOCATE Name_Cursor;  
GO             
```  
  
下面是结果集。
  
```
-----------
0  
```

```
LastName
---------------
Sanchez
```

```
-----------
-1
```  
  
## <a name="see-also"></a>另请参阅
[游标函数 (Transact-SQL)](../../t-sql/functions/cursor-functions-transact-sql.md)  
[OPEN (Transact-SQL)](../../t-sql/language-elements/open-transact-sql.md)
  
  
