---
title: "DISCOVER_TRACES 行集 |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 1be6a035-ffc9-489e-9d4d-7391b3e384e2
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: c79aa16cc7dc0d232c3acaa4407588932befc124
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="discovertraces-rowset"></a>DISCOVER_TRACES 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
提供有关服务器上当前活动的跟踪的信息。  
  
 **适用于：**表格模型、 多维模型  
  
## <a name="rowset-columns"></a>行集列  
 **DISCOVER_TRACES**行集包含以下各列。  
  
|列名|类型指示符|Description|  
|-----------------|--------------------|-----------------|  
|**TraceID**|**DBTYPE_WSTR**|跟踪 id。|  
|**TraceName**|**DBTYPE_WSTR**|跟踪名称。|  
|**LogFileName**|**DBTYPE_WSTR**|跟踪日志文件名。|  
|**LogFileSize**|**DBTYPE_I4**|跟踪日志文件大小。|  
|**LogFileRollover**|**DBTYPE_BOOL**|如果为 true，则表示应翻转日志文件；否则为 false。|  
|**AutoRestart**|**DBTYPE_BOOL**|如果为 true，则表示启用了自动重新启动选项；否则为 false。|  
|**CreationTime**|**DBTYPE_TIME**|该跟踪的创建日期和时间。|  
|**StopTime**|**DBTYPE_TIME**|跟踪的停止时间。|  
|**类型**|**PF_DBTYPE_WSTR**|跟踪的类型。|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_TRACES**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**TraceId**|**DBTYPE_I4**|選擇性。|  
|**类型**|WSTR|選擇性。|  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>使用 ADOMD.NET 返回行集  
 在使用 ADOMD.NET 和架构行集检索元数据时，可以使用 GUID 或字符串在 GetSchemaDataSet 方法中引用架构行集对象。 有关详细信息，请参阅 [Working with Schema Rowsets in ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets.md)。  
  
 下表提供了用于标识此行集的 GUID 和字符串值。  
  
|参数|值|  
|--------------|-----------|  
|GUID|a07ccd1a-8148-11d0-87bb-00c04fc33942|  
|字符串|DISCOVER_TRACES|  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
