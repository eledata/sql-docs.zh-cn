---
title: HoldoutMaxPercent 元素 |Microsoft 文档
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
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- HoldoutMaxPercent
helpviewer_keywords:
- HoldoutMaxPercent element
ms.assetid: e375cc51-5f9d-4252-98a1-326ca0dbbf83
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 5282451ccad6f4cd8f3deb80542f5b2d72e3e05d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="holdoutmaxpercent-element"></a>HoldoutMaxPercent 元素
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]指定数据源中将用于维持部分包含的测试组的事例的最大百分比[MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)元素。 其余事例用于定型。 值为 0 指示对可作为测试集来维持的事例数没有限制。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<MiningStructure>  
   ...  
   <ddl100_100:HoldoutMaxPercent>...</ddl100_100:HoldoutMaxPercent>  
   ...  
</MiningStructure>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|0 到 99 之间的整数。|  
|默认值|30|  
|基数|0-1：可出现一次并仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 如果为两个指定值**HoldoutMaxPercent**和**HoldoutMaxCases**，算法将限制测试设置为较小的两个值。  
  
 如果**HoldoutMaxCases**设置为默认值 0，并且尚未为设置一个值**HoldoutMaxPercent**，该算法使用完整的数据集以进行训练。  
  
 新属性**HoldoutMaxCases**， **HoldoutMaxPercent**， **HoldoutSeed**，或**HoldoutActualSize**仅在中可用[!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]及更高版本。 因此，必须在这些属性前加上新的命名空间前缀，如语法说明中所示，否则 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 将返回错误。  
  
> [!NOTE]  
>  在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 中，[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 不支持对挖掘结构使用维持分区。 因此，[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]包含维持参数之一的脚本语言 (ASSL) 语句**HoldoutMaxCases**， **HoldoutMaxPercent**， **HoldoutSeed**，或**HoldoutActualSize**，不能在[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]。 如果在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 中将这些维持参数之一用于 ASSL 语句，则 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 将返回错误。  
  
 对应于的父元素**HoldoutMaxPercent**在分析管理对象 (AMO) 对象模型并<xref:Microsoft.AnalysisServices.MiningStructure>。  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)   
 [HoldoutMaxCases 元素](../../../analysis-services/scripting/properties/holdoutmaxcases-element.md)   
 [HoldoutSeed 元素](../../../analysis-services/scripting/properties/holdoutseed-element.md)   
 [HoldoutActualSize 元素](../../../analysis-services/scripting/properties/holdoutactualsize-element.md)  
  
  
