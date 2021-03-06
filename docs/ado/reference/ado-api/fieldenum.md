---
title: FieldEnum | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- FieldEnum
helpviewer_keywords:
- FieldEnum enumeration [ADO]
ms.assetid: be4eda13-d4e4-4d6b-bb0d-3310b0a96fc2
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5b00bf49dc7ee74c6da15b078e674af5e0472ec6
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="fieldenum"></a>FieldEnum
指定在中引用的特殊字段[记录](../../../ado/reference/ado-api/record-object-ado.md)对象的[字段](../../../ado/reference/ado-api/fields-collection-ado.md)集合。  
  
## <a name="remarks"></a>注释  
 这些常量提供访问与关联的特殊字段的"快捷方式"**记录**。 检索[字段](../../../ado/reference/ado-api/field-object.md)对象**字段**集合，然后获取其内容与**字段**对象的[值](../../../ado/reference/ado-api/value-property-ado.md)属性。  
  
|常量|“值”|Description|  
|--------------|-----------|-----------------|  
|**adDefaultStream**|-1|引用包含默认值的字段[流](../../../ado/reference/ado-api/stream-object-ado.md)与关联的对象**记录**。|  
|**adRecordURL**|-2|引用包含当前的绝对 URL 字符串的字段**记录**。|
