---
title: MSSQLSERVER_3176 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: errors-events
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 27a1dc96d923e1958c5b914ff55c8ea81417e860
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver3176"></a>MSSQLSERVER_3176
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|事件 ID|3176|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|LDDB_FILE_CLAIM|  
|消息正文|'%ls'(%d)和 '%ls'(%d)要求使用文件 '%ls'。 WITH MOVE 子句可用于重新定位一个或多个文件。|  
  
## <a name="explanation"></a>解释  
尝试在多项操作中使用同一文件。  
  
### <a name="possible-causes"></a>可能的原因  
其他数据库已经在使用该文件名。  
  
## <a name="user-action"></a>用户操作  
将数据库文件还原到不同位置。 在 RESTORE 语句中，使用 WITH MOVE 子句移动各个文件。 在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中，在“还原数据库选项”对话框的“将数据库文件还原为”网格中更改文件位置。  
  
## <a name="see-also"></a>另请参阅  
[将数据库还原到新位置 (SQL Server)](~/relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
[将文件还原到新位置 (SQL Server)](~/relational-databases/backup-restore/restore-files-to-a-new-location-sql-server.md)  
[RESTORE (Transact-SQL)](~/t-sql/statements/restore-statements-transact-sql.md)  
  
