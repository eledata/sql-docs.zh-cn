---
title: "数据类型同义词 (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 7/23/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|data-types
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- data types [SQL Server], synonyms
- alternate names [SQL Server]
- synonyms [SQL Server], data types
ms.assetid: 390eef67-1a49-4185-a971-e07765be9717
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 07b4ada74ee54bf1c892e0938dd794e17ea4c0cb
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="data-type-synonyms-transact-sql"></a>数据类型同义词 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中包含数据类型同义词以便实现 ISO 兼容性。 下表列出了这些同义词以及它们映射到的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 系统数据类型。
  
|同义词|SQL Server 系统数据类型|  
|---|---|
|**Binary varying**|**varbinary**|  
|**char varying**|**varchar**|  
|**character**|**char**|  
|**character**|**char(1)**|  
|**character(** *n* **)**|**char(n)**|  
|**character varying(** n **)**|**varchar(n)**|  
|**Dec**|**decimal**|  
|**Double precision**|**float**|  
|**float**[**(**n**)**] for n = 1-7|**real**|  
|**float**[**(**n**)**] for n = 8-15|**float**|  
|**integer**|**int**|  
|**national character(** n **)**|**nchar(n)**|  
|**national char(** n **)**|**nchar(n)**|  
|**national character varying(** n **)**|**nvarchar(n)**|  
|**national char varying(** n **)**|**nvarchar(n)**|  
|**national text**|**ntext**|  
|**timestamp**|rowversion|  
  
在诸如 CREATE TABLE、CREATE PROCEDURE 或 DECLARE @variable 这类数据定义语言 (DDL) 语句中，数据类型同义词可用来代替相应的基本数据类型名。 但是，创建对象后看不到同义词。 创建对象后，为对象分配与同义词相关联的基本数据类型。 没有记录能表明在创建对象的语句中指定了同义词。
  
将给所有由原始对象派生出的对象（如结果集列或表达式）分配基本数据类型。 所有对原始对象和任何派生对象执行的后续元数据函数都将报告基本数据类型，而不是同义词。 这种行为会发生在元数据操作（如 sp_help）和其他报告表或结果集列的数据类型的系统存储过程、信息架构视图或各种数据访问 API 元数据操作上。
  
例如，您可以通过指定 `national character varying` 创建表：
  
```sql
CREATE TABLE ExampleTable (PriKey int PRIMARY KEY, VarCharCol national character varying(10))  
```  
  
实际为 `VarCharCol` 分配了 nvarchar(10) 数据类型，所有后续元数据函数将该列报告为 nvarchar(10) 列。 元数据函数永远不会将它们报告为 national character varying(10) 列。
  
## <a name="see-also"></a>另请参阅
[数据类型 (Transact-SQL)](../../t-sql/data-types/data-types-transact-sql.md)
  
  
