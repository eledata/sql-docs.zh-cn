---
title: "启动复制监视器 | Microsoft Docs"
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
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9e1a339c818c4199656d3114d214b2908501a017
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="start-the-replication-monitor"></a>启动复制监视器
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  可以从任何 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] 实例上的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]中启动复制监视器，也可以在命令提示符下启动复制监视器。 启动复制监视器后，将发布服务器添加至监视器。 有关详细信息，请参阅 [从复制监视器中添加和删除发布服务器](../../../relational-databases/replication/monitor/add-and-remove-publishers-from-replication-monitor.md)。  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a>从 SQL Server Management Studio 启动复制监视器  
  
1.  连接至 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 中的 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]实例，然后展开服务器节点。  
  
2.  右键单击 **“复制”** 文件夹或它的任一子文件夹，然后单击 **“启动复制监视器”**。  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a>从命令提示符启动复制监视器  
  
1.  在命令提示符下，导航到工具安装目录。 默认路径为 [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\。  
  
2.  运行 sqlmonitor.exe。  
  
## <a name="see-also"></a>另请参阅  
 [监视复制](../../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  
