---
title: "OData 源属性 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: data-flow
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 59b56a5040b7ea0219478f134a358f447eac8ad1
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="odata-source-properties"></a>OData 源属性
在数据流中右键单击“OData 源”并单击“属性”时，可在“属性”窗口中看到“OData 源”组件的属性。  

## <a name="properties"></a>属性 
|“属性”|Description|  
|-|-|  
|CollectionName|从 OData 服务检索的集合的名称。 **“CollectionName”** 属性在 **UseResourcePath** 为 False 时使用。<br /><br /> 此属性能够使用表达式，可以在运行时设置值。 但是，如果集合的元数据与设计时使用的元数据不匹配，会出现验证错误，从而导致数据流执行失败。|  
|DefaultStringLength|此值为没有最大长度的字符串列指定默认长度。<br /><br /> **默认值：** 4000|  
|查询|OData 查询参数。 此属性能够使用表达式，可以在运行时设置。|  
|ResourcePath|在需要指定完整资源路径（而不仅仅是选择集合名称）时使用此属性。 此属性在 **UseResourcePath** 为 True 时使用。|  
|UseResourcePath|设置为 True 时， **ResourcePath** 值追加到基 URL 以确定 OData 馈送位置。 设置为 False 时 ，使用 **CollectionName** 值。<br /><br /> **默认值：** False|  
  
## <a name="see-also"></a>另请参阅
[OData 源](odata-source.md)
