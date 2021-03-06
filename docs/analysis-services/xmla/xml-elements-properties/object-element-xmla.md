---
title: 对象元素 (XMLA) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Object Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Object
- urn:schemas-microsoft-com:xml-analysis#Object
- microsoft.xml.analysis.object
helpviewer_keywords:
- Object element
ms.assetid: 99470537-2c4a-4072-9613-940c41c12487
caps.latest.revision: 16
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: cf077a2eba1e1d37a52536e77815839795ac7849
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="object-element-xmla"></a>Object 元素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]包含对象引用由父元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Alter> <!-- or any of the parent elements in the Element Relationships table -->  
...  
   <Object>  
      <!-- One or more object identifiers, depending on the parent element -->  
   </Object>  
...  
</Alter>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|InclusionThresholdSetting|  
|默认值|InclusionThresholdSetting|  
|基数|请参阅下表。|  
  
|祖先或父级|基数|  
|------------------------|-----------------|  
|[Alter](../../../analysis-services/xmla/xml-elements-commands/create-element-xmla.md)|0-1：可出现一次且仅出现一次的可选元素。|  
|其他|1-1：出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[Alter](../../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md)，[备份](../../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)， [ClearCache](../../../analysis-services/xmla/xml-elements-commands/clearcache-element-xmla.md)，[删除](../../../analysis-services/xmla/xml-elements-commands/delete-element-xmla.md)， [DesignAggregations](../../../analysis-services/xmla/xml-elements-commands/designaggregations-element-xmla.md)，[锁](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md)， [NotifyTableChange](../../../analysis-services/xmla/xml-elements-commands/notifytablechange-element-xmla.md)，[过程](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)，[订阅](../../../analysis-services/xmla/xml-elements-commands/subscribe-element-xmla.md)，[同步](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)|  
|子元素|必需的 Analysis Services 脚本语言 (ASSL) 元素。 指定通过列出的对象，并且其上级的 ID 元素 (不包括**服务器**对象。)例如，以下**对象**元素确定分区：<br /><br /> `<Object>`<br /><br /> `<DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>`<br /><br /> `<CubeID>Adventure Works</CubeID>`<br /><br /> `<MeasureGroupID>Internet Sales</MeasureGroupID>`<br /><br /> `<PartitionID>Inernet_Sales_2001</PartitionID>`<br /><br /> `</Object>`|  
  
## <a name="remarks"></a>Remarks  
 标识符的显示顺序并不重要。  
  
 有关**Alter**元素、 实例[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]如果用作默认对象**对象**未指定元素。  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
