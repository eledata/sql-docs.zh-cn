---
title: "在 SQL Server 故障转移群集中承载报表服务器数据库 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.service: 
ms.component: install-windows
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd5f019-2857-452f-a023-cc3b9e93aec4
caps.latest.revision: "5"
author: markingmyname
ms.author: maghan
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: e3ae4f8b7a1abe9950ce2110da6914cc2b401438
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="host-a-report-server-database-in-a-sql-server-failover-cluster"></a>在 SQL Server 故障转移群集中承载报表服务器数据库
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 提供了对故障转移群集的支持，用户可以针对一个或多个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例使用多个磁盘。 对故障转移群集的支持仅限于报表服务器数据库；您不能将报表服务器服务作为故障转移群集的一部分运行。  
  
 若要在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 故障转移群集上承载报表服务器数据库，必须已安装并配置了群集。 然后，当您在 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 配置工具的“数据库安装”页中创建报表服务器数据库时，可以选择该故障转移群集作为服务器名称。  
  
 尽管报表服务器服务不能参与故障转移群集，但是您可以在装有 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 故障转移群集的计算机中安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 。 报表服务器的运行独立于故障转移群集。 如果在作为 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 故障转移实例一部分的计算机上安装了报表服务器，则不需要将故障转移群集用于报表服务器数据库；可以使用不同的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例来承载该数据库。  
  
## <a name="see-also"></a>另请参阅  
 [报表服务器数据库（SSRS 本机模式）](../../reporting-services/report-server/report-server-database-ssrs-native-mode.md)   
 [创建报表服务器数据库（SSRS 配置管理器）](../../reporting-services/install-windows/ssrs-report-server-create-a-report-server-database.md)  
  
  
