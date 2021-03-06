---
title: DISCOVER_ENUMERATORS 行集 |Microsoft 文档
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
- DISCOVER_ENUMERATORS
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DISCOVER_ENUMERATORS rowset
ms.assetid: ddc7b13c-3135-4419-8166-eddd459167da
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 0be0cb9885cf48911a31ba4181a235eae032094b
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="discoverenumerators-rowset"></a>DISCOVER_ENUMERATORS 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]返回的名称、 数据类型和枚举数支持的枚举值列表[!INCLUDE[msCoName](../../../includes/msconame-md.md)]XML for Analysis (XMLA) 提供程序特定数据源。 XMLA 访问接口可发布它所识别的所有枚举常量。  
  
 如果调用[发现](../../../analysis-services/xmla/xml-elements-methods-discover.md)方法替换**DISCOVER_ENUMERATORS**中的枚举值[RequestType](../../../analysis-services/xmla/xml-elements-properties/requesttype-element-xmla.md)元素，**发现**方法返回**DISCOVER_ENUMERATORS**架构行集。  
  
## <a name="rowset-columns"></a>行集列  
 每个枚举器都包含多个元素，枚举中的每个值都对应一个元素。 表示每个枚举器的行集是平面的，可以对属于同一枚举的多个元素重复使用相应枚举器的名称。  
  
 **DISCOVER_ENUMERATORS**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**枚举名称**|**DBTYPE_WSTR**||包含一组值的枚举器的名称。|  
|**EnumDescription**|**DBTYPE_WSTR**||枚举器的可本地化说明。 可以是**NULL**。|  
|**EnumType**|**DBTYPE_WSTR**||枚举值的数据类型。|  
|**ElementName**|**DBTYPE_WSTR**||枚举器集中一个值元素的名称。<br /><br /> 示例： **TDP，**|  
|**ElementDescription**|**DBTYPE_WSTR**||（可选）元素的可本地化说明。 可以是**NULL**。|  
|**ElementValue**|**DBTYPE_WSTR**||元素的值。 可以是**NULL**。<br /><br /> 示例： **01**|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_ENUMERATORS**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**枚举名称**|**DBTYPE_WSTR**||  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
