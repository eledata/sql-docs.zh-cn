---
title: AggregationInstance 元素 (ASSL) |Microsoft 文档
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
- AggregationInstance Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- AggregationInstance element
ms.assetid: 2e77e9e1-9f2c-4df4-9aa6-5b7b911016a3
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: d4ec54603b07f2e84e2de045426e56196e33242d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="aggregationinstance-element-assl"></a>AggregationInstance 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]定义一个分区的聚合实例。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<AggregationInstances>  
   <AggregationInstance>  
      <AggregationType>...</AggregationType>  
      <AggregationID>...</AggregationID>  
      <Source>...</Source>  
      <Dimensions>...</Dimensions>  
      <Measures>...</Measures>  
      <Annotations>...</Annotations>  
   </AggregationInstance>  
</AggregationInstances>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|InclusionThresholdSetting|  
|默认值|InclusionThresholdSetting|  
|基数|0-n：可多次出现的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[AggregationInstances](../../../analysis-services/scripting/collections/aggregationinstances-element-assl.md)|  
|子元素|[AggregationID](../../../analysis-services/scripting/properties/aggregationid-element-assl.md)， [AggregationType](../../../analysis-services/scripting/properties/aggregationtype-element-assl.md)，[批注](../../../analysis-services/scripting/collections/annotations-element-assl.md)，[维度](../../../analysis-services/scripting/collections/dimensions-element-assl.md)，[度量值](../../../analysis-services/scripting/collections/measures-element-assl.md)， [源](../../../analysis-services/scripting/properties/source-element-binding-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 当[分区](../../../analysis-services/scripting/objects/partition-element-assl.md)元素使用[AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md)元素以生成该分区的聚合每个[聚合](../../../analysis-services/scripting/objects/aggregation-element-assl.md)中**AggregationDesign**为该分区实例化。 多个分区可使用同一聚合设计来生成已定义聚合的多个实例。 **AggregationInstance**元素表示的定义聚合的实例。  
  
 分析管理对象 (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.AggregationInstance>。  
  
## <a name="see-also"></a>另请参阅  
 [对象 &#40;ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
