---
title: MSSQLSERVER_1461 | Microsoft Docs
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
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 47dcf5e0a055e6decd359ffc9479387194776428
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver1461"></a>MSSQLSERVER_1461
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|1461|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|DBM_SAFETY_MISMATCH|  
|消息正文|在服务器中检测到数据库"%.*ls"的不同数据库镜像安全级别。 将使用 FULL 安全级别。|  
  
## <a name="explanation"></a>解释  
修改事务安全级别时镜像连接断开，因为事务安全设置在主体数据库和镜像数据库中不一致。 将使用完全事务安全的默认安全设置。 会话将在高安全模式下运行。  
  
## <a name="user-action"></a>用户操作  
若要关闭事务安全，请对主体数据库重新运行 ALTER DATABASE *database_name* SET PARTNER SAFETY OFF 语句。  
  
