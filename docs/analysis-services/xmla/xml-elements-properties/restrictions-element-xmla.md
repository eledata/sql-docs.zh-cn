---
title: 限制元素 (XMLA) |Microsoft 文档
ms.custom: ''
ms.date: 03/04/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Restrictions Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#Restrictions
- http://schemas.microsoft.com/analysisservices/2003/engine#Restrictions
- microsoft.xml.analysis.restrictions
helpviewer_keywords:
- Restrictions element
ms.assetid: e745ce13-b468-4372-a6f0-0da3d772dda3
caps.latest.revision: 11
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 704906a3b42557feace9c75ce5f2702be553ff08
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="restrictions-element-xmla"></a>Restrictions 元素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]包含限制列和数据使用[发现](../../../analysis-services/xmla/xml-elements-methods-discover.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
  
<Discover>  
...  
   <Restrictions>  
      <RestrictionList>...</RestrictionList>  
   </Restrictions>  
...  
</Discover>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|InclusionThresholdSetting|  
|默认值|InclusionThresholdSetting|  
|基数|1-1：出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[发现](../../../analysis-services/xmla/xml-elements-methods-discover.md)|  
|子元素|[RestrictionList](../../../analysis-services/xmla/xml-elements-properties/restrictionlist-element-xmla.md)|  
  
## <a name="remarks"></a>Remarks  
 **限制**元素表示限制列和用来限制检索的信息的数据**发现**方法。  
  
## <a name="example"></a>示例  
  
```  
<Discover xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <RequestType>DISCOVER_PROPERTIES</RequestType>  
   <Restrictions>  
      <RestrictionList xmlns="urn:schemas-microsoft-com:xml-analysis">  
         <PropertyName>Catalog</PropertyName>  
      </RestrictionList>  
   </Restrictions>  
   <Properties />  
</Discover>  
```  
  
## <a name="see-also"></a>另请参阅  
 [属性 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
