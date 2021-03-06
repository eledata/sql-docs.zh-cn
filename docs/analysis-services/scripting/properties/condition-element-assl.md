---
title: 条件元素 (ASSL) |Microsoft 文档
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
- Condition Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- condition
helpviewer_keywords:
- Condition element
ms.assetid: 9c3cb31c-4aa1-49e4-aeb2-6cab54db0be3
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a4b91dcedde39e7d02c6d0263cf37de0fa7b3e62
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="condition-element-assl"></a>Condition 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]包含的多维表达式 (MDX) 表达式，它确定是否[操作](../../../analysis-services/scripting/objects/action-element-assl.md)父元素将应用到目标。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Action>  
   ...  
   <Condition>...</Condition  
      ...  
</Action>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String|  
|默认值|InclusionThresholdSetting|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[操作](../../../analysis-services/scripting/objects/action-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 **条件**元素包含计算结果为布尔值的 MDX 表达式。 如果表达式返回**True**，则**操作**适用于中指定的目标[目标](../../../analysis-services/scripting/properties/target-element-assl.md)元素。 否则为**操作**不适用。  
  
 对应于的父元素**条件**在分析管理对象 (AMO) 对象模型并<xref:Microsoft.AnalysisServices.Action>。  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
