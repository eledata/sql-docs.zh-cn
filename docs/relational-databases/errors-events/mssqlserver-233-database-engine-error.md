---
title: MSSQLSERVER_233 | Microsoft Docs
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
- "233"
helpviewer_keywords:
- 233 (Database Engine error)
ms.assetid: 201665dc-7ac8-4c19-90d3-33354c5caa72
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b441868e6cf3b7220f55fe8ebacbf7e3099078c8
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver233"></a>MSSQLSERVER_233
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|233|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称||  
|消息正文|已成功与服务器建立连接，但是在登录过程中发生错误。 (提供程序: 共享内存提供程序，错误: 0 - 在管道的另一端没有进程。) (Microsoft SQL Server，错误: 233)|  
  
## <a name="explanation"></a>解释  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 客户端无法连接到服务器。 发生此错误的原因可能是服务器未配置为接受远程连接。  
  
## <a name="user-action"></a>用户操作  
使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 配置管理器工具使 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 接受远程连接。  
  
## <a name="see-also"></a>另请参阅  
[网络协议和网络库](~/sql-server/install/network-protocols-and-network-libraries.md)  
[客户端网络配置](~/database-engine/configure-windows/client-network-configuration.md)  
[配置客户端协议](~/database-engine/configure-windows/configure-client-protocols.md)  
[启用或禁用服务器网络协议](~/database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
