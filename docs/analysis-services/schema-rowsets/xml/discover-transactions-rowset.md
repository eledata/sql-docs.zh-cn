---
title: "DISCOVER_TRANSACTIONS 行集 |Microsoft 文档"
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
ms.assetid: 85789177-c5df-4336-a90c-c20d69277ab4
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 7ca0b129013f5bdced79d8fb8245893a3db7ff06
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="discovertransactions-rowset"></a>DISCOVER_TRANSACTIONS 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
返回系统上当前挂起的一组事务。  
  
 **适用于：**表格模型、 多维模型  
  
## <a name="rowset-columns"></a>行集列  
 **DISCOVER_TRANSACTIONS**行集包含以下各列。  
  
|列名|类型指示符|Description|  
|-----------------|--------------------|-----------------|  
|**TRANSACTION_ID**|**DBTYPE_WSTR**|事务唯一标识符，作为 GUID。|  
|**TRANSACTION_SESSION_ID**|**DBTYPE_WSTR**|事务会话的唯一标识符，以 GUID 形式表示。|  
|**TRANSACTION_START_TIME**|**DBTYPE_DBTIMESTAMP**|事务开始时的服务器 UTC 日期和时间。|  
|**TRANSACTION_ELAPSED_TIME_MS**|**DBTYPE_I8**|自事务开始起经过的时间（毫秒）。|  
|**TRANSACTION_CPU_TIME_MS**|**DBTYPE_I8**|自事务开始后所有请求占用的 CPU 时间（毫秒）。|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_TRANSACTIONS**行集可限制在下表中列出的列。  
  
|**列名**|**类型指示符**|**限制状态**|  
|---------------------|------------------------|---------------------------|  
|**ID**|**DBTYPE_WSTR**|選擇性。|  
|**SESSION_ID**|**DBTYPE_WSTR**|選擇性。|  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>使用 ADOMD.NET 返回行集  
 在使用 ADOMD.NET 和架构行集检索元数据时，可以使用 GUID 或字符串在 GetSchemaDataSet 方法中引用架构行集对象。 有关详细信息，请参阅 [Working with Schema Rowsets in ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets.md)。  
  
 下表提供了用于标识此行集的 GUID 和字符串值。  
  
|参数|值|  
|--------------|-----------|  
|GUID|a07ccd28-8148-11d0-87bb-00c04fc33942|  
|字符串|DISCOVER_TRANSACTIONS|  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
