---
title: 帐户元素 (ASSL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
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
- Accounts Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Accounts
helpviewer_keywords:
- Accounts element
ms.assetid: 3ec62f58-c19b-4b15-b040-8941521a389b
caps.latest.revision: 44
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 68975a4da8425a423f38bed174c180ea5d27299b
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="accounts-element-assl"></a>Accounts 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]包含在中定义的帐户类型的集合[数据库](../../../analysis-services/scripting/objects/database-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Database>  
   ...  
   <Accounts>  
      <Account>...</Account>  
   </Accounts>  
   ...  
</Database>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|无（集合）|  
|默认值|无（集合）|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[“数据库”](../../../analysis-services/scripting/objects/database-element-assl.md)|  
|子元素|[帐户](../../../analysis-services/scripting/objects/account-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 维度，其[类型](../../../analysis-services/scripting/properties/type-element-dimension-assl.md)元素设置为*帐户*、 可以具有一个属性，指定的帐户类型，例如收入，支出，等等，表示由维度中的成员。 然后使用的帐户类型[度量值](../../../analysis-services/scripting/objects/measure-element-assl.md)元素，其[AggregationFunction](../../../analysis-services/scripting/properties/aggregatefunction-element-assl.md)元素设置为*ByAccount*，以确定时要使用的聚合函数聚合该维度的成员。 **Accounts** 元素包含表示帐户类型和应应用于每个帐户类型的聚合函数的 **Account** 元素的集合。  
  
 如果聚合函数不同于使用的默认值，则必须列出帐户类型[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]为各种帐户类型。  
  
 有效帐户类型集是固定的。  
  
 分析管理对象 (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.AccountCollection>。  
  
## <a name="see-also"></a>另请参阅  
 [AccountType 元素 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/accounttype-element-assl.md)   
 [集合 &#40;ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  
