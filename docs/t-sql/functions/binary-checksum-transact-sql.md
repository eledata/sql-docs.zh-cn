---
title: BINARY_CHECKSUM  (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, database-engine, sql-database
ms.service: ''
ms.component: t-sql|functions
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- BINARY_CHECKSUM
- BINARY_CHECKSUM_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- BINARY_CHECKSUM function
- binary [SQL Server], checksum values
ms.assetid: 07fece4d-58e3-446e-a3b5-92fe24d2d1fb
caps.latest.revision: 21
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 9ff8368877b3fb2153685554f1484b5fbbcc7c3a
ms.sourcegitcommit: 059fc64ba858ea2adaad2db39f306a8bff9649c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2018
---
# <a name="binarychecksum--transact-sql"></a>BINARY_CHECKSUM  (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-asdw-xxx-md.md)]

返回按照表的某一行或表达式列表计算的二进制校验和值。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```sql
BINARY_CHECKSUM ( * | expression [ ,...n ] )   
```  
  
## <a name="arguments"></a>参数  
*\**  
指定对表中的所有列进行计算。 BINARY_CHECKSUM 在计算中忽略具有不可比数据类型的列。 不可比数据类型包括 text、ntext、image、cursor、xml 和不可比公共语言运行库 (CLR) 用户定义的类型。
  
*expression*  
是任何类型的[表达式](../../t-sql/language-elements/expressions-transact-sql.md)。 BINARY_CHECKSUM 在计算中忽略具有不可比数据类型的表达式。

## <a name="return-types"></a>返回类型  
 **int**
  
## <a name="remarks"></a>Remarks  
按照表中任一行计算的 BINARY_CHECKSUM(*) 返回相同的值，只要随后未修改行。 BINARY_CHECKSUM 满足哈希函数的下列属性：在使用等于 (=) 运算符比较时，如果两个列表的相应元素具有相同类型且相等，则在任何两个表达式列表上应用的 BINARY_CHECKSUM 将返回同一值。 对于该定义，指定类型的 Null 值被作为相等进行比较。 如果表达式列表中的某个值发生更改，则列表的校验和通常也会更改。 但只在极少数情况下，校验和会保持不变。 因此，我们不推荐使用 BINARY_CHECKSUM 来检测值是否更改，除非应用程序可以容忍偶尔丢失更改。 请考虑改用 HashBytes。 指定 MD5 哈希算法时，HashBytes 为两个不同输入返回相同结果的可能性比 BINARY_CHECKSUM 小得多。
  
BINARY_CHECKSUM 可应用于表达式列表，并为指定列表返回相同的值。 如果任意两个表达式列表的对应元素具有相同的类型和字节表示形式，则对这两个列表应用的 BINARY_CHECKSUM 将返回相同的值。 对于此定义，指定类型的 Null 值被认为具有相同的字节表示形式。
  
BINARY_CHECKSUM 和 CHECKSUM 具有相似的功能：它们可用于计算表达式列表上的校验值，且表达式的顺序将影响结果值。 用于 BINARY_CHECKSUM(*) 的列顺序是在表或视图定义中指定的列顺序。 这些包括计算列。
  
CHECKSUM 和 BINARY_CHECKSUM 仅为字符串数据类型返回不同的值，这类字符串的区域设置可能导致具有不同表示形式的字符串进行等值比较。 字符串数据类型为 char、varchar、nchar、nvarchar 或 sql_variant（如果 sql_variant 的基类型为字符串数据类型）。 例如，字符串“McCavity”和“Mccavity”的 BINARY_CHECKSUM 值不同。 反之，在不区分大小写的服务器中，上述字符串的 CHECKSUM 返回相同的校验值。 CHECKSUM 值不应与 BINARY_CHECKSUM 值进行比较。
 
BINARY_CHECKSUM 支持最多 8,000 个 varbinary(max) 类型的字符和最多 255 个 nvarchar(max) 类型字符。
  
## <a name="examples"></a>示例  
以下示例使用 `BINARY_CHECKSUM` 检测表的行中的更改。
  
```sql
USE AdventureWorks2012;  
GO  
CREATE TABLE myTable (column1 int, column2 varchar(256));  
GO  
INSERT INTO myTable VALUES (1, 'test');  
GO  
SELECT BINARY_CHECKSUM(*) from myTable;  
GO  
UPDATE myTable set column2 = 'TEST';  
GO  
SELECT BINARY_CHECKSUM(*) from myTable;  
GO  
```  
  
## <a name="see-also"></a>另请参阅
[聚合函数 (Transact-SQL)](../../t-sql/functions/aggregate-functions-transact-sql.md)  
[CHECKSUM (Transact-SQL)](../../t-sql/functions/checksum-transact-sql.md)  
[CHECKSUM_AGG (Transact-SQL)](../../t-sql/functions/checksum-agg-transact-sql.md)
  
  
