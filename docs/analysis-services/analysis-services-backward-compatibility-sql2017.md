---
title: SQL Server 自 2017 年 Analysis Services 向后兼容性 |Microsoft 文档
ms.date: 07/11/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.custom: ''
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing Analysis Services, backward compatibility
- backward compatibility [Analysis Services]
- compatibility [Analysis Services]
- Analysis Services, backward compatibility
- upgrading Analysis Services
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
ms.assetid: ''
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
monikerRange: '>= sql-analysis-services-2017 || = sqlallproducts-allversions'
ms.openlocfilehash: c353b84213516227980763b2a3c7e68d83e78a68
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="analysis-services-backward-compatibility-sql-2017"></a>Analysis Services 向后兼容性 (SQL 2017)
[!INCLUDE[ssas-appliesto-sql2017](../includes/ssas-appliesto-sql2017.md)]

本文介绍了功能的可用性和当前版本和以前的版本之间的行为更改。

## <a name="deprecated-features"></a>已弃用的功能
A*弃用功能*从在将来版本中，产品会停止但仍支持，并且包含在当前版本，以保持向后兼容。 建议您中止在新的和现有项目中使用已弃用的功能，为了保持与将来的发布的兼容性。

在此版本中已弃用以下功能：
  
|||  
|-|-|  
|**模式/类别**|**功能**|
|多维|数据挖掘|
|多维|远程链接的度量值组|
|表格|在 1100年和 1103年兼容性级别的模型|
|表格|表格对象模型属性： Column.TableDetailPosition，Column.IsDefaultLabel，Column.IsDefaultImage|


## <a name="discontinued-features"></a>停用的功能
A*停止使用功能*在早期版本中已弃用。 它可能继续将包含在当前版本中，但不再受到支持。 停用的功能可能会删除完全在将来版本或更新。

以下功能在早期版本中已弃用，不再支持此版本中。
  
|||  
|-|-|  
|**模式/类别**|**功能**|  
|表格|VertipaqPagingPolicy 内存属性值 (2)，启用分页到磁盘使用内存映射文件。|
|多维|远程分区|  
|多维|远程链接的度量值组|  
|多维|维度写回|  
|多维|链接的维度|
|工具|SQL Server Profiler for Trace Capture<br /><br /> 替代功能使用 SQL Server Management Studio 中嵌入的扩展事件探查器。  <br /> 请参阅 [使用 SQL Server 扩展事件监视 Analysis Services](../analysis-services/instances/monitor-analysis-services-with-sql-server-extended-events.md)。|  
|工具|跟踪重播 <br />替代功能的 Server Profiler。 没有替代功能。|  
|跟踪管理对象和跟踪 API|Microsoft.AnalysisServices.Trace 对象（包含 Analysis Services 跟踪和重播对象的 API）。 替代功能由多个部分组成：<br /><br /> -跟踪配置： Microsoft.SqlServer.Management.XEvent<br />-跟踪读取： Microsoft.SqlServer.XEvent.Linq<br />-   跟踪重播：无|  

## <a name="breaking-changes"></a>重大更改
A*是否重大更改*功能、 数据模型，应用程序代码或将脚本保存到不再函数将导致触发 after 升级到当前的发行版。

在此版本中有任何重大更改。

## <a name="behavior-changes"></a>行为更改
A*行为更改*都会影响在当前版本与以前的版本相比的相同功能的方式。 描述了仅重要行为更改。 不包括用户界面中的更改。

中详细介绍更改 MDSCHEMA_MEASUREGROUP_DIMENSIONS 和 DISCOVER_CALC_DEPENDENCY， [Analysis services 的 SQL Server 自 2017 年 1 CTP 2.1 中的新增](https://blogs.msdn.microsoft.com/analysisservices/2017/05/18/whats-new-in-sql-server-2017-ctp-2-1-for-analysis-services/)公告。


## <a name="see-also"></a>另请参阅
[Analysis Services 向后兼容性 (SQL Server 2016)](analysis-services-backward-compatibility.md)
