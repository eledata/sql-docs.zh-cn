---
title: CubePermissions 元素 (ASSL) |Microsoft 文档
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
- CubePermissions Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- CubePermissions
helpviewer_keywords:
- CubePermissions element
ms.assetid: 75a3a0c2-e1d4-4896-b0f5-2ea9c769b927
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: bd88d6e1854f525d791cb6377c5ee57a2998233d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="cubepermissions-element-assl"></a>CubePermissions 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]包含的权限适用于集合[多维数据集](../../../analysis-services/scripting/objects/cube-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Cube>  
   ...  
   <CubePermissions>  
      <CubePermission>...</CubePermission>  
   </CubePermissions>  
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
|父元素|[Cube](../../../analysis-services/scripting/objects/cube-element-assl.md)|  
|子元素|[CubePermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 分析管理对象 (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.CubePermissionCollection>。  
  
## <a name="see-also"></a>另请参阅  
 [权限数据类型 &#40;ASSL &#41;](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)   
 [集合 &#40;ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  
