---
title: ProcessingQuery 元素 (ASSL) |Microsoft 文档
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ProcessingQuery Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- ProcessingQuery element
ms.assetid: d18e6f4b-c24c-4f73-8b85-4b6e8a82a695
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 51c6a61b134f83e1d63774104bf38dbe7c746369
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="processingquery-element-assl"></a>ProcessingQuery 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]包含要执行增量处理状态的通知的查询的参数化的文本。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<IncrementalProcessingNotification>  
   ...  
   <ProcessingQuery>...</ProcessingQuery>  
   ...  
</IncrementalProcessingNotification>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String|  
|默认值|InclusionThresholdSetting|  
|基数|1-1：出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[IncrementalProcessingNotification](../../../analysis-services/scripting/objects/incrementalprocessingnotification-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 中的表[DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md)引用**ProcessingQuery**的同级元素，由标识[TableID](../../../analysis-services/scripting/properties/tableid-element-assl.md)。  
  
 对应于的父元素**ProcessingQuery**在分析管理对象 (AMO) 对象模型并<xref:Microsoft.AnalysisServices.IncrementalProcessingNotification>。  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
