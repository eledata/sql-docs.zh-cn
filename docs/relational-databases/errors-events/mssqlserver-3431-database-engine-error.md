---
title: MSSQLSERVER_3431 | Microsoft Docs
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
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a8b5fad28f6df88f0c245d50d65c78596e64e31c
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver3431"></a>MSSQLSERVER_3431
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|3431|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|UNRESOLVED_XACT|  
|消息正文|无法恢复数据库 '%.*ls' (数据库 ID 为 %d)，因为事务结果尚未解析。 Microsoft 分布式事务处理协调器 (MS DTC) 事务已准备好，但 MS DTC 无法确定解析方法。 若要进行解析，请修复 MS DTC，从完整备份进行还原，或者修复数据库。|  
  
## <a name="explanation"></a>解释  
在数据库关闭时，使用 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 分布式事务处理协调器 (MS DTC) 的一项或多项分布式事务尚未完成。 此数据库的恢复失败，因为没有来自 MS DTC 的详细信息，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 无法完成事务或回退事务。  
  
## <a name="user-action"></a>用户操作  
若要恢复该数据库，必须首先解决 MS DTC 存在的问题。 若要调查 MS DTC 存在的问题，请检查 Windows 事件日志。 如果无法解决 MS DTC 问题和恢复数据库，请还原数据库备份。  
  
