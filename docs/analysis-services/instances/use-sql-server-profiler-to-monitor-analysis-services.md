---
title: "使用 SQL Server Profiler 监视 Analysis Services |Microsoft 文档"
ms.custom: 
ms.date: 01/23/2018
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 736b5de1af85d3143e8b258de0a3b388e5d2ea01
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a>Use SQL Server Profiler to Monitor Analysis Services
[!INCLUDE[ssas-appliesto-sqlas-all-aas](../../includes/ssas-appliesto-sqlas-all-aas.md)]

  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 跟踪引擎进程事件（例如批处理或事务的启动），并捕获有关这些事件的数据，从而使你可以监视服务器和数据库活动（例如，用户查询或登录活动）。 可以将 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 数据捕获到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 表或文件中，供后续分析使用，还可以重播在相同或其他 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 实例中捕获的事件，以确切了解所发生的情况。 可以实时或分步重播事件。 在同一计算机中运行跟踪事件和性能计数器是非常有用的。 事件探查器可基于时间将跟踪事件与性能计数器相关联，并在一条时间线上同时显示这两者。 跟踪事件提供详细信息，而性能计数器提供聚合视图。 有关如何创建和运行跟踪的信息，请参阅 [为重播创建事件探查器跟踪 (Analysis Services)](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md)。  
  
 下表对本部分的主题进行了说明：  
  
## <a name="in-this-section"></a>本節內容  
  
|主题|Description|  
|-----------|-----------------|  
|[通过 SQL Server Profiler 监视 Analysis Services 简介](../../analysis-services/instances/introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|说明如何使用 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 监视 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 实例。|  
|[为重播创建事件探查器跟踪 (Analysis Services)](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md)|说明使用 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]创建用于重播的跟踪的要求。|  
|[Analysis Services 跟踪事件](../../analysis-services/trace-events/analysis-services-trace-events.md)|说明 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 事件类。 这些事件类映射到 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 所生成的操作并用于跟踪重播。|  
  
## <a name="see-also"></a>另请参阅  
 [监视 Analysis Services 实例](../../analysis-services/instances/monitor-an-analysis-services-instance.md)  
  
  
