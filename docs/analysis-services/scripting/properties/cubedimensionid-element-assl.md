---
title: CubeDimensionID 元素 (ASSL) |Microsoft 文档
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
- CubeDimensionID Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- CubeDimensionID
helpviewer_keywords:
- CubeDimensionID element
ms.assetid: d1341fb2-9afe-40f1-a704-ce548bce48fc
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 4ba137b3f972f3aeddf9c948fa2f4f196556ad50
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="cubedimensionid-element-assl"></a>CubeDimensionID 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]标识[CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md)与父元素相关联的元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<AggregationDesignDimension> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <CubeDimensionID>...</CubeDimensionID>  
   ...  
</AggregationDesignDimension>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String|  
|默认值|InclusionThresholdSetting|  
|基数|1-1：可出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[AggregationDesignDimension](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md)， [AggregationDimension](../../../analysis-services/scripting/data-type/aggregationdimension-data-type-assl.md)， [AggregationInstanceCubeDimension](../../../analysis-services/scripting/data-type/aggregationinstancecubedimension-data-type-assl.md)， [CubeAttributeBinding](../../../analysis-services/scripting/data-type/cubeattributebinding-data-type-assl.md)， [CubeDimensionBinding](../../../analysis-services/scripting/data-type/cubedimensionbinding-data-type-assl.md)， [CubeDimensionPermission](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md)， [MeasureGroupDimension](../../../analysis-services/scripting/data-type/measuregroupdimension-data-type-assl.md)， [MeasureGroupDimensionBinding](../../../analysis-services/scripting/data-type/measuregroupdimensionbinding-data-type-assl.md)，[PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 对应的父级的元素**CubeDimensionID**分析管理对象 (AMO) 对象模型中是<xref:Microsoft.AnalysisServices.AggregationDesignDimension>， <xref:Microsoft.AnalysisServices.AggregationDimension>， <xref:Microsoft.AnalysisServices.CubeAttributeBinding>， <xref:Microsoft.AnalysisServices.CubeDimensionBinding>， <xref:Microsoft.AnalysisServices.CubeDimensionPermission>， <xref:Microsoft.AnalysisServices.MeasureGroupDimension>， <xref:Microsoft.AnalysisServices.MeasureGroupDimensionBinding>，和<xref:Microsoft.AnalysisServices.PerspectiveDimension>。  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
