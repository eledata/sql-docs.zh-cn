---
title: sys.remote_data_archive_databases (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-stretch
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.remote_data_archive_databases
- sys.remote_data_archive_databases_TSQL
- remote_data_archive_databases
- remote_data_archive_databases_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.remote_data_archive_databases catalog view
ms.assetid: 25bffb0c-9821-40b4-88cf-75f854891a09
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b67f68c2208ab54cfa87a04db98d6e953a25ede0
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="stretch-database-catalog-views---sysremotedataarchivedatabases"></a>拉伸数据库目录视图-sys.remote_data_archive_databases
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  包含一个行存储从已启用延伸的本地数据库的数据的每个远程数据库。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**remote_database_id**|**int**|自动生成本地标识符的远程数据库。|  
|**remote_database_name**|**sysname**|远程数据库的名称。|  
|**data_source_id**|**int**|用于连接到远程服务器的数据源|  
  
## <a name="see-also"></a>另请参阅  
 [Stretch 数据库](../../sql-server/stretch-database/stretch-database.md)  
  
  
