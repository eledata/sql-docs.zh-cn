---
title: sys.registered_search_properties (TRANSACT-SQL) |Microsoft 文档
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.registered_search_properties
- registered_search_properties
- sys.registered_search_properties_TSQL
- registered_search_properties_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- full-text search [SQL Server], search property lists
- search properties [SQL Server]
- property searching [SQL Server], viewing registered properties
- search property lists [SQL Server], viewing registered properties
- sys.registered_search_properties catalog view
ms.assetid: 1b9a7a5c-8c05-4819-83c3-7487dd08fcf7
caps.latest.revision: 20
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: e9ae52577d2e48adefc033b99ec4ca8be4f98650
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysregisteredsearchproperties-transact-sql"></a>sys.registered_search_properties (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  当前数据库中的任何搜索属性列表包含的每个搜索属性各占一行。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**property_list_id**|**int**|此属性所属的搜索属性列表的 ID。|  
|**property_set_guid**|**uniqueidentifier**|标识该搜索属性所属属性集的全局唯一标识符 GUID。|  
|**property_int_id**|**int**|在属性集内标识此搜索属性的整数。 **property_int_id**在属性集内唯一。|  
|**property_name**|**nvarchar(64)**|在搜索属性列表中唯一标识此搜索属性的名称。<br /><br /> 注意： 若要搜索的属性，此属性中指定名称[CONTAINS](../../t-sql/queries/contains-transact-sql.md)谓词。|  
|**property_description**|**nvarchar(512)**|属性的说明。|  
|**property_id**|**int**|由标识搜索属性列表中的搜索属性的内部属性 ID **property_list_id**值。<br /><br /> 在将给定属性添加到给定的搜索属性列表时，全文引擎会注册该属性并为其指定特定于该属性列表的内部属性 ID。 内部属性 ID 是一个整数，对给定的搜索属性列表唯一。 如果为多个搜索属性列表注册给定属性，则可能会为每个搜索属性列表指定不同的内部属性 ID。<br /><br /> 注意： 该内部属性 ID 是不同于属性添加到搜索属性列表时指定的属性整数标识符。 有关详细信息，请参阅 [使用搜索属性列表搜索文档属性](../../relational-databases/search/search-document-properties-with-search-property-lists.md)。<br /><br /> 若要查看全文索引中的所有与属性相关的内容： <br />                  [sys.dm_fts_index_keywords_by_property (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-property-transact-sql.md)|  
  
## <a name="remarks"></a>注释  
 有关搜索属性列表的详细信息，请参阅[使用搜索属性列表搜索文档属性](../../relational-databases/search/search-document-properties-with-search-property-lists.md)。  
  
## <a name="permissions"></a>权限  
 搜索属性的元数据可见性仅限于在您拥有或已向您授予部分 REFERENCE 权限的搜索属性列表中的属性。  
  
> [!NOTE]  
>  搜索属性列表所有者可以授予列表的 REFERENCE 或 CONTROL 权限。 具有 CONTROL 权限的用户还可以向其他用户授予 REFERENCE 权限。  
  
## <a name="examples"></a>示例  
 以下示例列出已注册的搜索属性的所有元数据。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT * FROM sys.registered_search_properties;   
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [ALTER FULLTEXT INDEX (Transact-SQL)](../../t-sql/statements/alter-fulltext-index-transact-sql.md)   
 [sys.fulltext_indexes (Transact-SQL)](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md)   
 [使用搜索属性列表搜索文档属性](../../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
  
