---
title: CHECKSUM (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CHECKSUM_TSQL
- CHECKSUM
dev_langs:
- TSQL
helpviewer_keywords:
- hash indexes
- CHECKSUM function
- checksum values
ms.assetid: e26d3339-845c-49c2-9d89-243376874c13
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: d41736f6ac216de0ecf755cbf7ca73ba34a697b8
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="checksum-transact-sql"></a>CHECKSUM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-asdw-xxx-md.md)]

返回按照表的某一行或一组表达式计算出来的校验和值。 CHECKSUM 用于生成哈希索引。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```sql
CHECKSUM ( * | expression [ ,...n ] )  
```  
  
## <a name="arguments"></a>参数  
\*  
指定对表的所有列进行计算。 如果有任一列是非可比数据类型，则 CHECKSUM 返回错误。 非可比数据类型有 text、ntext、image、XML 和 cursor，还包括以上述任一类型作为基类型的 sql_variant。
  
*expression*  
除非可比数据类型之外的任何类型的[表达式](../../t-sql/language-elements/expressions-transact-sql.md)。
  
## <a name="return-types"></a>返回类型
 **int**  
  
## <a name="remarks"></a>Remarks  
CHECKSUM 对其参数列表计算一个称为校验和的哈希值。 此哈希值用于生成哈希索引。 如果 CHECKSUM 的参数为列，并且对计算的 CHECKSUM 值生成索引，则结果是一个哈希索引。 它可用于对列进行等价搜索。
  
CHECKSUM 满足哈希函数的下列属性：在使用等于 (=) 运算符比较时，如果两个列表的相应元素具有相同类型且相等，则在任何两个表达式列表上应用的 CHECKSUM 将返回同一值。 对于该定义，指定类型的 Null 值被作为相等进行比较。 如果表达式列表中的某个值发生更改，则列表的校验和通常也会更改。 但只在极少数情况下，校验和会保持不变。 因此，我们不推荐使用 CHECKSUM 来检测值是否更改，除非应用程序可以容忍偶尔丢失更改。 请考虑改用 [HashBytes](../../t-sql/functions/hashbytes-transact-sql.md)。 指定 MD5 哈希算法时，HashBytes 为两个不同输入返回相同结果的可能性比 CHECKSUM 小得多。
  
表达式的顺序影响 CHECKSUM 的结果值。 用于 CHECKSUM(*) 的列顺序是表或视图定义中指定的列顺序。 其中包括计算列。
  
CHECKSUM 值取决于排序规则。 使用不同排序规则存储的相同值将返回一个不同的 CHECKSUM 值。
  
## <a name="examples"></a>示例  
以下示例演示如何使用 `CHECKSUM` 生成哈希索引。 通过将计算校验和列添加到索引的表中，然后对校验和列生成索引来生成哈希索引。
  
```sql
-- Create a checksum index.  
SET ARITHABORT ON;  
USE AdventureWorks2012;   
GO  
ALTER TABLE Production.Product  
ADD cs_Pname AS CHECKSUM(Name);  
GO  
CREATE INDEX Pname_index ON Production.Product (cs_Pname);  
GO  
```  
  
校验和索引可用作哈希索引，尤其是当要索引的列为较长的字符列时可以提高索引速度。 校验和索引可用于等价搜索。
  
```sql
/*Use the index in a SELECT query. Add a second search   
condition to catch stray cases where checksums match,   
but the values are not the same.*/  
SELECT *   
FROM Production.Product  
WHERE CHECKSUM(N'Bearing Ball') = cs_Pname  
AND Name = N'Bearing Ball';  
GO  
```  
  
对计算列创建索引将具体化为校验和列，对 `ProductName` 值所做的任何更改都将传播到校验和列。 也可以直接对索引的列生成索引。 然而，如果键值较长，则很可能不执行校验和索引甚至常规索引。
  
## <a name="see-also"></a>另请参阅
[CHECKSUM_AGG (Transact-SQL)](../../t-sql/functions/checksum-agg-transact-sql.md)  
[HASHBYTES (Transact-SQL)](../../t-sql/functions/hashbytes-transact-sql.md)  
[BINARY_CHECKSUM  (Transact-SQL)](../../t-sql/functions/binary-checksum-transact-sql.md)
  
  
