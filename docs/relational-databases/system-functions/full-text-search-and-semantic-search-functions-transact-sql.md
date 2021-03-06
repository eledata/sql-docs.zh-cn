---
title: 全文搜索和语义搜索函数 (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/06/2017
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
dev_langs:
- TSQL
helpviewer_keywords:
- semantic search [SQL Server], system functions
ms.assetid: a61a3694-7604-4583-962e-fc30f771c6fa
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9011efd5281b6fa30259623a84f8477540de6b6e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="full-text-search-and-semantic-search-functions-transact-sql"></a>全文搜索和语义搜索函数 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  本节介绍与全文搜索以及语义搜索相关的系统函数。  
  
## <a name="full-text-search-functions"></a>全文搜索函数  
 [CONTAINSTABLE (Transact-SQL)](../../relational-databases/system-functions/containstable-transact-sql.md)  
 返回由包含以下各项的列组成的零行、一行或多行表：单个词或短语的完全匹配项或模糊匹配项、词在一定差别范围内的相近或加权匹配项。  
  
 [FREETEXTTABLE (Transact-SQL)](../../relational-databases/system-functions/freetexttable-transact-sql.md)  
 返回由零个、 一个或多行包含匹配的含义，，而不仅仅是词必须完全相同中指定, 的文本的值的这些列的表*freetext_string*。  
  
## <a name="semantic-search-functions"></a>语义搜索函数  
 [semantickeyphrasetable (Transact-SQL)](../../relational-databases/system-functions/semantickeyphrasetable-transact-sql.md)  
 为与指定表中的列关联的那些关键短语返回包含零行、一行或多行的表。  
  
 [semanticsimilaritydetailstable (Transact-SQL)](../../relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql.md)  
 返回一个表，该表包含内容在语义上相似的两个文档（源文档和匹配的文档）共有的零个、一个或多个关键短语行。  
  
 [semanticsimilaritytable (Transact-SQL)](../../relational-databases/system-functions/semanticsimilaritytable-transact-sql.md)  
 为内容语义上类似于指定文档的列返回具有零个、一个或多个行的表。  
  
  
