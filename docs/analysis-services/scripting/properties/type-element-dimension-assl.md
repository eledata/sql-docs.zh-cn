---
title: 类型元素 （维度） (ASSL) |Microsoft 文档
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
- Type Element (Dimension)
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- TYPE
helpviewer_keywords:
- Type element
ms.assetid: 6a2798b1-26c7-49d8-b556-e681c69d9574
caps.latest.revision: 37
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: aac5535e8d94cdd602b139bd9046b77a15cbad5f
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="type-element-dimension-assl"></a>Type 元素 (Dimension) (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]提供有关内容的维度的信息。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Dimension>  
      ...  
   <Type>...</Type>  
   ...  
</Dimension>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String（枚举）|  
|默认值|*正则*|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 某些值**类型**，例如*帐户*，确定特定的行为。  
  
 此元素的值限定为下表中列出的字符串之一。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|*正则*|该维度是一个常规维度。|  
|*Time*|该维度是一个时间维度。<br /><br /> 注意： 此值指示维度支持特定于时间维度的功能。|  
|*地理位置*|维度包含地域属性。|  
|*组织*|维度包含单位属性。|  
|*物料清单*|维度包含物料清单属性。|  
|*帐户*|维度包含帐户相关属性。<br /><br /> 注意： 此值指示维度支持特定于帐户维度的功能。|  
|*客户*|维度包含客户相关属性。|  
|*产品*|维度包含产品相关属性。|  
|*方案*|维度包含方案相关属性。|  
|*定量*|维度包含定量属性。|  
|*实用工具*|维度包含效用属性。|  
|*货币*|维度包含货币属性。|  
|*费率*|维度包含汇率属性。|  
|*Channel*|维度包含渠道属性。|  
|*升级*|维度包含促销相关属性。|  
  
 对应于的允许值为枚举**类型**在分析管理对象 (AMO) 对象模型并<xref:Microsoft.AnalysisServices.DimensionType>。  
  
 对应于的父元素**类型**在分析管理对象 (AMO) 对象模型并<xref:Microsoft.AnalysisServices.Dimension>。  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
