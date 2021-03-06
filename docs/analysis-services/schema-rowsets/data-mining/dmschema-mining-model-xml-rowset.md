---
title: DMSCHEMA_MINING_MODEL_XML 行集 |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DMSCHEMA_MINING_MODEL_XML
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DMSCHEMA_MINING_MODEL_XML rowset
ms.assetid: f58b00e9-3f72-4cff-b448-21a9fb529772
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: b27cfca519f1a5afce1a58bf89a6434f6f85bd34
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="dmschemaminingmodelxml-rowset"></a>DMSCHEMA_MINING_MODEL_XML 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]返回挖掘模型的 XML 结构。 该 XML 字符串的格式遵循预测模型标记语言 (PMML 2.1) 标准。  
  
## <a name="rowset-columns"></a>行集列  
 **DMSCHEMA_MINING_MODEL_XML**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**MODEL_CATALOG**|**DBTYPE_WSTR**||目录名称。 使用模型为其成员的数据库的名称填充。|  
|**MODEL_SCHEMA**|**DBTYPE_WSTR**||非限定的架构名称。 此列不支持通过[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]; 它始终包含**NULL**。|  
|**MODEL_NAME**|**DBTYPE_WSTR**||模型名称。 此列不能包含**NULL**。|  
|**MODEL_TYPE**|**DBTYPE_WSTR**||模型类型。 它是特定于访问接口的字符串。 它可以是**NULL**。|  
|**MODEL_GUID**|**DBTYPE_GUID**||标识模型的 GUID。 提供程序并使用 Guid 来标识表返回**NULL**。|  
|**MODEL_PMML**|**DBTYPE_WSTR**||以 PMML 格式表示的模型内容的 XML 表示形式。|  
|**大小**|**DBTYPE_UI4**||XML 字符串中的字节数。|  
|**位置**|**DBTYPE_WSTR**||XML 文件的位置。 它是**NULL**如果物理文件不用于存储。|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 对于 DMSCHEMA_MINING_MODEL_XML 行集，可对下表中列出的列进行限制。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**MODEL_CATALOG**|**DBTYPE_W**STR|可选。|  
|**MODEL_SCHEMA**|**DBTYPE_WSTR**|可选。|  
|**MODEL_NAME**|**DBTYPE_WSTR**|可选。|  
|**MODEL_TYPE**|**DBTYPE_WSTR**|可选。|  
  
## <a name="see-also"></a>另请参阅  
 [数据挖掘架构行集](../../../analysis-services/schema-rowsets/data-mining/data-mining-schema-rowsets.md)  
  
  
