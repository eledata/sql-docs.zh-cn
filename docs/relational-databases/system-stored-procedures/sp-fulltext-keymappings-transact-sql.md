---
title: sp_fulltext_keymappings (TRANSACT-SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, pdw
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_fulltext_keymappings_TSQL
- sp_fulltext_keymappings
dev_langs:
- TSQL
helpviewer_keywords:
- full-text indexes [SQL Server], key column
- sp_fulltext_keymappings
- full-text indexes [SQL Server], troubleshooting
ms.assetid: 2818fa42-072d-4664-a2f7-7ec363b51d81
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 872f3c474a790bdf7cbfabb4f8adf36ca0339724
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="spfulltextkeymappings-transact-sql"></a>sp_fulltext_keymappings (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-pdw-md.md)]

  返回文档标识符 (DocId) 和全文键值之间的映射。 DocId 列包含值**bigint**映射到特定的全文索引表中的全文密钥值的整数。 满足搜索条件的 DocId 值将从全文引擎传递到数据库引擎，在数据库引擎中，它们被映射到要查询的基表中的全文键值。 全文键列是表的某一列上必需的唯一索引。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_fulltext_keymappings { table_id | table_id, docid | table_id, NULL, key }  
```  
  
#### <a name="parameters"></a>Parameters  
 *table_id*  
 全文索引表的对象 ID。 如果指定了无效*针对 table_id 所*，返回错误。 有关获取表的对象 ID 的信息，请参阅[OBJECT_ID &#40;TRANSACT-SQL&#41;](../../t-sql/functions/object-id-transact-sql.md)。  
  
 *docid*  
 与键值相对应的内部文档标识符 (DocId)。 无效的 *docid* 值不会返回任何结果。  
  
 *密钥*  
 指定表中的全文键值。 无效的 *key* 值不会返回任何结果。 有关全文键值的信息，请参阅[管理全文索引](http://msdn.microsoft.com/library/28ff17dc-172b-4ac4-853f-990b5dc02fd1)。  
  
> [!IMPORTANT]  
>  有关使用一个、两个或三个参数的信息，请参阅本主题后面的“备注”部分。  
  
## <a name="return-code-values"></a>返回代码值  
 无。  
  
## <a name="result-sets"></a>结果集  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|DocId|**bigint**|与键值相对应的内部文档标识符 (DocId) 列。|  
|Key|*|指定表中的全文键值。<br /><br /> 如果在映射表中不存在任何全文键，则返回一个空的行集。|  
  
 <sup>*</sup> 与基表中的全文键列的数据类型相同键的数据类型。  
  
## <a name="permissions"></a>权限  
 此函数是公用的，因此不需要任何特殊权限。  
  
## <a name="remarks"></a>注释  
 下表说明了使用一个、两个或三个参数的效果。  
  
|参数列表|结果|  
|--------------------------|----------------------|  
|*table_id*|当仅使用调用*针对 table_id 所*参数，sp_fulltext_keymappings 从指定的基表，以及对应于每个键 DocId 返回所有全文键 （键） 值。 包括挂起删除的键。<br /><br /> 此函数对于排除各种问题十分有用。 如果所选的全文键不是整数数据类型，它对于查看全文索引内容尤为有用。 这涉及到加入 sp_fulltext_keymappings 使用的结果的结果**sys.dm_fts_index_keywords_by_document**。 有关详细信息，请参阅[sys.dm_fts_index_keywords_by_document &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-document-transact-sql.md)。<br /><br /> 但是，我们通常建议在可能的情况下使用指定了特定全文键或 DocID 的参数执行 sp_fulltext_keymappings。 与返回完整的键映射相比，这种方法要高效许多，尤其是在处理超大表的时候，对于这些表，返回整个键映射的性能开销可能过于巨大。|  
|*针对 table_id 所*， *docid*|如果仅*针对 table_id 所*和*docid*指定， *docid*必须为非 Null 并指定表中指定有效的 DocId。 若要隔离基表中与特定全文索引的 DocID 对应的自定义全文键，此函数十分有用。|  
|*针对 table_id 所*为 NULL，*密钥*|如果存在三个参数，第二个参数必须为 NULL，和*密钥*必须为非 Null，并指定有效的全文关键值从指定的表。 若要隔离基表中与特定全文键对应的 DocID，此函数十分有用。|  
  
 在以下任一情况下会返回一个错误：  
  
-   指定无效*针对 table_id 所*。  
  
-   表没有经过全文索引。  
  
-   参数应该为非 NULL，但是现在为 NULL  
  
## <a name="examples"></a>示例  
  
> [!NOTE]  
>  本节在此示例使用`Production.ProductReview`表[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]示例数据库。 你可以通过执行提供的示例创建此索引`ProductReview`表中[CREATE FULLTEXT INDEX &#40;TRANSACT-SQL&#41;](../../t-sql/statements/create-fulltext-index-transact-sql.md)。  
  
### <a name="a-obtaining-all-the-key-and-docid-values"></a>A. 获取所有键和 DocId 值  
 下面的示例使用[DECLARE](../../t-sql/language-elements/declare-local-variable-transact-sql.md)语句创建局部变量， `@table_id` ，并向分配的 ID`ProductReview`作为其值的表。 此示例执行**sp_fulltext_keymappings**指定`@table_id`为*针对 table_id 所*参数。  
  
> [!NOTE]  
>  使用**sp_fulltext_keymappings**并且仅带有*针对 table_id 所*参数适合于小型表。  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @table_id int = OBJECT_ID(N'Production.ProductReview');  
EXEC sp_fulltext_keymappings @table_id;  
GO  
  
```  
  
 此示例返回表中的所有 DocId 和全文键，如下所示：  
  
||||  
|-|-|-|  
||`docid`|`key`|  
|`1`|`1`|`1`|  
|`2`|`2`|`2`|  
|`3`|`3`|`3`|  
|`4`|`4`|`4`|  
  
### <a name="b-obtaining-the-docid-value-for-a-specific-key-value"></a>B. 获取特定键值的 DocId 值  
 下面的示例使用 DECLARE 语句创建局部变量 `@table_id`，并将 `ProductReview` 表的 ID 赋值给该变量。 此示例执行**sp_fulltext_keymappings**指定`@table_id`为*针对 table_id 所*参数，NULL 表示*docid*参数，并且 4 *密钥*参数。  
  
> [!NOTE]  
>  使用**sp_fulltext_keymappings**并且仅带有*针对 table_id 所*参数适用于小的表。  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @table_id int = OBJECT_ID(N'Production.ProductReview');  
EXEC sp_fulltext_keymappings @table_id, NULL, 4;  
GO  
  
```  
  
 此示例返回以下结果。  
  
||||  
|-|-|-|  
||`docid`|`key`|  
|`4`|`4`|`4`|  
  
## <a name="see-also"></a>另请参阅  
 [全文搜索和语义搜索存储过程&#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/full-text-search-and-semantic-search-stored-procedures-transact-sql.md)  
  
  
