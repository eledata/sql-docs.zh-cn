---
title: MSSQLSERVER_948 | Microsoft Docs
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
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 623d41edf08c22abc958321ec77ea7e1bf0b5421
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver948"></a>MSSQLSERVER_948
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|948|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|不适用|  
|消息正文|数据库 '%.*ls' 的版本为 %d，无法打开。 此服务器支持 %d 版及更低版本。 不支持降级路径。|  
  
## <a name="explanation"></a>解释  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中的某些功能会影响数据库文件的结构。 将数据库附加到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的另一个实例时，文件格式可能与不同版本的[!INCLUDE[ssDE](../../includes/ssde-md.md)]不兼容。  
  
例如，如果在较高版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中使用 vardecimal 存储格式，并尝试在低于 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2 的版本中附加数据库文件，便可能导致此错误。  
  
## <a name="user-action"></a>用户操作  
确定在发起服务器上运行的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的版本。 在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中，右键单击服务器，然后单击“属性”，或在查询窗口中键入 **SELECT @@VERSION**。 通过使用原始版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 打开数据库。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的实例中调查已在原始数据库中启用的功能。 修改这些设置以适用于将在其中附加数据库的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本。  
  
