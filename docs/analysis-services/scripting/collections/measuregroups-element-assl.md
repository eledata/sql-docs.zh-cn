---
title: Measuregroup 元素 (ASSL) |Microsoft 文档
ms.custom: ''
ms.date: 03/07/2017
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
- MeasureGroups Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- MeasureGroups
helpviewer_keywords:
- MeasureGroups element
ms.assetid: 80e970e9-6ea6-47a9-9e5c-d0f9b01c09c0
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: bdd3f7f93e491d9abb112ae3fe04975015be8882
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="measuregroups-element-assl"></a>MeasureGroups 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]包含的集合[MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)与父元素关联的元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Cube> <!-- or CubeBinding, Perspective -->  
   ...  
   <MeasureGroups>  
      <MeasureGroup>...</MeasureGroup> <!-- parent: Cube -->  
      <MeasureGroup xsi:type="MeasureGroupBinding">...</MeasureGroup> <!-- parent: CubeBinding -->  
      <MeasureGroup xsi:type="PerspectiveMeasureGroup">...</MeasureGroup> <!-- parent: Perspective -->  
   </MeasureGroups>  
   ...  
</Cube>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|InclusionThresholdSetting|  
|默认值|InclusionThresholdSetting|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[多维数据集](../../../analysis-services/scripting/objects/cube-element-assl.md)， [CubeBinding](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)，[透视](../../../analysis-services/scripting/objects/perspective-element-assl.md)|  
|子元素|请参阅表。|  
  
|祖先或父级|子元素|  
|------------------------|-------------------|  
|[Cube](../../../analysis-services/scripting/objects/cube-element-assl.md)|[度量值组](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)|  
|[CubeBinding](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)|[MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)类型的[MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)|  
|[透视](../../../analysis-services/scripting/objects/perspective-element-assl.md)|[MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)类型的[PerspectiveMeasureGroup](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 在 Analysis Management Objects (AMO) 对象模型中，对应的元素为 <xref:Microsoft.AnalysisServices.MeasureGroupCollection> 或 <xref:Microsoft.AnalysisServices.PerspectiveMeasureGroupCollection>。  
  
## <a name="see-also"></a>另请参阅  
 [集合 &#40;ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  
