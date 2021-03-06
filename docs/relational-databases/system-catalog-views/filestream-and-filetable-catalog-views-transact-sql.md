---
title: Filestream 和 FileTable 的目录视图 (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- FileTables [SQL Server], catalog views
ms.assetid: 2c83a4a7-720b-4435-a3b5-788c29f56949
caps.latest.revision: 7
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9fcd323c157d43d0dad1546004f79f8e5affd60c
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="filestream-and-filetable-catalog-views-transact-sql"></a>Filestream 和 FileTable 目录视图 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  本节介绍与 FileTable 功能相关的目录视图。  
  
## <a name="filestream-and-filetable-catalog-views-transact-sql"></a>Filestream 和 filetable 的目录视图 (TRANSACT-SQL)
 [sys.database_filestream_options (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql.md)  
 显示已启用的针对 FileTable 中的 FILESTREAM 数据的非事务性访问级别的相关信息。 为 SQL Server 实例中的每个数据库包含一行。  
  
 [sys.filetable_system_defined_objects (Transact-SQL)](../../relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql.md)  
 显示与 FileTable 相关的系统定义对象的列表。 为每个系统定义对象包含一行。  
  
 [sys.filetables (Transact-SQL)](../../relational-databases/system-catalog-views/sys-filetables-transact-sql.md)  
 为每个 FileTable 返回一行。 继承自**sys.tables**。  

## <a name="see-also"></a>另请参阅
[Filestream](../../relational-databases/blob/filestream-sql-server.md)
<br>[Filetable](../../relational-databases/blob/filetables-sql-server.md)
<br>[Filestream 和 FileTable 的动态管理视图 (Transact SQL)](../system-dynamic-management-views/filestream-and-filetable-dynamic-management-views-transact-sql.md)
<br>[Filestream 和 FileTable 系统存储过程 (TRANSACT-SQL)](../system-stored-procedures/filestream-and-filetable-system-stored-procedures.md)
  
  
