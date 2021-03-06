---
title: DATABASE_PRINCIPAL_ID (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/29/2017
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
- DATABASE_PRINCIPAL_ID_TSQL
- DATABASE_PRINCIPAL_ID
dev_langs:
- TSQL
helpviewer_keywords:
- identification numbers [SQL Server], principals
- principal ID numbers [SQL Server]
- DATABASE_PRINCIPAL_ID function
- IDs [SQL Server], principals
ms.assetid: 908c7dd8-c10b-4658-92f6-0224f9835dd9
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 44f4bd65c93fc0c6ed0fd069946fabaedd1e0943
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="databaseprincipalid-transact-sql"></a>DATABASE_PRINCIPAL_ID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回当前数据库中的主体的 ID 号。 有关主体的详细信息，请参阅[主体（数据库引擎）](../../relational-databases/security/authentication-access/principals-database-engine.md)。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```sql
DATABASE_PRINCIPAL_ID ( 'principal_name' )  
```  
  
## <a name="arguments"></a>参数  
principal_name  
是 sysname 类型的表达式，表示数据库主体。  
如果省略 principal_name，则返回当前用户的 ID。 需要使用括号。
  
## <a name="return-types"></a>返回类型
**int**  
数据库主体不存在时为 NULL。
  
## <a name="remarks"></a>Remarks  
可以在选择列表、WHERE 子句或表达式允许的任意位置使用 DATABASE_PRINCIPAL_ID。 有关详细信息，请参阅[表达式 (Transact-SQL)](../../t-sql/language-elements/expressions-transact-sql.md)。
  
## <a name="examples"></a>示例  
  
### <a name="a-retrieving-the-id-of-the-current-user"></a>A. 检索当前用户的 ID  
以下示例返回当前用户的数据库主体 ID。
  
```sql
SELECT DATABASE_PRINCIPAL_ID();  
GO  
```  
  
### <a name="b-retrieving-the-id-of-a-specified-database-principal"></a>B. 检索指定数据库主体的 ID  
以下示例返回数据库角色 `db_owner` 的数据库主体 ID。
  
```sql
SELECT DATABASE_PRINCIPAL_ID('db_owner');  
GO  
```  
  
## <a name="see-also"></a>另请参阅
[主体（数据库引擎）](../../relational-databases/security/authentication-access/principals-database-engine.md)  
[权限层次结构（数据库引擎）](../../relational-databases/security/permissions-hierarchy-database-engine.md)  
[sys.database_principals (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-principals-transact-sql.md)
  
  
