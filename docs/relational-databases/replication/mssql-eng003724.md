---
title: MSSQL_ENG003724 | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c469d2d552d02fb3829a1a176877378cecb10ccc
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="mssqleng003724"></a>MSSQL_ENG003724
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="message-details"></a>消息详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|3724|  
|事件源|MSSQLSERVER|  
|组件|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|符号名称||  
|消息正文|无法对 %S_MSG '%.*ls' 执行 %S_MSG，因为它正用于复制。|  
  
## <a name="explanation"></a>解释  
 数据库中的对象经复制后，通常会在系统表 **sysarticles** （用于快照和事务发布）或 **sysmergearticles** （用于合并发布）中标记为已复制。 尝试删除复制的对象时，会引发此错误。  
  
## <a name="user-action"></a>用户操作  
 尝试删除对象之前，请确保数据库对象未经复制。 例如：  
  
-   如果此错误发生在发布数据库中，则先从发布中删除项目，然后再删除对象。 有关详细信息，请参阅[向现有发布添加项目和从中删除项目](../../relational-databases/replication/publish/add-articles-to-and-drop-articles-from-existing-publications.md)。  
  
-   如果此错误发生在订阅数据库中，则先删除订阅，然后再删除对象。 有关详细信息，请参阅[订阅发布](../../relational-databases/replication/subscribe-to-publications.md)。 对于事务发布的订阅，可以删除单个项目的订阅，而不用删除整个发布。 有关详细信息，请参阅 [sp_dropsubscription (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql.md)。  
  
 如果此错误发生在未复制的数据库中，请执行 [sp_removedbreplication (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql.md)，以确保此数据库中的对象不会标记为已复制。  
  
## <a name="see-also"></a>另请参阅  
 [错误和事件参考（复制）](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  
