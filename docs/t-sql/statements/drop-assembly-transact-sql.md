---
title: DROP ASSEMBLY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 05/10/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP ASSEMBLY
- DROP_ASSEMBLY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- deleting assemblies
- assemblies [CLR integration], removing
- dropping assemblies
- WITH NO DEPENDENTS option
ms.assetid: 452d181a-a8e6-44a3-975d-29966d01b18d
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9c6156ff11476e91f13285c1db7d4cc545d5e8e5
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="drop-assembly-transact-sql"></a>DROP ASSEMBLY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  从当前数据库中删除程序集及其所有关联文件。 使用 [CREATE ASSEMBLY](../../t-sql/statements/create-assembly-transact-sql.md) 可以创建程序集，使用 [ALTER ASSEMBLY](../../t-sql/statements/alter-assembly-transact-sql.md) 则可以修改程序集。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
DROP ASSEMBLY [ IF EXISTS ] assembly_name [ ,...n ]  
[ WITH NO DEPENDENTS ]  
[ ; ]  
```  
  
## <a name="arguments"></a>参数  
 IF EXISTS  
 **适用范围**： [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] （[!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 到 [当前版本](http://go.microsoft.com/fwlink/p/?LinkId=299658)）。  
  
 仅当程序集已存在时对其进行有条件地删除。  
  
 assembly_name  
 希望删除的程序集的名称。  
  
 WITH NO DEPENDENTS  
 如果指定它，则只删除 assembly_name，而不删除该程序集引用的相关程序集。 如果不指定它，则 DROP ASSEMBLY 会删除 assembly_name 和所有相关程序集。  
  
## <a name="remarks"></a>Remarks  
 删除程序集时，将从数据库中删除程序集和它的所有关联文件，例如，源代码和调试文件。  
  
 如果不指定 WITH NO DEPENDENTS，则 DROP ASSEMBLY 删除 assembly_name 和所有相关程序集。 如果删除任何相关程序集的尝试失败，则 DROP ASSEMBLY 返回错误。  
  
 如果程序集被存在于该数据库中的另一个程序集引用，或者它被当前数据库中的公共语言运行时 (CLR) 函数、过程、触发器、用户定义类型或聚合使用，则 DROP ASSEMBLY 返回错误。  
  
 DROP ASSEMBLY 不会干扰引用当前正在运行的程序集的任何代码。 但是，执行 DROP ASSEMBLY 之后，任何调用程序集代码的尝试将失败。  
  
## <a name="permissions"></a>权限  
 需要程序集的所有权，或对它的 CONTROL 权限。  
  
## <a name="examples"></a>示例  
 以下示例假定已在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例中创建程序集 `HelloWorld`。  
  
```  
DROP ASSEMBLY Helloworld ;  
```  
  
## <a name="see-also"></a>另请参阅  
 [CREATE ASSEMBLY (Transact-SQL)](../../t-sql/statements/create-assembly-transact-sql.md)   
 [ALTER ASSEMBLY (Transact-SQL)](../../t-sql/statements/alter-assembly-transact-sql.md)   
 [EVENTDATA (Transact-SQL)](../../t-sql/functions/eventdata-transact-sql.md)   
 [获取有关程序集的信息](../../relational-databases/clr-integration/assemblies-getting-information.md)  
  
  
