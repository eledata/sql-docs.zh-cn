---
title: CHECKSUM_AGG (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
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
- CHECKSUM_AGG
- CHECKSUM_AGG_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- checksum values
- CHECKSUM_AGG function
- groups [SQL Server], checksum values
ms.assetid: cdede70c-4eb5-4c92-98ab-b07787ab7222
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 3499cd8fb118d12fdbf450c23f2919fd0003cee7
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="checksumagg-transact-sql"></a>CHECKSUM_AGG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回组中各值的校验和。 Null 值会被忽略。 后面可以跟随 [OVER 子句](../../t-sql/queries/select-over-clause-transact-sql.md)。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```sql
CHECKSUM_AGG ( [ ALL | DISTINCT ] expression )  
```  
  
## <a name="arguments"></a>参数  
**ALL**  
向所有值应用此聚合函数。 ALL 为默认值。
  
DISTINCT  
指定 CHECKSUM_AGG 返回唯一校验值。
  
*expression*  
整数[表达式](../../t-sql/language-elements/expressions-transact-sql.md)。 不允许使用聚合函数和子查询。
  
## <a name="return-types"></a>返回类型
将所有表达式值的校验和作为 int 类型返回。
  
## <a name="remarks"></a>Remarks  
CHECKSUM_AGG 可用于检测表中的更改。
  
表中行的顺序不影响 CHECKSUM_AGG 的结果。 此外，CHECKSUM_AGG 函数还可与 DISTINCT 关键字和 GROUP BY 子句一起使用。
  
如果表达式列表中的某个值发生更改，则列表的校验和通常也会更改。 但只在极少数情况下，校验和会保持不变。
  
CHECKSUM_AGG 与其他聚合函数具有相似的功能。 有关详细信息，请参阅[聚合函数 (Transact-SQL)](../../t-sql/functions/aggregate-functions-transact-sql.md)。
  
## <a name="examples"></a>示例  
以下示例使用 `CHECKSUM_AGG` 检测 [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] 数据库中 `Quantity` 表的 `ProductInventory` 列中的更改。
  
```sql
--Get the checksum value before the column value is changed.  
SELECT CHECKSUM_AGG(CAST(Quantity AS int))  
FROM Production.ProductInventory;  
GO  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
------------------------  
262  
```  
  
```sql
UPDATE Production.ProductInventory   
SET Quantity=125  
WHERE Quantity=100;  
GO  
--Get the checksum of the modified column.  
SELECT CHECKSUM_AGG(CAST(Quantity AS int))  
FROM Production.ProductInventory;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
------------------------  
287  
```  
  
## <a name="see-also"></a>另请参阅
[CHECKSUM (Transact-SQL)](../../t-sql/functions/checksum-transact-sql.md)  
[OVER 子句 (Transact-SQL)](../../t-sql/queries/select-over-clause-transact-sql.md)
  
  
