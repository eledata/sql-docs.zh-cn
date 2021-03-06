---
title: MiningModelPermission 元素 (ASSL) |Microsoft 文档
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
- MiningModelPermission Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- MiningModelPermission
helpviewer_keywords:
- MiningModelPermission element
ms.assetid: 4bd2f7e7-ff0d-404e-96fb-7e2c4eeb91e9
caps.latest.revision: 39
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: f4792a244335a1cd6f325e7c09637426e5331ee0
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="miningmodelpermission-element-assl"></a>MiningModelPermission 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]定义的权限成员[角色](../../../analysis-services/scripting/objects/role-element-assl.md)元素具有对单个[MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<MiningModelPermissions>  
   <MiningModelPermission xsi:type="Permission">  
      <!-- The following elements extend Permission -->  
      <AllowDrillThrough>...</AllowDrillThrough>  
      <AllowBrowsing>...</AllowBrowsing>  
   </MiningModelPermission>  
</MiningModelPermissions>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|[权限](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|  
|默认值|InclusionThresholdSetting|  
|基数|0-n：可多次出现的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[MiningModelPermissions](../../../analysis-services/scripting/collections/miningmodelpermissions-element-assl.md)|  
|子元素|[AllowBrowsing](../../../analysis-services/scripting/properties/allowbrowsing-element-assl.md)， [AllowDrillThrough](../../../analysis-services/scripting/properties/allowdrillthrough-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 在[!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]，你可以通过添加启用对挖掘结构的钻取**AllowDrillthrough**权限[添加](../../../analysis-services/scripting/collections/miningstructurepermissions-element-assl.md)集合。 如果**AllowDrillthrough**挖掘结构和挖掘模型，任何成员具有的角色上启用[AllowDrillThrough 元素 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/allowdrillthrough-element-assl.md)对模型的权限可以查询数据挖掘模型，并返回结构列不包含在模型中，通过使用以下语法：  
  
```  
SELECT StructureColumn('<column name>') FROM <model>.CASES  
```  
  
 因此，为了保护敏感数据或个人信息，应该仅在需要时才授予对挖掘模型的 **AllowDrillthrough** 权限。 有关详细信息，请参阅[AllowDrillThrough 元素 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/allowdrillthrough-element-assl.md).  
  
 分析管理对象 (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.MiningModelPermission>。  
  
## <a name="see-also"></a>另请参阅  
 [对象 &#40;ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
