---
title: AggregationDesignAttribute 数据类型 (ASSL) |Microsoft 文档
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
- AggregationDesignAttribute Data Type
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AggregationDesignAttribute
helpviewer_keywords:
- AggregationDesignAttribute data type
ms.assetid: 03d29d76-e4bd-4035-92cc-35149d83fbf9
caps.latest.revision: 42
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: f04d91622e1e898356e9ffe5f53572292b65216c
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="aggregationdesignattribute-data-type-assl"></a>AggregationDesignAttribute 数据类型 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]定义表示属性之间的关联的基元数据类型和[AggregationDesignDimension](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<AggregationDesignAttribute>  
   <AttributeID>...</AttributeID>  
      <EstimatedCount>...</EstimatedCount>  
</AggregationDesignAttribute>  
```  
  
## <a name="data-type-characteristics"></a>数据类型特征  
  
|特征|Description|  
|--------------------|-----------------|  
|基本数据类型|InclusionThresholdSetting|  
|派生数据类型|InclusionThresholdSetting|  
  
## <a name="data-type-relationships"></a>数据类型关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|InclusionThresholdSetting|  
|子元素|[AttributeID](../../../analysis-services/scripting/properties/attributeid-element-assl.md)， [EstimatedCount](../../../analysis-services/scripting/properties/estimatedcount-element-assl.md)|  
|派生元素|[属性](../../../analysis-services/scripting/objects/attribute-element-assl.md)([属性](../../../analysis-services/scripting/collections/attributes-element-assl.md)集合[AggregationDesignDimension](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md))|  
  
## <a name="remarks"></a>Remarks  
 分析管理对象 (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.AggregationDesignAttribute>。  
  
## <a name="see-also"></a>另请参阅  
 [AggregationDesignDimension 数据类型 &#40;ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md)   
 [Analysis Services 脚本语言 XML 数据类型 &#40;ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
