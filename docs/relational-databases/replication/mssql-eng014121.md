---
title: MSSQL_ENG014121 | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5a30282d09563f586b307541a25bea5b39f27317
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="mssqleng014121"></a>MSSQL_ENG014121
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="message-details"></a>消息详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|14121|  
|事件源|MSSQLSERVER|  
|组件|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|符号名称||  
|消息正文|无法删除分发服务器 '%s'。 此分发服务器与分发数据库相关联。|  
  
## <a name="explanation"></a>解释  
 配置为分发服务器的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例无法从分发服务器的角色中删除，因为存在与此实例相关联的分发数据库。 如果试图删除与一个或多个发布服务器相关联的分发数据库，将发生此错误。  
  
## <a name="user-action"></a>用户操作  
 若要查找与此分发服务器关联的任何发布服务器和分发数据库的名称，请从分发服务器上的任何数据库中执行 [sp_helpdistpublisher (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql.md)。  
  
 对与此分发服务器关联的任何分发数据库，执行 [sp_dropdistributiondb (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql.md)。 删除所有分发数据库关联后，才可以禁用分发。  
  
## <a name="see-also"></a>另请参阅  
 [错误和事件参考（复制）](../../relational-databases/replication/errors-and-events-reference-replication.md)   
 [配置分发](../../relational-databases/replication/configure-distribution.md)  
  
  
