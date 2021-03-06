---
title: sys.external_library_files (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 10/05/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- external_library_files
- external_library_files_TSQL
- sys.external_library_files
- sys.external_library_files_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.external_library_files catalog view
author: jeannt
ms.author: jeannt
manager: craigg
monikerRange: '>= sql-server-2017 || = sqlallproducts-allversions'
ms.openlocfilehash: 0278fa01c02bab9da03abb62c375c19e84d1d97d
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysexternallibraryfiles-transact-sql"></a>sys.external_library_files (TRANSACT-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

列出每个文件组成外部库一行。

|列名 |数据类型 |Description|
|------|------|-----|
|external_library_id | int |外部库对象的 ID。 |
|content |varbinary(max) |外部库文件项目的内容。 |
|平台 |tinyint |在其上安装 SQL Server 的主机平台的 ID。 |
|platform_desc | nvarchar(60) |主机平台的名称。 有效值为 WINDOWS、 LINUX。 |

### <a name="see-also"></a>另请参阅  

[sys.external_libraries](sys-external-libraries-transact-sql.md)  
[创建外部库](../../t-sql/statements/create-external-library-transact-sql.md)  
[SQL Server 机器学习服务管理包](../../advanced-analytics/r/installing-and-managing-r-packages.md)  
